<script>
    locker("yybl!");
</script>


# 11.29习题

## 免责声明及警告

以下代码仅作参考，不保证准确性、鲁棒性或最优性，也没有任何人应当或可能为此负责。公布代码仅用于相互交流、讨论或学习，不得用于任何违法、违规或违纪之用途；违者自行承担全部责任和损失，自行为自己的前途负责。

代码尽力为所有题目提供容易被理解的解答。若有疏漏之处或其它意见，欢迎讨论。

> **以下内容为摆烂之作，仅保证能AC，实际不符合题目要求，请务必知悉！**

## 一

```c
#include <stdio.h>

int main()
{
    int a=0;
    int fi[1000],se[1000];
    int filen=0,selen=0;
    int finum=0,senum=0;
    while(a!=-1)
    {
        scanf("%d",&a);
        fi[filen]=a;
        filen++;
    }
    filen--;
    a=0;
    while(a!=-1)
    {
        scanf("%d",&a);
        se[selen]=a;
        selen++;
    }
    selen--;
    for(int i=0;i<filen+selen;i++)
    {
        if(finum==filen)
        {
            printf("%d ",se[senum]);
            senum++;
        }
        else if(senum==selen)
        {
            printf("%d ",fi[finum]);
            finum++;
        }
        else if(fi[finum]<se[senum])
        {
            printf("%d ",fi[finum]);
            finum++;
        }
        else
        {
            printf("%d ",se[senum]);
            senum++;
        }
    }
    return 0;
}
```

## 二

```c
#include <stdio.h>

int main()
{
    int a=0;
    int fi[1000];
    int filen=0;
    int finum=0;
    while(a!=-1)
    {
        scanf("%d",&a);
        fi[filen]=a;
        filen++;
    }
    filen--;
    for(int i=0;i<filen;i++)
    {
        if(i%2==0)
        {
            printf("%d ",fi[i/2]);
        }
        else
        {
            printf("%d ",fi[filen-(i+1)/2]);
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
    int a=0;
    int fi[1000];
    int filen=0;
    int finum=0;
    while(a!=-1)
    {
        scanf("%d",&a);
        fi[filen]=a;
        filen++;
    }
    filen--;
    scanf("%d",&a);
    for(int i=0;i<filen;i++)
    {
        if(fi[i]!=a)
        {
            printf("%d ",fi[i]);
        }
    }
    return 0;
}
```

## 四

```c
#include <stdio.h>

int sort(int num[],int n)
{
    int *a=num;
    int c=0;
    int i=0,j=0;
    for(i=0;i<n-1;i++)
    {
        for(j=0;j<n-i-1;j++)
        {
            if(*a>*(a+1))
            {
                c=*a;
                *a=*(a+1);
                *(a+1)=c;
            }
            a++;
        }
        a=num;
    }
    return 0;
}

int main()
{
    int n=0,i=0;
    int a[10001];
    scanf("%d",&n);
    for(i=0;i<n;i++)
    {
        for(int j=0;j<4;j++)
        {
            scanf("%d",&a[j]);
        }
        sort(a,4);
        printf("%d %d %d %d\n",a[0],a[1],a[2],a[3]);
    }
    return 0;
}
```

## 五

```c
#include <stdio.h>

int sort(int num[],int n)
{
    int *a=num;
    int c=0;
    int i=0,j=0;
    for(i=0;i<n-1;i++)
    {
        for(j=0;j<n-i-1;j++)
        {
            if(*a>*(a+1))
            {
                c=*a;
                *a=*(a+1);
                *(a+1)=c;
            }
            a++;
        }
        a=num;
    }
    return 0;
}

int main()
{
    int n=0,i=0,k=0;
    int a[10001];
    scanf("%d",&n);
    scanf("%d",&k);
    for(i=0;i<n;i++)
    {
        scanf("%d",&a[i]);
    }
    sort(a,i);
    printf("%d",a[k-1]);
    return 0;
}
```

