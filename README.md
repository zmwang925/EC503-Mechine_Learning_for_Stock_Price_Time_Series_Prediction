# EC503-Project


## Data source

 - Tradingphysics
  
 - JoinQuant

## Data preprocessing

### Select Candidate factors
#### Kernel PCA
- Algorithm
  - Outline
  1. 取某一天某一个时间点的N支股票的d个因子（d x N)
  2. 使用Kernel PCA提取其中k个影响最大的因子（elbow method）
  - Kernel selection
  1. Linear Kernel
  2. Polynomial Kernel
  3. Gaussian Kernel
- Evaluation

  <img width="740" alt="Screen Shot 2021-11-08 at 5 40 58 PM" src="https://user-images.githubusercontent.com/90360797/140829626-3ae21d55-9340-4173-9e57-5bd5d0848b9a.png">
- Output
  N支股票的K个因子
  K x N的矩阵
  
### Fitting monthly rate of return:
#### Ridge Regression


#### LASSO Regression


#### Elastic Net


#### Performance Evaluation
对比三个方法的MSE，比较并分析，选择MSE最小的算法进行下一步。

### Optimize profolio proportions
#### Q Learning 





				
					
