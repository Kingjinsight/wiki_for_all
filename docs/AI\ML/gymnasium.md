# Gymnasium

It is the new version of Gym library.

## Basic

It provides two things:

- An interface that allows you to create RL environments
- A collection of environments(gym-control, atari,box2D...)

With Gymnasium:

1. Create our environment using: `gymnasium.make()`
2. reset the environment to its initial state with `observation = env.reset()`

At each step:

3. Get an action using our model
4. Using `env.step(action)`, we perform this acton in the environment and get
      - **observation**: The new state
      - **reward**: The reward
      - **terminated**: Indicates if the episode terminated
      - **truncated**: Indicates a timelimit or if an agent go out of bounds of the environment for instance
      - **info**: A dictionary that provides additional information(depend on the environment)

If the episode is terminated:

- we reset the environment to its initial state
