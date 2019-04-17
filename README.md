# robot_pose_ekf_study
对ros下的robot_pose_ekf包源码依照个人理解添加注释

建立线性模型时 传入的参数为变换矩阵和噪声的期望与方差
建立非线性模型时 传入的参数为噪声的期望与方差

  要重写期望获得函数和雅可比矩阵计算函数
  该期望获得函数即是扩展卡尔曼计算公式中计算时间更新中的X值的公式



在进行扩展卡尔曼滤波时
先对系统模型进行更新 即filter_->update(sysmodel_, u) u即为控制量
然后再对测量模型进行更新 即filter_->update(meansmodel_, z) z即为观察值

每个传感器数据进行卡尔曼滤波的顺序为 odom->imu->vo->gps
