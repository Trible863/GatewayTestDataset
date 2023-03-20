# 区块链网关测试数据集
本研究团队在进行区块链网关的研究工作中发现目前尚没有用于区块链网关性能测试的数据集，为了顺利进行区块链网关的研究，本研究团队经过调研，发布了用于区块链网关性能测试代数据集，供有相关类似研究的人员用于网关性能测试。

Email: fengchunbo19@mails.ucas.ac.cn

----------------
### 数据来源
采用英特尔英特尔伯克利研究室（IBRL）传感器[数据集](http://db.csail.mit.edu/labdata/labdata.html)作为原始数据集，该数据集为IBRL在2004年使用54个传感器采集到的约230万条的感知数据。本文将原始数据按照设备编号分组并按时间顺序排序，采用移动平均数的方法归一化数据采样周期，并剔除数据量小于3万条的设备整合为[标准数据集](https://github.com/Trible863/GatewayTestDataset/blob/main/standardSensorData.rar)。

### 总体说明
本仓库主要包含[standardSensorData.rar](https://github.com/Trible863/GatewayTestDataset/blob/main/standardSensorData.rar)和[noiseSensorData.rar](https://github.com/Trible863/GatewayTestDataset/blob/main/standardSensorData.rar)两个压缩文件，standardSensorData.rar中的数据为正常的传感设备采集的感知数据，noiseSensorData.rar中的数据为添加了5%异常数据的感知数据，每个压缩文件中包含47个txt文件，每个txt文档表示一个传感器，每个文档中包含31744条数据，各个传感器的起始与终止时间相同。

### 噪声添加方式
根据[Sensor faults: Detection methods and prevalence in real-world datasets](https://dl.acm.org/doi/abs/10.1145/1754414.1754419)中提到的在时序数据中常见的异常包括提下三类：
* 恒定异常：对于大量连续的样本，传感器报告一个恒定的值。与“正常”传感器读数相比，报告的恒定值要么非常高，要么非常低，与潜在的物理现象无关。
* 突变异常：两个连续数据点之间的测量值发生了急剧变化。
* 噪声异常：传感器读数的差异增大，噪音故障会影响多个连续的样本。

本数据集在标准数据集的基础上按照5%的比重随机选取数据，按照上述三种异常添加了异常数据。
