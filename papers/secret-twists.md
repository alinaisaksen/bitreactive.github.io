---
title: Secret Twists to Efficiently Develop Reactive Systems
layout: article
---


# The Secret Twists to Efficiently Develop Reactive Systems


The three most powerful principles to develop reactive systems are the following:

  - Divide and conquer, then reuse effectively
  - Visualize your system
  - Automatically and formally verify everything, always

These are such fundamental principles that one can hardly call them new. 
It is surprising, however, that they do not live up to their potential in programmers' daily routines. In this whitepaper, we present the secret twists to make these principles work for you and your organization.



# Introduction

Reactive simply means to react appropriately to events, keeping an eye on time, and handling events as parallel as possible, but in an ordered way. The ability to react correctly is important for several reasons:

  - If your application has a user interface, it should quickly react on user input and deliver feedback to users instantly.
  - If your application is heavy on communication, it needs to process incoming messages quickly, and react appropriately on network troubles without introducing any errors.
  - If your application decomposes tasks into subtasks, it should execute subtasks in an optimal way, as concurrent and independent as possible, so that the overall result can be provided as quickly as possible.

Reactive systems typically pose strict requirements on security, dependability, responsiveness and efficiency. They must work robustly even if the network is down or if there are transmission errors. In addition, many systems must work without any intervention from the outside environment.

To meet these requirements requires a careful design of reactive behavior.

It is difficult to develop reactive systems right with pure programming only.

Your domain probably requires applications that are more reactive than you think.

The problem is that reactive behavior is hard to get right by pure programming: Concurrent behavior becomes very complicated even for small systems, resulting in synchronization problems. Describing concurrency and synchronization using pure code, in a tangible manner is therefore almost impossible. To understand a system, a programmer must jump around in the code in an endless number of possible scenarios. Ad hoc and last-minute-fixes add more lines of code and obscures the system further. As a result, the business-specific code is buried down under thousands of lines of code. Valuable logic is therefore hidden, not only from the project stakeholders, but also from developers. How the system is designed will affect the potential of its evolution and the cost of change. Therefore, it is important that the system is designed correctly from the start. A successful software design for reactive systems follows three design principles:

  - Divide and conquer, then reuse effectively.
  - Visualize your system.
  - Automatically and formally verify everything, always.

Though these principles seem intuitive, doing it right is not. In this whitepaper, we present the necessary twists to make them work for you and your organization.