
题目：

n(n<20)个人站成一圈，逆时针编号为1～n。有两个官员，A从1开始逆时针数，B从n开始顺时针数。在每一轮中，官员A数k个就停下来，官员B数m个就停下来（注意有可能两个官员停在同一个人上）。接下来被官员选中的人（1个或者2个）离开队伍。

输入n，k，m输出每轮里被选中的人的编号（如果有两个人，先输出被A选中的）。例如，n=10，k=4，m=3，输出为4 8, 9 5, 3 1, 2 6, 10, 7。注意：输出的每个数应当恰好占3列。

输入： 
10 4 3

输出： 
_ _ 4_ _ 8,_ _ 9_ _ 5,_ _ 3_ _ 1,_ _ 2_ _ 6,_ 10,_ _ 7


代码：
#include<stdio.h>
#include<stdlib.h>
#define maxn 25
int a[maxn];
int n, k, m;

//逆时针走t步，步长是d（-1表示逆时针走），返回新位置
int findKM(int p,int d,int target){
	while (target--){
		do{
			p = (p + d + n - 1) % n + 1;
		} while (a[p] == 0); //走到下一个非0数字
	}
	return p;
}
int main(){
	int start, pB, pA;
	while (scanf("%d %d %d", &n, &k, &m) == 3 && n){
		for (int i = 1; i <= n; i++){
			a[i] = i;
		}
		start = n, pB = n, pA = 1; //剩余人数
		while (start){
			pB = findKM(pB, 1, k); //顺时针k
			pA = findKM(pA, -1, m); //逆时针m
			if (pB != pA){
				printf("%3d%3d", pB, pA);
				start = start - 2;
			}
			else{
				printf("%3d", pB);
				start--;
			}
			a[pB] = a[pA] = 0; //离开队伍的人位置为0
			if (start){
				printf(",");
			}
		}
		printf("\n");
	}
	return 0;
}
