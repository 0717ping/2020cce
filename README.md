# 2020cce
2020程式設計的程式碼倉庫

## week01 2021/02/26
## 第一題程式碼
```C
#include <stdio.h>
int main()
{
	int n;
	scanf("%d",&n);
	printf("%d=50*%d+5*%d+1*%d\n",n,n/50,(n%50)/5,(n%5)/1);
}
```
## 第二題程式碼
```C
#include <stdio.h>
int main()
{
	int n;
	scanf("%d",&n);
	
	int ans=0;
	for(int i=1;i<=n;i++)
	{
		if(n%i==0) ans=ans+1;		
	}
	printf("%d\n",ans);
}
```
## 第三題程式碼
```C
#include <stdio.h>
int main()
{
	int a[10],ans=0;

	for(int i=0;i<10;i++)
	{
		scanf("%d",&a[i]);
		if(a[i]%3==0) ans++;
	}
	printf("%d\n",ans);
}
```
## 第四題程式碼
```C
#include <stdio.h>
int main()
{
	int n;
	scanf("%d",&n);
	
	if(n>=90) printf("A\n");
	else if(80<=n && n<90) printf("B\n");
	else if(60<=n && n<80) printf("C\n");
	else printf("F\n");
}
```
## 第五題程式碼
```C
#include <stdio.h>
int main()
{
	int a,b,i,ans=1;
	scanf("%d%d",&a,&b);
	
	for(i=1;i<=b;i++)
	{
		if(a%i==0 && b%i==0)
		ans=i;
	}
	printf("%d %d\n",a/ans,b/ans);
}
```
## week02 2021/03/05
## 第一題程式碼
### 利用 int *p 來改變 n1變數的值
```C
#include <stdio.h>
int main()
{
    int n1=10, n2=20, n3=30;
    printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);

    int *p = &n1;
    *p = 200;
    printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
}
```
## 第二題程式碼
### 利用 int *p2 來改變 n3 變數的值
```C
#include <stdio.h>
int main()
{
    int n1=10, n2=20, n3=30;
    printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);

    int *p = &n1;
    *p = 200;
    printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);

    int *p2 = &n3;
    *p2 = 300;
    printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
}
```
## 第三題程式碼
### 利用 p2=p 讓口袋的address位址換了一張, 所以 *p2=400 就會換到其他地方送400元
```C
#include <stdio.h>
int main()
{
    int n[3]={10,20,30};
    printf("n[0]:%d n[1]:%d n[2]:%d\n",n[0],n[1],n[2]);

    int *p = &n[0];
    *p = 200;
    printf("n[0]:%d n[1]:%d n[2]:%d\n",n[0],n[1],n[2]);

    int *p2 = &n[2];
    *p2 = 300;
    printf("n[0]:%d n[1]:%d n[2]:%d\n",n[0],n[1],n[2]);

    p2=p;
    *p2=400;
    printf("n[0]:%d n[1]:%d n[2]:%d\n",n[0],n[1],n[2]);
    return 0;
}
```
## week03 2021/03/12
## 第一題程式碼
### int *p = &a[2]; *p=222; p = p + 2; *p = 666;
```C
#include <stdio.h>
int main()
{
    int a[5] = { 0, 10, 20, 30, 40};
    int *p = &a[2];
    *p = 222;

    p = p + 2;
    *p = 666;
}
```
## 第二題程式碼
### int *p = &a[2]; *p=222; p = p + 2; *p = 666;p--; *p=555;
```C
#include <stdio.h>
int a[5] = { 0, 10, 20, 30, 40};
void printAll()
{
    for(int i=0; i<5 ;i++)printf("%d ", a[i]);
    printf("\n")
}
int main()
{
        printAll();
    int *p = &a[2];
    *p = 222;
        printAll();
    p = p + 2;
    *p = 666;
        printAll();
    p--;
    *p = 555;
        printAll();
}
```
## 第三題程式碼
### int * p = &a[2] ; 的 p 心中的值(心裡放住址的小紙條) 印出來給你看 printf("%d\n", p);
```C
#include <stdio.h>
int a[5] = { 0, 10, 20, 30, 40};
void printAll()
{
    for(int i=0; i<5 ;i++)printf("%d ", a[i]);
    printf("\n")
}
int main()
{
        printAll();
    int *p = &a[2];
    *p = 222;
        printAll();
        printf("p心裡小紙條記ㄉ值是:%d\n",p);
    p = p + 2;
    *p = 666;
        printAll();
        printf("p心裡小紙條記ㄉ值是:%d\n",p);
    p--;
    *p = 555;
        printAll();
        printf("p心裡小紙條記ㄉ值是:%d\n",p);
}
```
## 第四題程式碼
### malloc()
```C
#include <stdio.h>
#include <stdlib.h>

int a[10];
int main()
{
    int b[10];

    int *p = (int*) malloc( sizeof(int)*10 );

    return 0;
}
```
## week04 2021/03/19
## 第一題程式碼
```C
#include <stdio.h>

struct POINT {
    float x, y;
};

int main()
{
    struct POINT a;
}
```
## 第二題程式碼
```C

```
## 第三題程式碼
```C

```
## 第四題程式碼
```C

```
## 第五題程式碼
```C

```
