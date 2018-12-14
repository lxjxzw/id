#include <stdbool.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
typedef struct
{
    char number[10];
    char name[20];
    char profession[20];
    int classNo;
    char date[20];
} file;

int i=10;
file c[100] =
{
    {"A001","小红","软件工程",02,"2017年9月1日"},
    {"A002","小橙","土木工程",03,"2017年9月1日"},
    {"A003","小黄","商务英语",01,"2017年9月1日"},
    {"A004","小绿","材料物理",07,"2017年9月1日"},
    {"A005","小青","应用化学",8,"2017年9月1日"},
    {"A006","小蓝","法语",11,"2017年9月1日"},
    {"A007","小紫","俄语",05,"2017年9月1日"},
    {"A008","小黑","日语",06,"2017年9月1日"},
    {"A009","小白","韩语",04,"2017年9月1日"},
    {"A010","小明","德语",9,"2017年9月1日"}
};

int main(void)
{
    system("color 35");
    int a;
    void zhujiemian();
    void display();
    void search();
    void add();
    void delete();
    void tuichu();
    void change();
    zhujiemian();
    printf("请选择功能\n");
    while(scanf("%d",&a)!=EOF)
    {
        switch(a)//实现选择功能
        {
            case 1:
                change();
                break;
            case 2:
                display();
                break;
            case 3:
                search();
                break;
            case 4:
                add();
                break;
            case 5:
                delete();
                break;
            case 6:
                tuichu();
                break;
            default:
                printf("输入错误，请重新选择功能!\n");
        }
    }
}

void zhujiemian()
{
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
    printf("$                                                                         $\n");
    printf("$                        欢迎使用档案管理系统                             $\n");
    printf("$                                                                         $\n");
    printf("---------------------------------------------------------------------------\n");
    printf("$                            设计制作:                                    $\n");
    printf("$                     哈尔滨理工大学 软件1班 刘雪洁                       $\n");
    printf("$                                                                         $\n");
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
    printf("$    1修改数据                        2显示数据                           $\n");
    printf("$    3查找数据                        4增加数据                           $\n");
    printf("$    5删除数据                        6退出                               $\n");
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
}



void display()
{
    int j;
    printf("      档案号     姓名       专业             班级           建档日期\n");//汉字两字节空格一字节对齐
    for(j=0; j<i; j++)
    {
        printf("%10s %10s %10s %15d %20s\n",c[j].number,c[j].name,c[j].profession,c[j].classNo,c[j].date);
    }
}
void change()//功能为输入档案号后，修改该学生的除档案号以外的所有信息
{
    char v[20];
    printf("按照档案号修改\n");
    printf("输入该学生的档案号");
    scanf("%s", v);
    char temp[3][20];
    bool len=false;
    if(v[0] == 'A')
    {
        for(int j=0; j<i; j++)
        {
            if(strcmp(v, c[j].number) == 0)
            {
                printf("输入除档案号以外的所有数据:");
                for(int y=0; y<4; y++)
                {
                    scanf("%s", temp[y]);
                }
                strcpy(c[j].name, temp[0]);
                strcpy(c[j].profession, temp[1]);
                c[j].classNo = atoi(temp[2]);//自动类型转换
                strcpy(c[j].date, temp[3]);
                len=true;
                printf("档案号:%s 姓名:%s 专业:%s 班级:%d 建档日期:%s\n",c[j].number,c[j].name,c[j].profession,c[j].classNo,c[j].date);
                break;
            }
        }
            if(len) printf("修改成功");
            else
            printf("没有找到此档案号");
    }
    else printf("输入不合法\n");
}
void search()//按档案号或姓名
{
    void one(char n[]);
    void two(char h[]);
    printf("请选择查找功能\n");
    printf("1~按档案号 2~按姓名");
    int m;
    char n[20],h[20];
    scanf("%d",&m);
    switch(m)
    {
        case 1:
            one(n);
            break;
        case 2:
            two(h);
            break;
        default:
            printf("输入错误！请重新选择功能!\n");
    }
}
void one(char n[])
{
    int p;
    getchar();
    printf("请输入档案号");
    scanf("%s",n);
    for(p=0; p<i; p++)
        if(strcmp(n,c[p].number)==0)
        {
            printf("%10s%10s%10s%15d%10s\n",c[p].number,c[p].name,c[p].profession,c[p].classNo,c[p].date);
            break;
        }
    if(p==i)printf("无此数据");
}
void two(char h[])
{
    int y;
    getchar();
    printf("请输姓名");
    scanf("%s",h);
    for(y=0; y<i; y++)
        if(strcmp(h,c[y].name)==0)
        {
            printf("%10s%10s%10s%15d%10s\n",c[y].number,c[y].name,c[y].profession,c[y].classNo,c[y].date);
            break;
        }
    if(y==i)printf("无此数据");
}
void add()
{
    printf("请输入新数据\n");
    printf("请依次输入档案号 姓名 专业 班级 建档日期");
    getchar();//  吃掉回车
    scanf("%s%s%s%d%s",c[i].number,c[i].name,c[i].profession,&c[i].classNo,c[i].date);
    i++;//输入新数据放回结构体
}
void delete()
{
    printf("请输入要删除档案号  ");
    printf("请合法输入\n");
    // int k;
    char b[10];
    //...........同上
    scanf("%s",b);
    getchar();
    bool judge = false;
    if(b[0]=='A')//防止输入不合法
    {
        for(int k=0; k<i; k++)
        {
            if(strcmp(b, c[k].number) == 0)
            {
                for(int j=k; j<i-1; j++)
                {
                    strcpy(c[j].number, c[j+1].number);
                    strcpy(c[j].name, c[j+1].name);
                    strcpy(c[j].profession, c[j+1].profession);
                    c[j].classNo=c[j+1].classNo;
                    strcpy(c[j].date, c[j+1].date);
                }
                strcpy(c[i-1].number, "");
                strcpy(c[i-1].name, "");
                strcpy(c[i-1].profession, "");
                c[i-1].classNo=0;
                strcpy(c[i-1].date, "");
                judge = true;
                i--;
                break;
            }
        }
        if(judge) printf("删除成功\n");
        else printf("无此档案号\n");
    }
    else
        printf("输入错误，请重新选择功能!");
}

void tuichu()
{
    printf("感谢使用本系统");
    exit(0);
}
