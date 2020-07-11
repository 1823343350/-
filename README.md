  编译用的是Visual C++ 6.0
  暑假作业100题

1.欧几里得算法求最大公约数
2.筛法求素数
3.康托展开
4.逆康托展开
5.同余定理
6.高次方求模
7.三角形面积（海伦公式）
8.三点顺序
9-28（一维数组和二维数组）
29-48（单链表和双链表）
49-68（二分查找法，排序）
69-78（字符串，常用算法，KMP算法等）
79-98（基本算法）
剩余（图论，计算几何）

1.
#include "stdafx.h"

int main(int argc, char* argv[])
{
	
	int a,b,c,t,z;

	scanf("%d%d",&a,&b);
	z=b;
	if(b>a)
	{
		c=a,a=b,b=c;
		z=b;
	}

	for(c=a%b;c!=0;)
	{
		if(c>b)
		{
			c=c%b;
		}
		else
		{
			t=c;
			c=b%c;
			b=t;
		}
	};
		
	printf("%d和%d最大公约数%d\n",a,z,b);
	return 0;
}

2.1 普通算法求n以内的素数

#include "stdafx.h"

int main(int argc, char* argv[])
{

	int a[10000],n,i,k,s;

	scanf("%d",&n);

	for(i=1;i<=n;i++)
		a[i]=i;
		
	a[1]=0;
	
	for(i=2;i<=n;i++)
	{
		s=1;
		
		for(k=2;s!=0;k++)
		s=a[i]%k;
		
		if(k<a[i])
		a[i]=0;
	}

	for(i=1;i<=n;i++)
		if(a[i]!=0)
			printf("%d ",a[i]);
	return 0;
}

2.2 
筛法求素数

#include "stdafx.h"

int main(int argc, char* argv[])
{

	int a[1000],b[1000];

	int i,k,n,s;

	scanf("%d",&n);

	for(i=1;i<=n;i++)
	{
		a[i]=i;
		b[i]=i;
	}

	b[1]=0;

	for(i=2;i<=n;i++)
	for(k=i+1;k<=n;k++)
		{
			s=a[k]%i;
			if(s==0)
				b[k]=0;
		}

	for(i=1;i<=n;i++)
		if(b[i]!=0)
		printf("%d ",b[i]);


	return 0;
} 从1到n，第一个质数是2，然后将n中所有2的倍数删掉，依次将n中所有3的倍数，4的倍数。。。全部删掉，剩下来的就是n以内的素数，缺点是有些数重复删除了。

