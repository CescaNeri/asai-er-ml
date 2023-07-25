## Intelligent Agents

**Algorithms** -> list of reproducible steps to transform input in output

* Requires clear representation for input, output and storage
* Study algorithm's time/memory requirements and TERMINATION
* Algorithms can be combined to solve more complex problems

### Artificial Intelligence

Create algorithms which emulate some typically-human capabilities, like:

* Path-finding (find a path between two points in the space)
* Logical reasoning (infer consequences from premises)
* Planning (figure out which actions needed to reach a goal)
* Learning (lean new behaviors from examples)

*Are these algorithms intelligent?*

No, if it considered alone.
The intelligence of a software is referred as the set of algorithms which allow for intelligent tasks which can be COMBINED to perform complex solutions.

Intelligent software entities => **INTELLIGENT AGENTS**

### Agents

An agent is an entity capable of acting to achieve some **goal**, while being situated into some **environment** which can be both perceived or affected.
Possibly, the agent in the environment **interact** with other agents.

**Goal** -> description of the state of the world (environment + other agents) to be **reached**.

* **Weak** goal (hard-coded in the agent)
* **Strong** goal (explicit representation of the goal)

Other distinctions:

* **Achievement** goal (situation to reach)
* **Test** goal (information to acquire)
* **Maintenance** goal (situation to keep stable)
* **Sub-goal** (a goal necessary to reach another goal)

The **environment** refers to the space where agents live and interact.
It enables and constraints agents' **interaction**, **perception** and **action**.

**Perception** refers to the operation by which agents gather information from the environment.
Perceptions are subject to errors.

* **Percept**: raw information being gathered
* **Sensor**: the interface among the environment and the agent

An **action** is an operation by which agents affect the environment.
Actions may fail in so many ways.
The **actuator** is the interface among the agent and the environment.

Sensors and actuators are commonly coupled.

**Interactions** refers to the ability of an agent to be influences by other agents. It may involve both perception and actuation.

Interaction is different from **communication**.

-> Communication is direct (deliberate) exchange of information.

**Communication** refers to th exchange of messages to pass information among multiple agents.
The role of the receiver is important in communication: receiver agent may need to eventually handle the message. 
How the message is handled depends on the nature of the agent.

* Reactive agent (start a computation as soon as the message is received)
* Computationally-autonomous agent (memorizes the message and decides when/how to handle it)

### Autonomy of Agents

Agents are **autonomous** when they encapsulate the criterion by which they select which goal to pursue (motivational autonomy) or by which they choose which action to do while pursuing a goal (executive autonomy).

Agents are intelligent when they have cognitive capabilities and know when and how to use them to pursue their goals:

* Perceiving stimuli and recognize abstractions
* Representing knowledge
* Learning from the experience
* Memorizing for later re-use
* Planning courses of actions to pursue a goal
* Reasoning about knowledge
* Interact with other agents to exchange information

Having cognitive capabilities does not automatically lead to **intelligence** as machines are not provided with common sense.

### Representation

In-memory representation of the environment leveraging on some model, reified into some language, constructed on top of perception enabling complex deliberation.

*Can software agents learn from data?*

Agents who actually learn should:

* Have access to data
* Be autonomous in design decisions
* Have computational power

On the other hand, agents who exploits pre-trained models do not need access to data, they can use the model for perception without the need to take decisions or compute.

## Multi Agent System

Agents are the entities encapsulating behavior (intelligence).

**Concurrency**: agents are the entities encapsulating control flow (order according to which functions are executed within a program).
With **concurrent** programs, the machine simultaneously execute multiple processes.

Agents have **computational autonomy** as they have their own **control flow**.

With **distributed systems**, agents are the entities in charge of communicating ver the network.

**Simulation**: focus on behavior of simulated entities.

* Agents are the entities in the simulated world
* The agent is a simulated entity

### Agent Oriented Programming

Agents are active objects which encapsulate the control flow and communication.

```python
memory = dict()

while True:
    percepts = sense()
    memory = update(memory, percepts)
    action = deliberate(memory)
    act(action)
```

**Cognitive agents** focus on human-like capabilities and abstractions.

### BDI Agents

Cognitive aspects fitting the mental state of each agent:

* Belief (things that the agent think to know)
* Desires (goal that the agent is willing to pursue)
* Intentions (activities the agent is currently performing, possibly following some plan)
* Plans (procedural knowledge about how to pursue goals)

BDI Agents follows an **event-driven architecture** (relevant structure representing relevant happening).
New events may spawn intentions to execute plans (control flows controlling the agent's behavior).

### Control Loop of BDI Agents

1. Revise belief base with new messages and percepts
2. Add relevant events to the events stack
3. Pick next event from the event stack, if any
4. Prior intention -> select the intention
5. Future intention -> select a plan
6. Execute one step of the intention    

### Jason Syntax

```prolog
human(socrates) -> fact
mortal(X) :- human(X) -> rule

!reach(Destination) -> achievement
?discover(X) -> intention

Event : Guard <- Action1; ...;ActionN -> plan
```
