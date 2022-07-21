## 17行推箱子，接近理论极限（没有把多个语句放在同一行的情况，放心）


##### 没想到吧我居然把源代码直接放在README里，反正也只有17行


```)
#include <stdio.h>
#include <windows.h>
main() {
	int x,y,z,s=103,p,u,m[10][10]={0};
	char o[7][5]={"  ","人","点","汄","箱","墙","湘"};
	SetConsoleCursorInfo(GetStdHandle(STD_OUTPUT_HANDLE),&((CONSOLE_CURSOR_INFO){1,0}));
	m[2][2]=1,m[3][2]=2,m[4][3]=6,m[6][3]=4,m[6][6]=5;//这里放地图的初始值
	do {
		SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),(COORD){0,0});
		for (int i=0;i<10;i++) {
			for (int n=0;n<10;n++) {
				s>3?(!i||i==9||!n||n==9?(m[i][n]=5):0,s==4?s-=3:s--):(m[i][n]==1||m[i][n]==3?x=n,y=i:0,m[i][n]==4?s=2:0,printf((n==9?"%s\n":"%s"),o[m[i][n]%7]));
			}
		}
		s==2?(p=((z=_getch())=='a'?2:z=='w'?1:z=='s'?3:z=='d'?4:0),(u=p==2&&x==1||p==1&&y==1||p==4&&x==8||p==3&&y==8||m[y+(p-2)%2][x+(p-3)%2]==5?0:m[y+(p-2)%2][x+(p-3)%2]<3?1:m[y+(p-2)%2][x+(p-3)%2]+m[y+(p-2)%2*2][x+(p-3)%2*2]<7?-1:0)>0?(m[y][x]--,m[y+(p-2)%2][x+(p-3)%2]++):u<0?(m[y][x]--,m[y+(p-2)%2][x+(p-3)%2]-=3,m[y+(p-2)%2*2][x+(p-3)%2*2]+=4):0):s==1?printf(" You win!"):0;
	} while (s--);
}
(```
