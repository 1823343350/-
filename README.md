// -编译用的是Visual C++ 6.0
//暑假作业100题

//1。计算物体自由倾斜的距离：一个物体从高空自由落下。求它在t秒内对准的垂直距离，重力加速度为10m每平方秒。

#include "stdafx.h"

int main(int argc, char* argv[])
{
	int t,s;
	scanf("%d",&t);
	s=10*t*t/2;
	printf("时间:%d秒,下落距离:%d米\n",t,s);
	return 0;
}
// s=1/2*g*t*t,用的是整形数据，所以要把/2放在后面；

// 2
