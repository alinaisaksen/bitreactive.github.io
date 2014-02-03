---
title: Activity Semantics
layout: reference
---

# Run-to-Completion Steps

The behavior of an application is executed in run-to-completion steps. These are steps that are executed in isolation. An application waits until an event happens. Once this event happens, the application executes all actions that can be executed, and then waits again for the next event. For the token flows this means that a token movement is started by an event, and that the run-to-completion step is finished once all tokens have found their new stable positions.

A run-to-completion step corresponds in an activity diagram to a subgraph of the activity, consisting of all nodes and edges that are traversed within one single step. Each edge that is part of a run-to-completion step is passed by exactly one token. Therefore, run-to-completion steps can be visualized through highlighting parts the activity diagram, which is done in the animation modus of the tool.

An run-to-completion step may also pass through blocks. Each block of an activity contributes in one of three ways to an run-to-completion step:

  - The block is passed by tokens, and contributes with exactly one ESM transition to the run-to-completion step.
  - The block is not involved in the run-to-completion step at all. No tokens are moved through it, and the block stays in its state.
  - The block is blocked, since tokens arrive in a way that harm its ESM. Then token arriving at the pins are simply stopped.

## Triggering Events
An run-to-completion step is always triggered by exactly one of the following events:
  
  - Startup via initial nodes, when the application or system is activated.
  - Timeouts, once timers expire.
  - Event receptions, once an event is dispatched by one of the building block's operations.
  - Spontaneous ESM transitions (which are triggered from inside a building block, effectively by an event reception or timeout within a building block.)

\includegraphics[width=\linewidth]{figures/run-to-completion.pdf}

## Stable Positions
All run-to-completion steps start with a single token. However, since fork nodes may be involved, there may be more than one token travel within a single run-to-completion step. The run-to-completion step finishes once all moving tokens found a stable resting position. Such stable positions are the following:
  
  - A token enters a timer. This means that the timer is activated, and the token entering the timer stops. The token will leave the timer (and trigger a new activity step) once the timer expires.
  - A token enters an event reception. This means that the event reception is activated, and the token entering the event reception stops. The token will leave the event reception (and trigger a new run-to-completion step) once the event occurs.
  - A token stops once it enters a flow final node. In this case, the token is just removed.
  - A token also stops when it enters an activity final node. In contrast to a flow final node, this means that the entire application is terminated after all token in this activity step have arrived in their final position.
  - A token stops when it enters an incomplete join node. This means that the join node still needs tokens to arrive on the other incoming edges to fire through.
  - A token stops when it enters an operation which has many parameters and is incomplete. This means that the operation still needs tokens to arrive on the other pins for parameters to fire through.

In the following cases, tokens do **not** stop:
  
  - A token does not stop in set and get variable actions.
  - A token does not stop in a decision node.
  - A token does not stop in a join node in which all other incoming edges already provide a token. Then the join node fires immediately, without waiting.
  - A token does not stop in an operation which has zero or only one parameter. This is because we assume operations do not block, but to execute quickly. If an operation should nevertheless perform a long-running operation, there exists a special pattern to handle this case, using a thread and an event reception.
  - Operations with several parameters work similar to joins. Tokens do not stop if all parameters are available.
