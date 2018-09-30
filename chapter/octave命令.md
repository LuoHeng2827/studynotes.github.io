## octave常用命令
1. 基本的数学运算
```octave{.line-numbers}
3+4
5-1
4*4
6/2
2^6
```

2. 注释
%   
>

3. 变量
```octave{.line-numbers}
a=1 % 会自动显示赋值结果
a=1; % 抑制打印，不显示赋值结果
a % 打印变量
```

4. 逻辑运算
```octave{.line-numbers}
1==2 % 结果为0，表示为假
1~=2 % 结果为1，表示为真，其他高级语言一般用'!='
1 && 0 % 逻辑与运算，ans=0
1 || 0 % 逻辑或运算，ans=1
xor(1,0) % 异或运算，ans=1
```
5. 更改命令行提示符
```octave{.line-numbers}
PS1('>> ')
```

6. 复杂的屏幕输出
```octave{.line-numbers}
disp(a); % 打印a
disp(sprintf('2 decimals?: % 0.2f',a));% 打印a，保留两位小数
```

7. 控制长短格式的快捷命令
```octave{.line-numbers}
format long % long类型长度
format short % short类型长度，默认类型
```

8. 矩阵
```octave{.line-numbers}
A = [1 2; 3 4; 5 6] % 建立3*2的矩阵
A = [1 2 3] % 建立1*3的行向量
A = [1; 2; 3;] % 建立1=3*1的列向量
ones(2,3) % 生成元素都为1的2*3的矩阵
2*ones(2,3) % 生成元素都为2的2*3的矩阵
zeros(1,3) % 生成元素都为0的1*3的矩阵
rand(1,3) % 生成元素为随机值的1*3的矩阵，随机值介于0~1
randn(1,3) % 生成的1*3的矩阵，三个值组成一个平均值为0或者标准偏差为的高斯分布
eye(4) % 建立4*4单位矩阵
size(A) % 返回矩阵A的大小
size(A,1) % 返回矩阵A第一个纬度的大小
size(A,2) % 返回矩阵A第二个纬度的大小
length(A) % 返回矩阵A最大纬度的大小(一般用于向量)
A(2,:) % 打印A矩阵第2行所有元素
A([1 3], :) % 取A矩阵第一个索引值为1和3的所有元素
A(:,2)=[10; 11; 12] % 将新的列向量赋给矩阵的第2列
A=[A,[100;101;102]] % 给A附加一个新的列矩阵
A(:) % 将A的所有元素放入一个列向量
C=[A B] % 将矩阵A和B连在一起(左右排列)
C=[A, B] % 将矩阵A和B连在一起(左右排列)
C=[A; B] % 将矩阵A和B连在一起(上下排列)
```

9. 其他符号
```octave{.line-numbers}
1:0.1:2 % 得到从数值1开始，步长为0.1，直到增加到2的一组行向量
1:6 % 得到 1 2 3 4 5 6 这样的行向量
```

10. 绘制图形
```octave{.line-numbers}
hist(w) % 绘制w的直方图
hist(w,50) % 绘制50条w的直方图
plot(x,y) %  x向量为x轴取值，y向量为y轴取值
xlabel("xxx") % x轴名字
ylabel("xxx") % y轴名字
hold on % 将后续图叠加画在前一幅图，而不是覆盖
title("xxx") % 图的标题
legend("line1","line2") % 标记图中的每一条线的名字
print -dpng "xxx.png" % 保存成png格式的图片
close % 关闭图像
figure(1); plot(x,y) % 给图像编号，可以同时显示多个图案
subplot(m,n,i) % 将图像划分为m*n个格子。使用第i个作图
axis([-1 1 -1 1])调整轴坐标范围，x轴和y轴为-1到1
```

11. 帮助命令
```octave{.line-numbers}
help eye % 显示eye函数的帮助
```

12. 其他命令
```octave{.line-numbers}
pwd % 显示octave所在目录
ls % 列出所有路径 
cd xxx % 改变目录
load xx.dat % 加载文件
who % 显示工作空间的所有变量
whos % 显示工作空间的所有变量及详细信息
clear A % 清除变量A
v=price(1:10) % 将列向量price的前10个元素存入v中
save hello.mat v; % 将v存入到hello.mat文件
exit(quit) % 退出octave
```
11. 数据运算
```octave{.line-numbers}
A*C % 矩阵A和B相乘
A.*B % 将矩阵A中的每个元素与矩阵B相对应的元素相乘(.表示位运算)
A.^2 % 将矩阵A的每个元素进行平方
1./A % 将矩阵的每个元素进行倒数运算
log(A) % 对矩阵A每个元素求对数
exp(A) % 对矩阵每个元素进行以e为底元素为幂的运算
abs(A) % 对矩阵A每个元素求绝对值
-A % 对矩阵A的每个元素求相反数
A+1 % 矩阵A的每个元素+1
A' % 得到矩阵A的转置
max(rand(3),rand(3)) % 得到两个随机的3*3矩阵，逐元素比较取较大值，再返回新的矩阵
max(A) % 返回矩阵A每列最大的元素
max(A,[],1) % 返回矩阵A每列最大的元素
max(A,[],2) % 返回矩阵A每行最大的元素
max(max(A)) % 返回矩阵A最大元素
max(A(:)) % 返回矩阵A最大元素
[val,ind]=max(A) % 将向量A的最大值和索引存入val和ind
a<3 % 逐元素判断，若为真则为1
find(a<3> % 获得a中小于3的元素的索引)
magic(3) % 创建一个3*3的魔方阵
[r,c]=find(A>=7) % 找到矩阵A大于等于7的元素，r:=行的索引，c:=列的索引
sum(A) % 得到矩阵A所有元素的和
sum(A,1) % 得到矩阵A每列的和
sum(A,2) % 得到矩阵A每行的和
sum(sum(A.*eye(9))) % 得到矩阵A对角线的和，A是9*9矩阵
sum(sum(A.*flipud(eye(9))) % 得到矩阵A副对角线的和，A是9*9矩阵
prod(A) % 得到矩阵A所有元素的乘积
floor(A) % 将矩阵A所有的元素进行化整
flipud(A) % 将矩阵A上下翻转
prinv(A) % 对矩阵A求逆，若没有逆，求得则是伪逆矩阵
```

