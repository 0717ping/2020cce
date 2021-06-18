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
## week13 2021/05/21
## 第一題程式碼
### 設定背景顏色
```
size(1004,400);
background(98,133,255);
```
## 第二題程式碼
### 用if(mousePressed) 及else來切換背景
```C
void setup(){
	size(1004,400);
}
void draw(){
	if(mousePressed)background(98,133,255);
	else background(251,249,157);
}
```
## 第三題程式碼
### void mousePressed()做按下去的動作
```C
void setup(){//只做一次
	size(1004,400);
}
void draw(){//每秒狂做60次
	if(mousePressed)background(98,133,255);
	else background(251,249,157);
	textSize(50);//字的大小設50
	text(a,100,100);//將a在100100畫出來
}
int a=0;//外部變數
void mousePressed(){//按下去時會呼叫函式
	a++;
}
```
## 第四題程式碼
### 顯示垷在的時間
```C
void setup(){//只做一次
	size(1004,400);
}
void draw(){
	background(98,133,255);
	textSize(50);
	int h = hour();//小時
	int m = minute();//分鐘
	int s = second();//秒
	text( "Now:" + h + ":" + m + ":" + s ,100,100);
}//            字串    數  字串   數  字串  數
```
## 第五題程式碼
### 
```C
void setup(){//只做一次
	size(1004,400);
	textFont( createFont("標楷體",50);
}
void draw(){
	background(98,133,255);
	textSize(50);
	int h = hour();//小時
	int m = minute();//分鐘
	int s = second();//秒
	fill(255,0,0);//填充墨水的色彩
	text( "Now:" + h + ":" + m + ":" + s ,100,100);//現在時間
	int total = h*60*60 + m*60 + s;//總秒數
	text(	"總秒數:" + total, 100,200);
}
```
## 第六題程式碼
### 
```C
void setup(){//只做一次
	size(1004,400);
	textFont( createFont("標楷體",50);
}
void draw(){
	background(98,133,255);
	textSize(50);
	int h = hour();//小時
	int m = minute();//分鐘
	int s = second();//秒
	fill(255,0,0);//填充墨水的色彩
	text( "Now:" + h + ":" + m + ":" + s ,100,100);//現在時間
	int total = h*60*60 + m*60 + s;//總秒數
	int total2=12*60*60 + 0*60 + 0;//目標時間的總秒數
	text(	"總秒數:" + total, 100,200);
	int ans = total2-total;
	int hh = ans/60/60%60, mm = ans/60%60, ss = ans%60;
	text(	"還剩下:" + hh + ":" + mm + ":" + ss, 100,300);
}
```
## week14 2021/05/28
## 第一題程式碼
### 用亂數random(60)取出小於60的數
```C
void setup(){//設定 只做一次
   size(300,200);
   float ans = random(60);//亂數取<60的數
   textSize(30);
   text( ans, 0, 30);
}
```
## 第二題程式碼
### 利用mosuePressed()來改亂數
```C
//Q1: 數字有小數點不好 A:整數無條件捨去
//Q2: 沒有互動 A:用mousePressed互動
void setup(){
  size(300,200);
  textSize(30);
}
int ans=0;
void draw(){//畫圖,每秒60次 60fps
  background(98,133,255);
  //int ans = (int)random(60);//強制轉型
  text( ans, 30, 30);//跳太快了
}
void mousePressed(){//mouse按下去才做亂數
   ans = (int)random(60);
}
```
## 第三題程式碼
### 亂數洗牌
```C
//int a[]={1,2,3,4,5,6,7,8,9,10};//C,C++
int []a = {1,2,3,4,5,6,7,8,9,10};//Java
void setup(){
  size(400,200);
  textSize(30);
}
void draw(){
  background(98,133,255);
  for(int i=0; i<10; i++){
     text( a[i], i*40, 100); 
  }
}
void mousePressed(){
   int i1 = (int) random(10);
   int i2 = (int) random(10);
   int temp=a[i1] ; a[i1]=a[i2] ; a[i2]=temp;
}//交換,行數太擠,所以塞成一行,中間是分號
```
## 第四題程式碼
### 大樂透拿前面6個數字當成中獎號碼
```C
//int a[]={1,2,3,4,5,6,7,8,9,10,...寫49很累
int []a = new int[49];//Java的陣列宣告
void setup(){
  size(400,200);
  textSize(30);
  for(int i=0; i<49; i++) a[i] = i+1;//人類:1
}                       //電腦:0
void draw(){
  background(98,133,255);
  for(int i=0; i<6; i++){//49只秀6個數
     text( a[i], i*50, 100); 
  }//大樂透 抽獎時,會掉下球, 49球挑6球
}
void mousePressed(){
  for(int i=0; i<10000; i++){
     int i1=(int) random(49), i2=(int) random(49);
     int temp=a[i1]; a[i1]=a[i2]; a[i2]=temp;
  }
}
```
## 第五題程式碼
### 大樂透的球
```C
int []a = new int[49];//Java的陣列宣告
void setup(){
  size(400,200);
  textSize(30);
  for(int i=0; i<49; i++) a[i] = i+1;//人類:1 丟入號碼球
  for(int i=0; i<10000; i++){
     int i1=(int) random(49), i2=(int) random(49);
     int temp=a[i1]; a[i1]=a[i2]; a[i2]=temp;
  }
}
int N=0;
void draw(){
  background(98,133,255);
  for(int i=0; i<N; i++){//49只秀6個數
     fill(255); ellipse(50+i*50, 100, 40, 40);//白球
     textAlign(CENTER,CENTER);//文字對齊 中,中
     fill(0); text( a[i], 50+i*50, 100);//黑字
  }
}
void mousePressed(){
  N++;
}
```
## week15 2021/06/04
## 第一題程式碼
### 複習倒數計時
```C
void setup(){
  size(400,200);
  textSize(40);
}
void draw(){
  background(98,133,255);
  int s = second();
  text( s, 100,100);
}
```
## 第二題程式碼
### 用餘數及減法做出9到0的倒數計時
```C
void setup(){
  size(400,200);
  textSize(40);
}
void draw(){
  background(98,133,255);
  int s = second();
  //text( 59-s, 100,100);
  text( 9-s%10, 100,100);
}
```
## 第三題程式碼
### 下載函式Sound播出聲音
```C
//發出聲音,有點難,要用外掛Processing的Sound
//這裡叫PDE:Processing Developing Environment
import processing.sound.*;
SoundFile player;
//tada.mp3檔, 也可以拉進來這裡
void setup(){
  size(400,200);
  player = new SoundFile( this, "tada.mp3" );
}
void draw(){
  background(98,133,255);
}
void mousePressed(){
  player.play();
}
```
## 第四題程式碼
### 把123合併
```C
//從第2步的程式開始增加!!!
import processing.sound.*;//Step03的程式
SoundFile player;//Step03的程式
void setup(){
  size(400,200);
  textSize(40);
  player = new SoundFile( this, "tada.mp3" );
}//Step03的程式, 記得把tada.mp3也放進來
void draw(){//每秒60次
  background(98,133,255);
  int s = second();
  //text( 59-s, 100,100);
  text( 9-s%10 , 100,100);
  if( 9-s%10 == 0 ) player.play();//Step03的程式
}//0秒的時候,if()會進去60次
```
## 第五題程式碼
### stop(), 否則 play()
```C
//Step03出發做Step05
import processing.sound.*;
SoundFile player;
void setup(){
   size(400,200);
   player = new SoundFile( this, "bell.mp3" );
}//把bell.mp3放進來
void draw(){
  background(98,133,255);
}
void mousePressed(){//2種:play(),stop()
  if( player.isPlaying() ){
    player.stop();
  }else{
    player.play();
  }
}
```
## 第六題程式碼
### 將processing to p5 js converter轉換
```C
function setup(){
  createCanvas(400,200);
  textSize(40);
}
function draw(){
  background(98,133,255);
  let s = second();
  text( s, 100,100);
}
```
## week16 2021/06/11
## 第一題程式碼
### 畫出圓形,設定圓心,寬,高
```C
void setup(){//設定 只做一次
  size(400,200);
}
void draw(){//畫圖
  background(98,133,255);
  ellipse(50,50,80,80);
}
```
## 第二題程式碼
### start,stop利mouseX除50.0 來輔助 半圓
```C
void setup(){//設定 只做一次
  size(400,200);
}
void draw(){//畫圖
  background(98,133,255);
  fill(255);//白
  ellipse(50,50,80,80);
  fill(255,0,0);//紅
  float stop=mouseX/50.0;
  text(stop, 200,100);
  arc(100,100,180,180,0,stop);
}
```
## 第三題程式碼
### degrees.弧度radians 的差別
```C
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
int degree=0;
void draw(){
   background(98,133,255);
   arc(100,100, 180,180,radians(90),radians(180));
}
```
## 第四題程式碼
### 利用 shift移動量的變數讓它每秒轉動60度
```C
 void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
float shift=0;
void draw(){
   background(98,133,255);
   float start = radians(90+shift);
   float stop = radians(180+shift);
   arc(100,100, 180,180, start, stop );
   shift+=1;
}
```
## 第五題程式碼
### v乘0.99變慢最後很慢時停下來
```C
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
float shift=0, v=10;//一開始速度為0
void draw(){
   background(98,133,255);
   float start = radians(90+shift);
   float stop = radians(180+shift);
   arc(100,100, 180,180, start, stop );
   if(v>0.0001){//還有速度時會轉動
    shift+=v;//轉動的速度
    v = v * 0.99;//速度會慢慢減速
   }
   text(shift, 200, 100);//印出shift
   text(v, 200,150);//印出轉動的速度
}
```
## 第六題程式碼
### 觸發 random()讓v是亂數
```C
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
float shift=0, v=0;//一開始速度為0
void mousePressed(){
  v = random(10)+5;//5...15.0
}
void draw(){
  background(98,133,255);
   float start = radians(90+shift);
   float stop = radians(180+shift);
   arc(100,100, 180,180, start, stop );
  if(v>0.1){//還有速度時會轉動
    shift+=v;//轉動的速度
    v = v * 0.99;//速度會慢慢減速
   }
   text(shift, 200, 100);//印出shift
   text(v, 200,150);//印出轉動的速度
}
```
## 第七題程式碼
### 畫出24片小Pizza
```C
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
float shift=0, v=0;//一開始速度為0
void mousePressed(){
  //v = random(10);//0...10.0
  v = random(10)+5;//5...15.0
}
void draw(){
  background(98,133,255);
  for(int i=0;i<24;i++){
    if( i%3==0 ) fill(0);
    if( i%3==1 ) fill(255);
    if( i%3==2 ) fill(255,180,0);
    float start = radians(    0+shift+i*360/24);
    float stop = radians(360/24+shift+i*360/24);
    arc(100,100, 180,180, start, stop );
  }
  if(v>0.1){//還有速度時會轉動
    shift+=v;//轉動的速度
    v = v * 0.99;//速度會慢慢減速
   }
   text(shift, 200, 100);//印出shift
   text(v, 200,150);//印出轉動的速度
}
```
## week17 2021/06/18
## 第一題程式碼
### 
```C
void setup(){
    size(400,200);
    textSize(40);
}
String line="world";
void draw(){
  background(0);
  text( "hello", 100,100);
  text(  line,   100,150);
}
```
## 第2題程式碼
### 
```C
void setup(){
    size(400,200);
    textSize(40);
}
String line="";
String Q="hello";
void draw(){
  background(0);
  text( "Q:  "+Q,     100,100);
  text( "You:"+line,  100,150);
}
void mousePressed(){
  line = line + "a";
}
```
## 第3題程式碼
### 
```C
void setup(){
    size(400,200);
    textSize(40);
}
String line="";
String Q="hello";
void draw(){
  background(0);
  text( "Q:  "+Q,     100,100);
  text( "A:  "+line,  100,150);
}
void keyPressed(){
  line = line + key;
}
```
## 第4題程式碼
### 
```C
void setup(){
    size(400,200);
    textSize(40);
}
String line="";
String Q="hello";
void draw(){
  background(0);
  text( "Q:  "+Q,     100,100);
  text( "A:  "+line,  100,150);
}
void keyPressed(){
  int len = line.length();
  if(key>='a' && key<='z') line = line + key;
  if(key>='A' && key<='Z') line = line + key;
  if(key == BACKSPACE ) line = line.substring(0,len-1);
}
```
## 第5題程式碼
### 
```C
void setup(){
    size(400,200);
    textSize(40);
}
String line="";
String Q="hello";
void draw(){
  background(0);
  int len = line.length(); text( len, 100,50);
  text( "Q:  "+Q,     100,100);
  text( "A:  "+line,  100,150);
}
void keyPressed(){
  int len = line.length();
  if(key>='a' && key<='z') line = line + key;
  if(key>='A' && key<='Z') line = line + key;
  if(key == BACKSPACE && len>0 ) line = line.substring(0,len-1);
}
```
## 第6題程式碼
### 
```C
void setup(){
    size(400,200);
    textSize(40);
}
String line="";
String Q ="hello";
void draw(){
  background(0);
  text("Score: " + score, 100,50);
  text( "Q:  "+Q,     100,100);
  text( "A:  "+line,  100,150);
}
int score=0;
void keyPressed(){
  int len = line.length();
  if(key>='a' && key<='z') line = line + key;
  if(key>='A' && key<='Z') line = line + key;
  if(key == BACKSPACE && len>0 ) line = line.substring(0,len-1);
  if(key == ENTER){
    if(line.equals(Q)==true){
      score ++;
    }else score --;
  }
}
```
## 第7題程式碼
### 
```C
void setup(){
   size(400,200);
   textSize(40);
}
String line="";
String []Q={ "hello", "world", "other"};
int Qi=0;
void draw(){
   background(0);
   text("Score: "+score,100,50);
   text("Q: "+Q[Qi],100,100);
   text("A: "+line,100,150);
}
int score=0;
void keyPressed(){
  int len=line.length();
   if(key>='a'&&key<='z')line = line + key;
   if(key>='A'&&key<='Z')line = line + key;
   if(key == BACKSPACE && len>0)line = line.substring(0,len-1);
   if(key == ENTER){
      if(line.equals(Q[Qi])==true ){
        score++;
        Qi++;
        line = "";
      }else score --;
   }
}
```
