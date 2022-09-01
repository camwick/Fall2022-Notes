# Intelligent Agents
[Back](../README.md)

**Quiz 1 due Sunday at midnight**

#### Agents
- anything that can be viewed as perceiving its environment through sensors and acting upon that environment through actuators
	- humans, robots, software agents, etc...

#### Sensor
- device acting as an input from physical environment
- cameras, motion senesors, temperature sensors, etc...

#### Environment
- part of the universe whose state we care about when designing the agent
- environments vary

#### Perception
- refers to the content an agent's sensors are perceiving
- percept sequence is the complete history of everything the agent has ever perceived

#### Action
- to do something with an aim of achieving a goal
- in class example: ROOMBA's goal is to clean the floor

#### Good Behavior: Rationality
- a rational agent does the correct thing (action)

#### Ombiscience != Rationality != Perfection
- omniscience is not possible in a real life scneario
- rationality is not the same as perfection
- rationality maximizes expected performance, while perfection maximizes actual performance

#### PEASE  - Vacuum cleaner robot
- Performance: cleanness, efficiency: distance traveled to clean, battery life, security
- Environment: room, table, wood floor, carpet different obstacles
- Actuators: wheels, different brushes, vacuum extractor, dirt disposal tube
- Sensors: camera, dirt detection sensor, bump sesnors, infrared wall sensors

## Types of Agents
- four basic types in order of increasing generality:
	- simple reflex agents
	- model-based reflex agents
	- goal-based agents
	- utility-based agents
- all can be generalized into learning agents that can improve their performance and generate better actions

### Simple reflex agent
- select an actino based on the current state only ignoring the percept history
- simple but limited
- only works if the environment is fully observable
	- correct action based on the current percept only

### Model-based reflex agents
- handle partial observability by keeping track of the part of the world it can't see now
- internal state depending on the percept history (best guess)
- model of the world based on:
	- how the world evolves independently 

### Learning Agent
- four conceptual components:
	- learning element: responsible for making improvements
	- performance element: responsible for selecting external actions
	- critic: how well is the agent doing w.r.t. a fixed perfomance standard
	- problem generator: allows the agent to explore


### Goal-based Agent
- combines the goal information with the environment model to choose the actions that achieve that goal
- flixible as knowledge supporting the decisions is explicitly represented and can be modifed

### Utility-based Agent
- occasionaly, achieving the goal is not enough
- we may want a quicker, safer, or cheaper trip to reach a destination
- agent happiness should be taken into consideration -- utitlity
- utitly function - agent's performance measure
	- uncertainty causes a utility agent to chose the action that maximizes the expected utility