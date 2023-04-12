# OpenAI Gym wrapper for the DeepMind Control Suite (Updated)

A lightweight wrapper around the DeepMind Control Suite that provides the standard OpenAI Gym interface. This updated version is compatible with gym>0.23.0 and has been modified to address incompatibility issues with newer gym versions. The wrapper allows you to:

* Ensure deterministic behavior with reliable random seed initialization.
* Convert proprioceptive observations into image-based observations by setting `from_pixels=True`. Additionally, you can choose the image dimensions by setting `height` and `width`.
* Normalize the action space to bound each action's coordinate within the `[-1, 1]` range.
* Perform action repeat by setting the `frame_skip` argument.

## Installation

```bash
pip install git+git://github.com/ItsBean/dmc2gym.git
```

## Usage

```python
import dmc2gym

env = dmc2gym.make(domain_name='point_mass', task_name='easy', seed=1)

done = False
obs = env.reset()
while not done:
  action = env.action_space.sample()
  obs, reward, done, info = env.step(action)
```


This updated introduction reflects the changes to the repository, including compatibility with the new gym version and the new GitHub repository owner.
