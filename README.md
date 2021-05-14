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
###  示範 struct POINT{ float x, y; }; 的宣告定義
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
###  C Tutor 及 CodeBlocks 示範 struct POINT a={4.1, 3.2}; 並利用 a.x 及 a.y 印出來
```C
#include <stdio.h>

struct POINT {
    float x, y;
};

int main()
{
    struct POINT a = { 4.1, 3.2 };
    printf("%f %f\n",a.x,a.y);
}
```
## 第三題程式碼
### C Tutor 及 CodeBlocks 示範, 接續上題, 再利用 a.x 及 a.y 來改變裡面的值
```C
#include <stdio.h>

struct POINT {
    float x, y;
};

int main()
{
    struct POINT a = { 4.1, 3.2 };
    printf("%f %f\n",a.x,a.y);

    a.x=1;
    a.y=2;
    printf("%f %f\n", a.x,a.y);
}
```
## 第四題程式碼
###  C Tutor 及 CodeBlocks(配合printf) 示範 外面的global全域變數 會初始值, 裡面的 local區域變數會是亂碼
```C
#include <stdio.h>

struct DATA {
    int x, y;
} a[3] ;
struct DATA b={100,200};

int main()
{
    for(int i=0; i<3; i++){
        printf("a[%d]:%d %d\n", i, a[i].x, a[i].y );
    }
    printf("b: %d %d\n", b.x, b.y );

    struct DATA c;
    printf("c: %d %d 像亂碼\n", c.x, c.y );

    c = b;
    printf("c: %d %d\n", c.x, c.y );
}
```
## 第五題程式碼
###  C Tutor 及 CodeBlocks(配合printf) 示範, (結構)有個陣列、有個指標, 使用 p->x, p->y, p->z 取用到指標指到的值
```C
#include <stdio.h>
struct POINT {
    float x, y, z;
};
struct POINT point[5]={(0,0,0),(1,0,0),(0,1,0),(0,0,1),(1,1,1)};
int main()
{
    struct POINT*p=&point[0];
    printf("%.2f %.2f %.2f\n",p->x,p->y,p->z);
    p++;
    printf("%.2f %.2f %.2f\n",p->x,p->y,p->z);
    p++;
    printf("%.2f %.2f %.2f\n",p->x,p->y,p->z);
}
```
## week10 2021/04/29
## 第一題程式碼
### 陣列 tree 裡面放樹的名字qsort() 配合你的 compare() 來把樹名排序分成 for迴圈前面開頭, for迴圈中間 [收尾+開頭] for迴圈後面收尾
```C
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
char line[1000];
char tree[1000000][32];
int compare(const void *p1,const void*p2){
     return strcmp ((char*)p1,(char*)p2);
}
int main()
{
   int T;
   scanf("%d\n",&T);//讀資料
   
   for(int t=0;t<T;t++){//讀資料 get()一整行
       int N=0;//需要知道有幾棵樹
       while(gets(line)!=NULL){//讀失敗會變NULL
             if(strcmp(line,"")==0)break;//空行要離開
             
             strcpy(tree[N],line);//把樹的名字放到tree
             
             N++;//樹的統計
       }
       
       qsort(tree,N,32,compare);
       
       if(t>0)printf("\n");//前面有空白
       int ans=1;//新的開始
       printf("%s ",tree[0]);
       for(int i=0;i<N-1;i++){
          if(strcmp(tree[i],tree[i+1])==0){
             ans++;
          }else{//不相同，收尾+新的開始
                printf("%.4f\n",100*ans/(float)N);//收尾
                ans=1;
                printf("%s ",tree[i+1]);//新的開始
           }

       }
       printf("%.4f\n",100*ans/(float)N);//最後收尾
   }   
}
```
## week11 2021/05/7
## 第一題程式碼
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
char line[2000][80];
char others[80];
int compare(const void *p1,const void *p2)
{
	char * s1 =(char*) p1;
	char * s2 =(char*) p2;
	
	int result = strcmp( s1, s2);
	if (result>0) return 1;
	if (result==0) return 0;
	if (result<0) return -1; 
}
int main()
{
	int n;
	scanf("%d",&n);
	for(int i=0;i<n;i++)
	{
		scanf("%s",line[i]);
		gets( others );
	}
	
	qsort(line,n,80,compare);
	
	int ans=1;
	for(int i=0;i<n;i++)
	{
		if(strcmp(line[i],line[i+1])==0)ans++;
		else{
			printf("%s %d\n",line[i],ans);
			ans=1;
		}
	}
}
```
## 第二題程式碼
```C
#include <stdio.h>
#include <stdlib.h>
int a[10]={4,8,3,7,5,2,9,1,6,10};

