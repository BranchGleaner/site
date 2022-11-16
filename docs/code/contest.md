<script>
    locker("contest_solution");
</script>


# 比赛题解

## 免责声明及警告

以下代码仅作参考，不保证准确性、鲁棒性或最优性，也没有任何人应当或可能为此负责。公布代码仅用于相互交流、讨论或学习，不得用于一切违法、违规或违纪之用途；违者自行承担全部责任和损失，自行为自己的前途负责。

代码尽力为所有题目提供容易被理解的解答。若有疏漏之处或其它意见，欢迎讨论。

## 一　红叶荒波一相逢

```c
#include <stdio.h>
#include <math.h>
#include <stdlib.h>
#include <time.h>
#include <ctype.h>


int made[499501];
int org[1000];
int count=0,num=0;
long long int add=0,ans=0,madeans=0;

void make()
{
    int i=0,j=0,f=1;
    long long int zh=0;
    int t;
    madeans=0;
    count=num;
    for(i=0;i<num;i++)
    {
        scanf("%d",&org[i]);
    }
    for(i=0;i<num-1;i++)//生成
    {
        for(j=i+1;j<num;j++)
        {
            zh=((long long int)org[i]+(long long int)org[j])/2;
            //printf("zh=%lld\n",zh);
            made[count]=(int)zh;
            count++;
        }
    }
    for(i=0;i<num;i++)//转移
    {
        made[i]=org[i];
    }
    for(i=0;i<count-1;i++)//排序
    {
        f=1;
        for(j=0;j<count-i-1;j++)
        {
            if(made[j]>made[j+1])
            {
                t=made[j];
                made[j]=made[j+1];
                made[j+1]=t;
                f=0;
            }
        }
        if(1==f)
        {
            break;
        }
    }
    for(i=0;i<count;i++)
    {
        if(i%2==0)
        {
            madeans=madeans+made[i];
        }
        else
        {
            madeans=madeans-made[i];
        }
    }
    printf("%lld",madeans);
}

void solve()
{
    add=0;
    ans=0;
    int i=0;
    count=num;
    for(i=0;i<count;i++)
    {
        scanf("%d",&made[i]);
        add=add+made[i];
    }
    for(i=0;i<count;i++)
    {
        if((i*i+i)/2==count)
        {
            break;
        }
    }
    ans=(long long int)(add*2)/(long long int)(i+1);
    printf("%lld",ans);
}

int main()
{
	int j=1,i=1;
    int type=1;
	scanf("%d %d",&type,&num);
    if(type==1)
    {
        make();
    }
    else
    {
        solve();
    }
    return 0;
}
```

## 二　盘山纡水尽为开

```c
#include <stdio.h>

int main()
{
    unsigned long long int a=2,b=6,c=0;
    int k=0;
    scanf("%d",&k);
    if(k==1)
    {
        printf("2");
    }
    for(int i=3;i <= k+1;i++)
    {
        c=2*b+a;
        a=b;
        b=c;
        if(i==k+1)
        {
            printf("%llu",(a+b-4)/2);
        }
    }
}
```

## 三　天命既定的纠缠

```c
#include <stdio.h>
#include <math.h>

double a=0,b=0,c=0,d=0;

double count(double x)
{
    return a*x*x*x+b*x*x+c*x+d;
}

int main()
{
    double a1,a2,a3,a4,b1,b2,b3,b4;
    double ans=-100.000000;
    double read[3];
    int i=0,j=0;
    double z1=1.000000;
    double z2=1.000000;
    double pri=0.000000;
    scanf("%lf %lf %lf %lf %lf %lf %lf %lf",&a1,&a2,&a3,&a4,&b1,&b2,&b3,&b4);
    a=a1-b1;
    b=a2-b2;
    c=a3-b3;
    d=a4-b4;
    z1=count (ans-0.005000);
    for(;ans<100.005000;)
    {
        //printf("ans=%lf\n",ans);
        z2=count(ans+0.005000);
        if((z1==0||z1*z2<0)&&read[i-1]!=ans)
        {
            //printf("z1=%lf,z2=%lf,ans=%lf\n",z1,z2,ans);
            read[i]=ans;
            i++;
        }
        if(z2==0&&read[i-1]!=ans)
        {
            read[i]=ans+0.010000;
            i++;
        }
        ans=ans+0.010000;
        z1=z2;
    }
    if(i==0)
    {
        printf("No comment");
    }
    else
    {
        for(j=0;j<i;j++)
        {
            pri=pri+read[j];
            //printf("read=%lf\n",read[j]);
        }
        printf("%.2lf",pri);
    }
}
```

