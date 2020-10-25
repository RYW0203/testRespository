#include<stdio.h>

/*
定义两个全局数组,所有元素初始化为0
矩阵a为每一天的初始细菌矩阵,b为经过一天繁殖后的细菌矩阵
*/
int a[9][9] = { 0 };
int b[9][9] = { 0 };

void reProduct(int i, int j)   //定义繁殖函数
{
	int bacteriaNum = 0;
	bacteriaNum = a[i][j];
	
	//两倍的bacteriaNum留在原来的单元格
	b[i][j] += bacteriaNum * 2;

	//构建循环处理周边8个单元格
	for (int m = i - 1; m <= i + 1; m++)
	{
		for (int n = j - 1; n <= j + 1; n++)
		{
			//bacteriaNum = (bacteriaNum * 10 - bacteriaNum * 2) / 8;周边单元格细胞的增加量就是中心单元格前一天细菌数量
			b[m][n] += bacteriaNum;
		}
	}

	//上方的循环使得中心细菌数多增加了一个bacteriaNum,减去即可,也可将b[i][j] += bacteriaNum * 2;改为b[i][j] += bacteriaNum;,则省略此步骤
	b[i][j] -= bacteriaNum;
}

//将b矩阵的值赋给a,之后对b矩阵清零
void swapMat()
{
	for (int i = 0; i < 9; i++)
	{
		for (int j = 0; j < 9; j++)
		{
			a[i][j] = b[i][j];
			b[i][j] = 0;
		}
	}
}

//输出细菌矩阵
void outputMat()
{
	for (int i = 0; i < 9; i++)
	{
		for (int j = 0; j < 9; j++)
		{
			printf("%d\t", a[i][j]);
		}
		printf("\n\n");
	}
}


int main() {


	int num=0, day = 0;
	printf("Input:");
	scanf("%d %d", &num, &day);

	//设置初始矩阵中心单元格细菌数量
	a[4][4] = num;

	for (int d = 0; d < day; d++) 
	{
		//第一层循环遍历天数
		//内部i,j循环遍历矩阵
		for (int i = 0; i < 9; i++)
		{
			for (int j = 0; j < 9; j++)
			{
				if (a[i][j] != 0)   //处理所有非零元素,也就是计算每个单元格细胞一天的繁殖量，繁殖的结果保存在矩阵b中
				{
					reProduct(i, j);
				}
			}
		}

		/*
		处理完一天之后,矩阵b变成第二天的开始情况，下一轮循环应该以b为基础进行繁殖
		为了统一处理，将矩阵b“赋值”给a,原来的矩阵b所有元素清零,这样第二天的循环还是以a为初始细菌矩阵,b为经过一天繁殖后的矩阵
		*/
		swapMat();
	}
	
	//输出结果
	outputMat();

	return 0;
}