int compare( const void *p1,const void *p2)
{
    int d1 = * (int*)p1 ;
    int d2 = * (int*)p2 ;
    if( d1 > d2 ) return 1;
    if( d1 == d2 ) return 0;
    if( d1 < d2 ) return -1;
}
int main()
{
    qsort( a, 10, sizeof(int),compare);
    for(int i=0; i<10; i++){
        printf("%d ",a[i]);
    }
}
```
## 第三題程式碼
```C
#include <stdio.h>
struct data{
    int ans;//有幾個?
    char c;//字母
};
struct data box;
int main()
{
    box.ans=1;
    box.c='A';

    printf("%c %d\n",box.c,box.ans);
}
```
## 第四題程式碼
```C
#include <stdio.h>
typedef struct data{
    int ans;//有幾個?
    char c;//字母
}DATA;
//struct data box;
DATA box;
int main()
{
    box.ans=1;
    box.c='A';

    printf("%c %d\n",box.c,box.ans);
}
```
## 第五題程式碼
```C
#include <stdio.h>
char line[2000];
int main()
{//step01:Input 一次一整行很多一整行
	for( int t=0; gets(line) ; t++){
		//step02: Ouput
		if(t>0) printf("\n");
		printf("blahblahblah\n");
		printf("blahblahblah\n");
		printf("blahblahblah\n");
	}
}
```
## 第六題程式碼
```C
#include <stdio.h>
char line[2000];
int ans[256];//step03: 統計有幾個字母ex. ans[65]=3 表示'A'有3次
int main()
{//step01:Input 一次一整行 很多一整行
	for( int t=0; gets(line) ; t++){
	
		for(int i=0; i<256; i++) ans[i]=0;//step03:清乾淨
		
		for(int i=0; line[i]!=0; i++){//step04:字串的迴圈
			char c =line[i];//step04:第i個字母
			ans[ c ] ++;//step04:統計到ans[]裡面
		}
		
		//step02: Ouput 對應印出來
		if( t>0 ) printf("\n");
		for(int i=0; i<256 ;i++){
			if( ans[i]>0 )printf("%d %d\n", i, ans[i] );
		}
	}
}
```
## week12 2021/05/14
## 第一題程式碼
```C
#include <stdio.h>
char line[2000];
int main()
{
	for(int t=0; gets( line ); t++){ //Step01: Input
		int ans[256]={};//{0,0,0,0,0,0...}
		
		for(int i=0; line[i]!=0; i++){
			char c = line[i];
			ans[c] ++;
		}//Step03: 字串的for迴圈
		
		if(t>0) printf("\n");//車廂 前面掛空白行
		for(int i=0; i<256; i++){ //Step02: Output
			if(ans[i]>0) printf("%d %d\n", i, ans[i]);
		}
	}
}
```
## 第二題程式碼
```C
#include <stdio.h>
char line[2000];
int main()
{
	for(int t=0; gets( line ) ; t++){ //Step01: Input
		int ans[256]={};// {0,0,0,0,0,0,0,0,0...}
		char  c[256]={};// {0,1,2,3,...,65,66,67...}
		for(int i=0; i<256; i++) c[i] = i;
		
		for(int i=0; line[i]!=0 ;i++){
			char c = line[i];
			ans[c] ++;
		}//Step03:字串的for迴圈
		
		for(int i=0; i<256; i++){//左手i //排序
			for(int j=i+1; j<256; j++){//右手j
				if( ans[i] > ans[j] ){
					int temp=ans[i];//交換ans[]
					ans[i]=ans[j];
					ans[j]=temp;
					char t=c[i];//交換
					c[i]=c[j];
					c[j]=t;
				}
				if( ans[i] == ans[j] && c[i]<c[j]){
					int temp=ans[i];//交換ans[]
					ans[i]=ans[j];
					ans[j]=temp;
					char t=c[i];//交換字母
					c[i]=c[j];
					c[j]=t;
				}
			}
		}
		if(t>0) printf("\n");//車廂 前面掛空白行
		for(int i=0; i<256; i++){ //Step02: Output
			if(ans[i]>0) printf("%d %d\n", c[i], ans[i] );
		}
	}
}
```
## 第三題程式碼
```C
#include <stdio.h>
int a[100];
int main()
{
	int T;//Step01: Input 有幾筆
	scanf("%d", &T);
	for(int t=0; t<T; t++){
		int N;
		scanf("%d", &N);
		for(int i=0; i<N; i++){//Step02: Input到陣列a[i]
			scanf("%d", &a[i]);
		}
		
		int ans=0;
		
		for(int k=0; k<N-1; k++){
			for(int i=0; i<N-1; i++){//泡泡還續 還不對
				if(a[i] > a[i+1]){
					int temp=a[i];
					a[i]=a[i+1];
					a[i+1]=temp;
					ans++;//又做了一次交換swap
				}
			}
		}
		//Step03: Output
		printf("Optimal train swapping takes %d swaps.\n", ans);
	}
}
```
