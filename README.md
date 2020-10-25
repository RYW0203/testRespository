# testRespository
在边长为9的正方形培养皿中，正中间位置有m个细菌，假设细菌寿命仅一天，
但每天可繁殖10个后代，而且这个后代，有两个分布在原来的单元格中，其
余的均匀分布在其四周相邻的8个单元格中，
求经过n(1<=n<=4)天后，细菌在培养皿中的分布情况。
输入：
    两个整数，第一个整数m表示中心位置细菌的个数(2<=m<=30),第二个整
    数n表示经过的天数(1<=n<=4)。
输出：
    输出9*9整数矩阵，每行整数之间用空格分隔，整个矩阵代表n天后细菌
    在培养皿上的分布情况。
Sample:
Input:
      2  1
Output:
    000000000
    000000000
    000000000
    000222000
    000242000
    000222000
    000000000
    000000000
    000000000
    
