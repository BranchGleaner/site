<script>
    locker("rnkyclzd");
</script>
# 11.15作业

## 免责声明及警告

以下代码仅作参考，不保证准确性、鲁棒性或最优性，也没有任何人应当或可能为此负责。公布代码仅用于相互交流、讨论或学习，不得用于任何违法、违规或违纪之用途；违者自行承担全部责任和损失，自行为自己的前途负责。

代码尽力为所有题目提供容易被理解的解答。若有疏漏之处或其它意见，欢迎讨论。

## 一

### 代码设计

```c
#include <stdio.h>

void split_time(long total_sec,int *hr,int *min,int *sec)
{
	*hr=total_sec/3600;
	*min=(total_sec-*hr*3600)/60;
	*sec=total_sec-*hr*3600-*min*60;
}

int main()
{
	long n=0;
	int oa=0,ob=0,oc=0;
	int *a=&oa;
	int *b=&ob;
	int *c=&oc;
	printf("Enter the number of seconds since midnight:");
	scanf("%ld",&n);
	split_time(n,a,b,c);
	printf("Since midnight, %d hours, %d minutes and %d seconds have elapsed.",*a,*b,*c);
	return 0;
}
```

### 运行展示

> **应该不会有人连运行展示都照搬吧，不会吧不会吧/(ㄒoㄒ)/~~**

#### 示例Ⅰ

```
Enter the number of seconds since midnight:5294
Since midnight, 1 hours, 28 minutes and 14 seconds have elapsed.
```

#### 示例Ⅱ

```
Enter the number of seconds since midnight:65946
Since midnight, 18 hours, 19 minutes and 6 seconds have elapsed.
```

#### 示例Ⅲ

```
Enter the number of seconds since midnight:49520
Since midnight, 13 hours, 45 minutes and 20 seconds have elapsed.
```

## 二

### 代码设计

```c
#include <stdio.h>

int isspe(int n)
{
	if((n%4==0&&n%100!=0)||n%400==0)
	{
		return 1;
	}
	return 0;
}

void split_date(int day_of_year,int year,int *month,int *day)
{
	if(isspe(year)==0)
	{
		if(1<=day_of_year&&day_of_year<=31)
		{
			*month=1;
			*day=day_of_year;
			return;
		}
		if(32<=day_of_year&&day_of_year<=59)
		{
			*month=2;
			*day=day_of_year-31;
			return;
		}
		if(60<=day_of_year&&day_of_year<=90)
		{
			*month=3;
			*day=day_of_year-59;
			return;
		}
		if(91<=day_of_year&&day_of_year<=120)
		{
			*month=4;
			*day=day_of_year-90;
			return;
		}
		if(121<=day_of_year&&day_of_year<=151)
		{
			*month=5;
			*day=day_of_year-120;
			return;
		}
		if(152<=day_of_year&&day_of_year<=181)
		{
			*month=6;
			*day=day_of_year-151;
			return;
		}
		if(182<=day_of_year&&day_of_year<=212)
		{
			*month=7;
			*day=day_of_year-181;
			return;
		}
		if(213<=day_of_year&&day_of_year<=243)
		{
			*month=8;
			*day=day_of_year-212;
			return;
		}
		if(244<=day_of_year&&day_of_year<=273)
		{
			*month=9;
			*day=day_of_year-243;
			return;
		}
		if(274<=day_of_year&&day_of_year<=304)
		{
			*month=10;
			*day=day_of_year-273;
			return;
		}
		if(305<=day_of_year&&day_of_year<=334)
		{
			*month=11;
			*day=day_of_year-304;
			return;
		}
		if(335<=day_of_year&&day_of_year<=365)
		{
			*month=12;
			*day=day_of_year-334;
			return;
		}
	}
	else
	{
		day_of_year=day_of_year-1;
		if(0<=day_of_year&&day_of_year<=30)
		{
			*month=1;
			*day=day_of_year+1;
			return;
		}
		if(31<=day_of_year&&day_of_year<=59)
		{
			*month=2;
			*day=day_of_year-30;
			return;
		}
		if(60<=day_of_year&&day_of_year<=90)
		{
			*month=3;
			*day=day_of_year-59;
			return;
		}
		if(91<=day_of_year&&day_of_year<=120)
		{
			*month=4;
			*day=day_of_year-90;
			return;
		}
		if(121<=day_of_year&&day_of_year<=151)
		{
			*month=5;
			*day=day_of_year-120;
			return;
		}
		if(152<=day_of_year&&day_of_year<=181)
		{
			*month=6;
			*day=day_of_year-151;
			return;
		}
		if(182<=day_of_year&&day_of_year<=212)
		{
			*month=7;
			*day=day_of_year-181;
			return;
		}
		if(213<=day_of_year&&day_of_year<=243)
		{
			*month=8;
			*day=day_of_year-212;
			return;
		}
		if(244<=day_of_year&&day_of_year<=273)
		{
			*month=9;
			*day=day_of_year-243;
			return;
		}
		if(274<=day_of_year&&day_of_year<=304)
		{
			*month=10;
			*day=day_of_year-273;
			return;
		}
		if(305<=day_of_year&&day_of_year<=334)
		{
			*month=11;
			*day=day_of_year-304;
			return;
		}
		if(335<=day_of_year&&day_of_year<=365)
		{
			*month=12;
			*day=day_of_year-334;
			return;
		}
	}
}

int main()
{
	int n=0,y=0;
	int oa=0,ob=0;
	int *a=&oa;
	int *b=&ob;
	printf("Enter the specified year:");
	scanf("%d",&y);
	printf("Enter the specified date:");
	scanf("%d",&n);
	split_date(n,y,a,b);
	printf("The %dth day of year %d is the %dth month and %dth day.",n,y,*a,*b);
	return 0;
}
```

### 运行展示

#### 示例Ⅰ

```
Enter the specified year:2022
Enter the specified date:42
The 42th day of year 2022 is the 2th month and 11th day.
```

#### 示例Ⅱ

```
Enter the specified year:1500
Enter the specified date:196
The 196th day of year 1500 is the 7th month and 15th day.
```

#### 示例Ⅲ

```
Enter the specified year:2024
Enter the specified date:366
The 366th day of year 2024 is the 12th month and 31th day.
```
