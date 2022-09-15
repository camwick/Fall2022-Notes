# Intelligent Agents 3
[Back](../README.md)

### Simple Reflex Agent
- selects an action based on the current state
	- ignores the percept history
- simple but limited
	- can only work if the environment is fully observable

### Model-based reflex agents
- internal state depending on the percept history
- model of the world based on 
	- how the world evolves independently
	- how the agent actions affect the world

### Goal Based Agents
- knowing the current state of the environment is not enough
	- agent needs goal information
- combines goal information with the environment model to choose the actions that achieve that goal
- flexible as knowledge supporting the decisions is explicitly represented and can be modified

### Utility-based agents
- sometimes achieving the desired goal is not enough
	- may look for a quicker, safer, and or cheaper trip to reach a destination
- agent happiness may be taken into consideration
- utility function is the performance measure

## Goal-Based Agents Stuff
### Problem Solving Agents
- uses atomic representations that is, states of the world are considered as wholes, with no internal structure visible to the problem-solving algorithms

### Goal Formulation
- need to maximize their performance measure
- goals help organize behavior by limiting the objectives that the agent is trying to achieve and hence the actions it needs GOAL FORMULATION to consider
- goal formulation is the first step in problem solving
	- set of world states
	- task is to find out how to act, now and in the future, so that it reaches a goal state

### Problem Formulation
- the process of deciding what actions and states to consider, given a goal
- if no additional information
	- then it has no choice but to try one of the actions at random
- in general, an agent that has several options will decide what to do by examining future actions that would lead to states of known value
- we assume
	- environment is observable
		- agent always knows the current state
	- environment is discrete
		- only finite amount of options
	- environment is known
		- agent knows which states are reached by each action
	- environment is deterministic
		- each action has exactly 1 outcome
- five components:
	- initial state - state agent starts in
	- action(S) - set of actions that can be executed in s
	- transition model - description of what each action does
		- specified by a function results
		- result(s, a) - returns the state that results from successor
		- successor - refers to any state reachable from a given state by a single action
	- result - 
	- state space - initial state, actions, and transition model 
	- graph of actions
