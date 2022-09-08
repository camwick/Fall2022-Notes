# Intelligent Agents 2
[Back](../README.md)

Quiz 2 was posted, due September 11  at 11:59

## Fully Observable Environment
- definition: an agent's sensors give it access to the complete state of the environment at each point in time
- convenient because an agent wouldn't need to keep record of it's state

### Partially observable environment
- an environment can be partially observable when parts of the state are missing from the sensor data

### Single-Agent Environment
- the environment has only one agent
	- ex. vacuum cleaner

### Multi-Agent Environment
- involves multiple agents
	- ex. chess, robots in a warehouse, self driving cars

### Competitive Environment
- agent trying to maximize their own performance while minimizing performance of another agent
- always multi-agent environment
- behavior could be competitive, but sometimes considered rational
	- ex. chess

### Cooperative Environment
- agents help each to succeed
- usually considered rational actions
- ex. cars on the road

### Deterministic Environment
- environment is completely determined by the current state and the action executed by the agent(s)
- always fully observable and lesser to no chances of uncertainties
	- ex. vacuum cleaner

### Non-Deterministic Environment
- environment **is not** completely determined by the current state and the action executed by the agent(s)
- usually partially observable and filled with uncertainties
	- ex. cars
- real world scenarios are mostly non-deterministic due to complexities involved
- if possibilities listed are quantified, we call them _stochastic_

### Episodic Environment
prof went past the slide...

### Sequential Environment
- current decision could affect all future decisions
- more complex than episodic
	- ex. chess, cars

### Static Environment
- environment doesn't change with time
	- ex. crossword puzzles
- easy to deal with because environment does not change when the agent is deciding on an action, nor need it worry about time
- performance measure can change with time

### Dynamic Environment
- changes with time and the agent needs to act on it
	- ex. cars, chess
- performance score can change 

### Known Environment
- can be partially observable
	- solitaire
		- known rules but still unable to see the cards that have not yet been turned over

### Known Unknown Environment
- environment may be fully observable but unknown
	- ex. player learning chess

### The hardest Problem
- case where the environment is partially observable, multi-agent, nondeterministic, sequential, dynamic, continuous, and unkown
	- ex. autonomous driving

### Example from class
- amazon alexa
	- partially observable
	- stochastic
	- sequential
	- dynamic
	- continuous
	- multi-agent
	- unknown
	- cooperative (can be competitive based on scenario)
