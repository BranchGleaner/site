<script>
    locker("mzsm");
</script>

# 11.15习题

## 免责声明及警告

以下代码仅作参考，不保证准确性、鲁棒性或最优性，也没有任何人应当或可能为此负责。公布代码仅用于相互交流、讨论或学习，不得用于抄作业等违法、违规或违纪之用途；违者自行承担全部责任和损失，自行为自己的前途负责。

代码尽力为所有题目提供容易被理解的解答。若有疏漏之处或其它意见，欢迎讨论。

## 一

```c
#include<stdio.h>

int main()
{
    int a=0,b=0,c=0;
    scanf("%d %d",&a,&b);
    c=a;
    a=b;
    b=c;
    printf("%d %d",a,b);
    return 0;
}
```

## 二

```c
#include <stdio.h>
#include <string.h>

int max(int a,int b)
{
    if(a<b)
    {
        return b;
    }
    else
    {
        return a;
    }
}

int judge(char a[],char b[])
{
    int i=0,ans=0;
    for(i=0;i<max(strlen(a),strlen(b));i++)
    {
        if(a[i]<b[i])
        {
            ans=-1;
            break;
        }
        if(a[i]>b[i])
        {
            ans=1;
            break;
        }
    }
    return ans;
}

int main()
{
    char s[100],t[100],r[100];
    gets(s);
    gets(t);
    gets(r);
    if(judge(s,t)==-1)
    {
        if(judge(s,r)==-1)
        {
            if(judge(t,r)==-1)
            {
                printf("%s\n",s);
                printf("%s\n",t);
                printf("%s\n",r);
            }
            else
            {
                printf("%s\n",s);
                printf("%s\n",r);
                printf("%s\n",t);
            }
        }
        else
        {
            printf("%s\n",r);
            printf("%s\n",s);
            printf("%s\n",t);
        }
    }
    else
    {
        if(judge(s,r)==1)
        {
            if(judge(t,r)==-1)
            {
                printf("%s\n",t);
                printf("%s\n",r);
                printf("%s\n",s);
            }
            else
            {
                printf("%s\n",r);
                printf("%s\n",t);
                printf("%s\n",s);
            }
        }
        else
        {
            printf("%s\n",t);
            printf("%s\n",s);
            printf("%s\n",r);
        }
    }
    return 0;
}
```

## 三

```c
#include <stdio.h>

int main()
{
    int a[10000],b[10000];
    int n,m,i=0,ai=0,bi=0;
    scanf("%d %d",&n,&m);
    for(i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    for(i=0;i<m;i++)
    {
        scanf("%d",&b[i]);
    }
    for(i=0;i<m+n;i++)
    {
        //printf("i=%d\n",i);
        if(ai==n)
        {
            printf("%d ",b[bi]);
            bi++;
            continue;
        }
        if(bi==m)
        {
            printf("%d ",a[ai]);
            ai++;
            continue;
        }
        if(a[ai]<=b[bi])
        {
            printf("%d ",a[ai]);
            ai++;
        }
        else
        {
            printf("%d ",b[bi]);
            bi++;
        }
    }
    return 0;
}
```

## 四

```c
#include <stdio.h>

int main()
{
    int a[100][100];
    int n,m,i=0,k=0,sum=0,num=0;
    long long int max=-9999999999;
    scanf("%d %d",&n,&m);
    for(i=0;i<n;i++)
    {
        sum=0;
        for(k=0;k<m;k++)
        {
            scanf("%d",&a[i][k]);
            sum=sum+a[i][k];
        }
        if(sum>max)
        {
            max=sum;
            num=i;
        }
    }
    for(k=0;k<m;k++)
    {
        printf("%d ",a[num][k]);
    }
    return 0;
}
```

## 五

```c
#include <stdio.h>

int main()
{
    int a[100];
    int n,m,i,k;
    scanf("%d",&n);
    for(i=0;i<n;i++)
    {
        scanf("%d",&m);
        for(k=0;k<m;k++)
        {
            scanf("%d",&a[k]);
        }
        for(k=m-1;k>=0;k--)
        {
            printf("%d ",a[k]);
        }
        printf("\n");
    }
    return 0;
}
```


