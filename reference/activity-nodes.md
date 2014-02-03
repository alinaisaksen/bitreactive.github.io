---
title: Activity Nodes
layout: reference
---

# Activity Nodes

<p class="summary">This section explains all of the elements used in activity blocks.</p> 


The activities are graphs consisting of different activity nodes. 
The activity nodes are connected by edges, which are either control flows or object flows. 
Object flows work like control flows, but can also pass data.

In the end, activities describe in which sequence operations within building blocks are executed. 
The different activity nodes are used to describe how the different flows depend on each other. 


## Initial Nodes
Initial nodes mark the start of a system and hence only exist at the topmost level. Typically, each system contains one or more initial nodes. Before the system is started, initial nodes hold one token, which moves downstream at startup.

\includegraphics[width=\linewidth]{figures/initial.pdf}

Usually you need to initialize several blocks during startup. Instead of a single initial state and a fork with a lot of flows (resulting in ugly layout), use several initial nodes. They are all fired at the same time, just as if they were connected by a fork. The layout depicted on right hand-side of the figure below is easier to read, since it avoids the fork with the edges as used on the left-hand side.
 
## Decision Nodes
Decision nodes introduce alternative branches, depending on the values of the guards attached to them. You have to ensure that at least one of the outgoing guards is enabled to avoid blocking. Decision nodes have object flows both for the ingoing as well as for the outgoing edges.

### Boolean Guards
To make a decision dependent on a boolean value provided by an operation, simply use a pair of outgoing branches from a decision node, and add the guards true and false. The edges entering and leaving the decision nodes need to be object flows, since they transport the boolean value to the guards.

\includegraphics[width=4cm]{figures/decisions-boolean.pdf}

### Constant Strings and Integers
To decide between more than two branches, you can use literal values. In the example, the operation produces a string value, which is then compared with the literal string values specified by each outgoing branch. To make sure that the decision is non-blocking, you must add an else branch in any case. Literal integers can be specified as well.

\includegraphics[width=\linewidth]{figures/decisions-literals.pdf}

## Fork Nodes
Fork nodes introduce concurrent flows that execute in parallel. Actions belonging to different flows may be executed in any order, depending on how a system is implemented. Usually this means that these flows should not write on the same variables to avoid interference.

Forks may be connected using both control and object flows. Some of the outgoing edges may be of type object flow while others are of type control flow. However, if object flows are involved, all outgoing object flows and the ingoing edge have to provide the same data type.

### Concurrency
Fork nodes can also be considered as an assurance by the developer of the application regarding the behavior of their outgoing flows: A fork node allows a system that implements a specification to execute the operations of parallel branches in any order, without worrying about data consistency. If you are unsure, if two operations can be executed in parallel, do not use a fork node at all and simply execute these operations in a certain sequence. In the example below, prepareData may be executed after useData. Therefore, this value may not be initialized at all.

\includegraphics[width=6cm]{figures/fork.pdf}

Fork and decision nodes result in very different behavior:

  - Fork nodes introduce parallel flows, all executed within the same run-to-completion step.
  - Decision nodes introduce alternative flows, where only one is executed in a run-to-completion step.

## Merge Nodes

Merge nodes make that several flows are merged into one, by forwarding all incoming tokens to the outgoing edge. Both control and object flows are possible for merge nodes, however all attached flows have to provide the same data type. Merge nodes may have only one outgoing flow, but as many incoming as needed. For layout reasons, it is often better to have several merge node in a series rather than one single one, as shown with the two merge nodes (1) and (2) below.

\includegraphics[width=\linewidth]{figures/merge.pdf}

## Join Nodes
Join nodes synchronize several flows. Tokens are stored on the incoming edges, and as soon as the last missing token arrives, the join node fires through, with one token flowing along the outgoing edge.

A join node may have two or more incoming edges. At most one of them may be an object flow. In case all incoming edges are control flows, the outgoing edge has to be a control flow as well.

Join and merge nodes have a very different effect:

  - With a join node, all incoming flows have to provide a token so that the outgoing flow is executed. This means that a join synchronizes several incoming flows.
  - With a merge node, the incoming flows are not synchronized at all. The flow originating from a merge is executed whenever one of the incoming flows is executed.

## Flow Final Nodes
Flow final nodes terminate a flow. A token flowing into a flow final node is simply removed. 
Flow final nodes are only needed in two situations:

  - When a decision should have branch in which nothing should happen, this branch can point to a flow final node.

\includegraphics[width=7cm]{figures/flow-final-decision.pdf}

  - When an incoming pin of a block should not result in any action, it may lead to a flow final node. This may be useful if the pin is needed for compatibility with previous versions of the block, or if the ESM of the block should make a state change, but no internal action.

