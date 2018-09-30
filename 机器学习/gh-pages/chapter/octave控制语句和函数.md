## 控制语句
```octave{.line-numbers}
for i=1:10,...;end; % 让i等于1到10
while i<=5,...;end; % while语句
if i==6,...; % if语句
else ...;end; % else语句
elseif i==1 % elseif语句
```
##函数
###定义函数
1. 创建文件(函数名.m)squareThisNumber.m
2. 编辑文件，编写函数定义
```octave{.line-numbers}
function [y1,y2] = squareThisNumber(x)
y1=x^2;
y2=x^2;
```
3. * 在当前路径(pwd查看)直接可调用
   * 利用Octave的搜索路径调用
```octave{.line-numbers}
% Octave Search path
addpath('squareThisNumber.m所在路径')
```

###向量化
$h_\theta(x)=\sum_{i=0}^{n} \theta_jx_i=\theta^Tx$
>未向量化的代码实现方法
```c++{.line-numbers}
double prediction=0.0
for(int i=0;i<n;i++)
    prediction+=theta[j]*x[j];
```
> 向量化的代码实现方法
```c++{.line-numbers}
double prediction=theta.transpose()*x;
```
> 向量化的优点：快速，高效，简洁。