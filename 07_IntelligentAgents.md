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