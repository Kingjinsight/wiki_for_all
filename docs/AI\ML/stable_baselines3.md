# Stable Baselines3

## Basic usage

1. **Create environment**: gym.make() / make_vec_env()
2. **Define the model, instantiate this model**: `model = PPO("MlpPolicy)`
3. **Train the agent by define the traning timesteps**: `model.learn(total_timesteps=int(n))`
4. **Wrap the environment in a Monitor**: `eval_env = Monitor(env)`
5. **Evaluate policy**: `evaluate_policy(model, eval_env, m_eval_episodes, deterministics)`

## Functions

### Training

- `make_vec_env("EnvName", n_envs=n)`: Create a vectorized environment of n environment, a method for stacking multiple independent environment into a single environment.
- `model.save("filename")`: Specify file name for model and save the model to file


### Evaluation

- `evaluate_policy(model, env, n_eval_episodes, deterministics)`: Run the policy foe n_eval_episodes and outputs the average return per episode.
    - deterministics: Whether to use deterministic or stochastic actions
- `Monitor`: It is used to know the episode reward, length, time and other data

### Load model

- `methods.load(checkpoint, custom_objects=custome_objects, print_system_info=True)`: models from huggingface hub
    - checkpoint: `huggingface_sb3.load_from_hub()`
    - custom_objects: Dictionary of objects to replace upon loading, such as learning rate
