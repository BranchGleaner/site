<script>
    locker("rnkyclzd");
</script>


# 11.22习题

## 免责声明及警告

以下代码仅作参考，不保证准确性、鲁棒性或最优性，也没有任何人应当或可能为此负责。公布代码仅用于相互交流、讨论或学习，不得用于任何违法、违规或违纪之用途；违者自行承担全部责任和损失，自行为自己的前途负责。

代码尽力为所有题目提供容易被理解的解答。若有疏漏之处或其它意见，欢迎讨论。

> **注意：以下代码实现均未按要求使用指针！**

## 一

```c
#include <stdio.h>
//实现子串查找等

int getlen(char *c)
//实现字符数统计
{
    int num=0;
    char *n=c;
    while(*n!='\0')
    {
        num++;
        n++;
    }
    return num;
}

int search(char *x,char *y)
{
    char *a=x,*b=y;
    int f=getlen(a);
    int s=getlen(b);
    int n=0;
    int c=0;
    while(*(a+s-1)!='\0')
    {
        for(n=0;*b!='\0';n++)
        {
            if(*a!=*b)
            {
                a++;
                b++;
                break;
            }
            a++;
            b++;
        }
        if(n==s)
        {
            return c;
        }
        c++;
        a=x+c;
        b=y;
        //printf("n=%d\n",n);
    }
    return 0;
}

int main()
{
    int n=0,i=0;
    char a[10001],b[10001];
    scanf("%d",&n);
    gets(a);
    for(i=0;i<n;i++)
    {
        gets(a);
        gets(b);
        char *p=a,*q=b;
        printf("%d\n",search(p,q)-1);
    }
    return 0;
}
```

## 二

```c
#include <stdio.h>

int search(char *c)
//实现字符数统计
{
    int num=0;
    char *n=c;
    int flag=0;
    while(*n!='\0')
    {
        if(*n>='0'&&*n<='9')
        {
            if(flag==0)
            {
                flag=1;
                num++;
            }
            
        }
        else
        {
            flag=0;
        }
        n++;
    }
    return num;
}

int main()
{
    int n=0,i=0;
    char a[10001];
    scanf("%d",&n);
    gets(a);
    for(i=0;i<n;i++)
    {
        gets(a);
        char *p=a;
        printf("%d\n",search(p));
    }
    return 0;
}
```

## 三

> **为省事起见，第三题的实现也完全符合第五题的要求。即：第三题与第五题的代码完全相同。**

```c
#include <stdio.h>

int count=0;
char *p=NULL;

int getlen()
//实现字符数统计
{
    int num=0;
    while(*p!='\0')
    {
        num++;
        p++;
    }
    p=p-1;
    return num;
}

void putt(int num)
{
    printf("%c",*p);
    p=p-1;
    if(num==count-1)
    {
        printf("\n");
        return;
    }
    num++;
    putt(num);
}

int main()
{
    int n=0,i=0;
    char a[10001];
    scanf("%d",&n);
    gets(a);
    for(i=0;i<n;i++)
    {
        p=a;
        gets(a);
        count=getlen();
        putt(0);
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
        scanf("%d",&a[i]);
    }
    sort(a,i);
    for(i=0;i<n;i++)
    {
        printf("%d ",a[i]);
    }
    return 0;
}
```

## 五

```c
#include <stdio.h>

int count=0;
char *p=NULL;

int getlen()
//实现字符数统计
{
    int num=0;
    while(*p!='\0')
    {
        num++;
        p++;
    }
    p=p-1;
    return num;
}

void putt(int num)
{
    printf("%c",*p);
    p=p-1;
    if(num==count-1)
    {
        printf("\n");
        return;
    }
    num++;
    putt(num);
}

int main()
{
    int n=0,i=0;
    char a[10001];
    scanf("%d",&n);
    gets(a);
    for(i=0;i<n;i++)
    {
        p=a;
        gets(a);
        count=getlen();
        putt(0);
    }
    return 0;
}
```

