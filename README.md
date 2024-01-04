# multi-robot-searching
修改自[pomdp-py](https://github.com/h2r/pomdp-py)，使用面向对象的POMDP（OOPOMDP）进行建模，使用POUCT进行求解  
## 代码架构：  
```
|-- README.md
|-- __init__.py
|-- __pycache__
|   |-- __init__.cpython-38.pyc
|   `-- example_worlds.cpython-38.pyc
|-- agent
|   |-- __init__.py
|   |-- __pycache__
|   |   |-- __init__.cpython-38.pyc
|   |   |-- agent.cpython-38.pyc
|   |   `-- belief.cpython-38.pyc
|   |-- agent.py
|   `-- belief.py
|-- domain
|   |-- __init__.py
|   |-- __pycache__
|   |   |-- __init__.cpython-38.pyc
|   |   |-- action.cpython-38.pyc
|   |   |-- observation.cpython-38.pyc
|   |   `-- state.cpython-38.pyc
|   |-- action.py
|   |-- observation.py
|   `-- state.py
|-- env
|   |-- __init__.py
|   |-- __pycache__
|   |   |-- __init__.cpython-38.pyc
|   |   |-- env.cpython-38.pyc
|   |   `-- visual.cpython-38.pyc
|   |-- env.py
|   `-- visual.py
|-- example_worlds.py
|-- models
|   |-- __init__.py
|   |-- __pycache__
|   |   |-- __init__.cpython-38.pyc
|   |   |-- observation_model.cpython-38.pyc
|   |   |-- policy_model.cpython-38.pyc
|   |   |-- reward_model.cpython-38.pyc
|   |   `-- transition_model.cpython-38.pyc
|   |-- components
|   |   |-- __init__.py
|   |   |-- __pycache__
|   |   |   |-- __init__.cpython-38.pyc
|   |   |   |-- grid_map.cpython-38.pyc
|   |   |   `-- sensor.cpython-38.pyc
|   |   |-- grid_map.py
|   |   `-- sensor.py
|   |-- observation_model.py
|   |-- policy_model.py
|   |-- reward_model.py
|   `-- transition_model.py
|-- problem.py
```
## 代码功能
### problem.py
主程序，包含POMDP问题定义、求解器定义、求解等

### example_worlds.py
生成地图

### agent
#### agent.py
定义`MosAgent`，包含信念地图、状态转移函数、观测函数、奖励模型、策略模型的实例化
#### belief.py
定义直方图信念和粒子群信念，分别用于POUCT和POMCP求解器

### domain
#### action.py
定义各种动作
#### observation.py
定义观测的函数方法
#### state.py
定义状态的函数方法

### env
#### env.py
定义`MosEnvironment`，根据动作给出奖励值
#### visual.py
定义可视化相关

### models
定义状态转移函数、观测模型函数、奖励模型、策略模型、传感器模型、地图模型