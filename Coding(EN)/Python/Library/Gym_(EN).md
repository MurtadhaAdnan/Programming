# Gymnasium Functions by Expertise Level

## `Introduction`
**Gymnasium** (formerly known as Gym) is a library for developing and comparing reinforcement learning algorithms:

- ✅ Provides standardized environments for testing
- ✅ Supports a wide range of tasks
- ✅ Integrates with major ML frameworks

## `Core Benefits`

| Feature | Explanation |
|---------|-------------|
| ⚡ Diverse Environments | 100+ ready-to-use environments |
| 🧠 Unified Interface | Simple and consistent API for all environments |
| 📊 Visualization Support | Visual display of training results |

---
<br><br><br>

## `Beginner Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `gymnasium.make(id)` | Create environment | `env = gymnasium.make('CartPole-v1')` | Environment object |
| `env.reset()` | Reset environment | `observation = env.reset()` | Initial state |
| `env.step(action)` | Take an action | `observation, reward, done, info = env.step(action)` | Action results |
| `env.render()` | Render environment | `env.render()` | Display window |
| `env.action_space` | Action space | `print(env.action_space)` | Possible actions info |
| `env.observation_space` | Observation space | `print(env.observation_space)` | State information |
| `env.close()` | Close environment | `env.close()` | Release resources |
| `env.seed()` | Set seed | `env.seed(42)` | Reproducible results |
| `gymnasium.__version__` | Library version | `print(gymnasium.__version__)` | Version number |
| `env.spec` | Environment specs | `print(env.spec)` | Environment info |

---
<br><br><br>

## `Intermediate Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| `Wrappers` | Modify environments | `env = TimeLimit(env, max_episode_steps=100)` | Modified environment |
| `VectorEnv` | Parallel envs | `envs = gymnasium.vector.make('CartPole-v1', num_envs=4)` | Multiple environments |
| `env.step()` with vector | Parallel steps | `observations, rewards, dones, infos = envs.step(actions)` | Multiple steps |
| `RecordVideo` | Record video | `env = RecordVideo(env, 'videos')` | Session recordings |
| `Monitor` | Log results | `env = Monitor(env, 'results')` | Statistics logging |
| `env.get_action_meanings()` | Action meanings | `print(env.get_action_meanings())` | Action interpretations |
| `env.unwrapped` | Access base env | `base_env = env.unwrapped` | Unwrapped environment |
| `env.reward_range` | Reward range | `print(env.reward_range)` | Min/max reward |
| `env.metadata` | Metadata | `print(env.metadata)` | Additional info |
| `env.configure()` | Configure env | `env.configure(remotes=1)` | Change settings |

---
<br><br><br>

## `Advanced Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| Custom `Env` class | Create custom env | `class MyEnv(gymnasium.Env): ...` | New environment |
| Custom `Space` | Define custom space | `class MySpace(gymnasium.Space): ...` | New space |
| `register()` | Register envs | `gymnasium.register(id='MyEnv-v0', entry_point='myenv:MyEnv')` | Registered env |
| `AsyncVectorEnv` | Async envs | `envs = AsyncVectorEnv([make_env])` | Parallel envs |
| Custom `Wrapper` | Create custom wrapper | `class MyWrapper(gymnasium.Wrapper): ...` | Modified behavior |
| `env.physics` | Physics engine | `print(env.physics)` | Access engine |
| `env.model` | Environment model | `print(env.model)` | Environment structure |
| `env.sim` | Environment sim | `print(env.sim)` | Simulation state |
| `env.render(mode='rgb_array')` | Image output | `img = env.render(mode='rgb_array')` | Pixel array |
| `env.compute_reward()` | Custom reward | `reward = env.compute_reward(achieved_goal, desired_goal)` | Custom reward |

---
<br><br><br>

## `Expert Level`

| Function | Description | Example | Output |
|----------|-------------|---------|--------|
| Custom `VectorEnv` | Custom parallel envs | `class MyVectorEnv(gymnasium.vector.VectorEnv): ...` | Parallel implementation |
| `env.get_attr()` | Get attributes | `values = env.get_attr('attribute')` | Read properties |
| `env.set_attr()` | Set attributes | `env.set_attr('attribute', value)` | Modify properties |
| `env.call()` | Call function | `results = env.call('method', *args)` | Execute methods |
| `env.env_method()` | Call env method | `results = env.env_method('method', *args)` | Execute on envs |
| `env.close_extras()` | Extra cleanup | `env.close_extras()` | Release extra resources |
| `env.observation()` | Transform obs | `obs = env.observation(obs)` | Process observation |
| `env.action()` | Transform action | `action = env.action(action)` | Process action |
| `env.reward()` | Transform reward | `reward = env.reward(reward)` | Process reward |
| `env.info()` | Transform info | `info = env.info(info)` | Process information |