## 四　赤沙之下有考验

```c
#include <stdio.h>
#include <ctype.h>
#include <stdlib.h>

char ans[20];

int judge(int num)
{
	//printf("num=%d",num);
	int k=1;
	for(;k<=num;)
	{
		if(k==num)
		{
			ans[0]='T';
			ans[1]='\0';
			return 0;
		}
		k=k*7;
	}
	ans[0]='F';
	ans[1]='\0';
    if(num==0)
    {
        ans[0]='0';
	    ans[1]='\0';
    }
	return 0;
}

int count(int num)
{
	//printf("num=%d",num);
	int k=1,n=1;
	for(;k<num;k++)
	{
		n=n*7;
	}
	sprintf(ans,"%d",n);
    if(num==0)
    {
        ans[0]='0';
	    ans[1]='\0';
    }
	return 0;
}

int main()
{
	char string[100];
    int n=0,i=0,flag=0,k=-1;
	scanf("%[^\n]",string);
	getchar();
	n=atoi(string);
	//printf("%d",n);
	for(;i<n;i++)
	{
		k=-1;
		flag=1;
		scanf("%[^\n]",string);
		getchar();
		//printf("%s",string);
		if(string[0]=='T'&&string[1]==' ')
		{
			//printf("str=%s",string);
			do
			{
				k++;
				string[k]=string[k+2];
			} while (string[k+2]!='\0');
			//printf("string=%s",string);
			for(k=0;string[k]!='\0';k++)
			{
                //printf("s=%c\n",string[k]);
				if(isdigit(string[k])==0&&string[k]!='\r')
				{
					flag=0;//有问题
					break;
				}
			}
			if(flag==1)
			{
				judge(atoi(string));
			}
		}
		else if(string[0]=='C'&&string[1]==' ')
		{
			//printf("str=%s",str);
			do
			{
				k++;
				string[k]=string[k+2];
			} while (string[k+2]!='\0');
			//printf("string=%s",string);
			for(k=0;string[k]!='\0';k++)
			{
				if(isdigit(string[k])==0&&string[k]!='\r')
				{
					flag=0;//有问题
					break;
				}
			}
			if(flag==1)
			{
				count(atoi(string));
			}
		}
		else
		{
			flag=0;
		}
		if(flag==0)
		{
			printf("0\n");
		}
		else
		{
			printf("%s\n",ans);
		}
	}
	return 0;
}
```

## 五　穿越烟帏与暗林

```c
#include<stdio.h>

int map[100][100],visit[100][100];
int ans=999999;
int m=0,n=0;
int cx[4]={1,0,-1,0},cy[4]={0,-1,0,1};

void search(int x,int y,int count)
{
    int tx,ty;
    int j=0;
    //printf("count=%d\n",count);
    if(x==m-1&&y==n-1&&count<ans)
    {
        ans=count;
        return;
    }
    for(j=0;j<=3;j++)
    {
        tx=x+cx[j];
        ty=y+cy[j];
        if(tx<0||tx>=m||ty<0||ty>=n)
        {
            continue;
        }
        if(map[tx][ty]==1&&visit[tx][ty]==0)
        {
            visit[tx][ty]=1;
            //printf("%d  before==%d,%d\n",count,tx+1,ty+1);
            search(tx,ty,count+1);
            visit[tx][ty]=0;
            //printf("%d  after==%d,%d\n",count,tx+1,ty+1);
        }
    }
    return;
}

int main(void)
{
    int i=0,k=0;
    scanf("%d %d",&m,&n);
    //printf("m=%d,n=%d\n",m,n);
    for(k=0;k<n;k++)
    {
        for(i=0;i<m;i++)
        {
            scanf("%d",&map[i][k]);
            //printf("i=%d,k=%d\n",i,k);
        }
    }
    for(k=0;k<n;k++)
    {
        for(i=0;i<m;i++)
        {
            visit[i][k]=0;
        }
    }
    if(map[0][0]==1)
    {
        visit[0][0]=1;
        search(0,0,1);
        //printf("ans=%d\n",ans);
        if(ans<999999)
        {
            printf("%d",ans);
        }
        else
        {
            printf("0");
        }
    }
    else{
        printf("0");
    }
    return 0;
}
```

