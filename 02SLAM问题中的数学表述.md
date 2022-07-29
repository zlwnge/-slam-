## SLAM问题中的数学表述

时间t离散为t=1,$\cdots$,K。机器人位置为x，则各时刻的位置就为$x_1$,$\cdots$,$x_K$。

运动方程: 

$$ x_k=f\left(x_{k-1}, u_k, w_k\right) \tag {2.1} $$

其中，$u_k$是运动传感器的读数，$w_k$是过程中加入的噪声

观测方程：

$$ z_{k,j}=h\left(y_j, x_k, v_{k,j}\right) \tag {2.2} $$

该方程表述的是机器人在$x_k$位置上看到某个路标点$y_j$时，产生了一个观测数据$z_{k,j}$。$v_{k,j}$是这次观测里的噪声
![image](https://user-images.githubusercontent.com/34792225/181718080-a5d07992-b214-4317-98ac-3ec76948f2a8.png)

这两个方程描述了最基本的slam问题：当知道运动测量的读数u，以及传感器读数z时，如何求解定位问题（估计x）和建图问题（估计y）？

这时，我们就把slam问题建模成了一个<b>状态估计问题</b>：如何通过带有噪声的测量数据，估计内部的、隐藏着的状态变量？

状态估计问题的求解与两个方程的具体形式，及噪声服从哪种分布有关。

> 线性系统、非线性系统、高斯系统、非高斯系统

线性高斯系统 --> Kalman Filter(KF)
非线性非高斯系统 --> Extended Kalman Filter(EKF)和非线性优化 --> 粒子滤波(Particle Filter) --> 图优化(Graph Optimization)