Note that operations may lead to a flow final node, but this node may be left our for simplicity.

\includegraphics[width=5cm]{figures/flow-final-operation.pdf}


## Activity Final Nodes
Activity final nodes terminate a flow, but in comparison to flow final nodes they also terminate an entire application by removing all tokens from the included join nodes, event receptions and timers. Since activity final nodes terminate an application, they can only be used at the system level.

\includegraphics[width=2cm]{figures/activity-final.pdf}

% write about deadlock detection

### Activity Final vs. Flow Final
Both types of final nodes terminate a flow. The activity final node, however, also terminates the entire system.


## Timers
To realize a simple delay, use the timer element. By default, the duration can be determined as a constant (at design-time). To change the duration at run-time, you can connect an object flow to a timer that provides an integer (int). The value will be used to set the duration of the timer in milliseconds.If a timer is activated again before it expired, the timer is restarted, which means that the time period begins again.

\includegraphics[width=4cm]{figures/timer-1.pdf}

*Flow Breaks.* In some situations, we just want to interrupt the execution of a flow for technical reasons, so that other behavior of the system may be executed in between. This can happen for instance to comply with the ESM of a block. In these cases, timers with a delay of 0 ms can be used. To obtain this type of timer, add a timer component and from its context menu, set the duration to 0 ms. This kind of timer looks like the following figure.

\includegraphics[width=1cm]{figures/flowbreak.pdf}

*Forwarding of Data.* Both timers and flow breaks may pass data when used within an object flow. The example below shows a flow break within an object flow passing data of type JSONObject.

\includegraphics[width=\linewidth]{figures/timer-2.pdf}

## Building Blocks for Special Timers
In many cases, you may need more control over the timer, for instance, turn it off again. For these cases exist dedicated building blocks in the standard library, from which we introduce some below.

\includegraphics[width=\linewidth]{figures/timer-3.pdf}

*Timers with Termination.* In some cases, you want the possibility to stop a timer. For this case, there are two building blocks in the Timers Library (com.bitreactive.library.timers), i.e., Timer (1) and Timer 2 (2). Both realize timers that can be aborted via a pin. The only difference is that the duration for Timer is determined by an instance parameter and Timer 2 accepts a duration at run-time.

*Periodic Timers.* Periodic Timers can be realized easiest by the special building block Timer Periodic (3). This block comes in two variants. The first takes the duration as an instance parameter. The second variant accepts the duration of the period as input parameter.

*Timeout Blocks.* To observe if a certain event happens within a certain time, i.e., an event arrives in time, use the Timeout block (4) or its variants from the library.

## Variables
A building block can declare variables that store data, like the one for a String below (1). This data can be accessed by all operations within the building block, and there are specific set (2) and get (3) actions for variables.

\includegraphics[width=\linewidth]{figures/variables.pdf}

## Operations and Java Methods
Operation nodes refer to Java methods and work on data or APIs. If an operation has several parameters, it works similar to a join node. Each pin for the parameter can store a token, and the operation is executed once the last missing token arrives.

\includegraphics[width=\linewidth]{figures/operations.pdf}

The content of operations is described by Java methods. The behavior of the building block determines when and in which sequence Java methods are never allowed to block or wait. This rule ensures that applications can be executed efficiently and stay responsive. If some code has to wait for an external response (for instance an HTTP request) there exist notification patterns to decouple the behavior, using threads and event receptions.

Exceptions must be caught within the methods. Java methods that represent operations must not throw any exceptions. This means you have to think of all exceptions that may happen and handle them appropriately.


In general, Java allows more than one method with the same name as long as they have a different signature, i.e., a distinct set of parameters. To keep the connection between the activity and the Java code simple, only one Java method with a certain name may exist.

 
## Event Receptions
Event receptions represent internal events needed for synchronization. They tell for instance when a certain operation or API delivers a result or an interrupt happened. As long as a token rests on them, they are ready to receive the specified event.

Events always originate from the code of a building block. This means, that some operation of the building block must contain code that dispatches this event, otherwise it will never be received. Three things are important for declaring an event, as shown below. (1) The reception in the behavior of a block, and (2) it's dispatching from code. An event declaration can add parameter to an event. This parameter has to be fed into the system from code when the event is dispatched (2), and the behavior will automatically declare a reception pin for that parameter.

\includegraphics[width=\linewidth]{figures/events.pdf}

By default, an event reception is deactivated once the event happens, and it will not receive any more of them, until it is activated again, as in (1) below. To continuously listen to incoming events, a construction with a fork can be used, as shown in (2). Instead of the construction with the fork, the event reception can also be marked with an "*", so show that it is continuously enabled (3).

\includegraphics[width=\linewidth]{figures/events-2.pdf}