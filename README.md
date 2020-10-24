# INIReader #
![Github](https://img.shields.io/badge/Author-Nambers-blue) ![Github](https://img.shields.io/badge/Time-2020/2/5-green)

功能:读写ini运行库

武汉加油!!!


使用说明:

本静态库可以读写任何后缀的ini格式的配置文件【必须有后缀不能没有后缀，可以是.xxx,.sdasa,.dasasf等，只要内容为ini格式】
本库使用易语言制作(特点：运行慢，体积大728KB，不过相比于自己造轮子要方便)
内置2个函数：


`ReadInI(path,F,S)//读`
path是读取文件的路径，必须是绝对路径【盘符开始】
F是节名
S是键名
返回键值


`WriteInI(path,F,S,Z)//写`
path是读取文件的路径，必须是绝对路径【盘符开始】
F是节名
S是键名
Z是写入值
返回键值



C++示例代码:
```C++
#include <Windows.h>

typedef char* (WINAPI* ptrSub) (char*, char*, const char*);//定义函数
typedef bool (WINAPI* ptrSub2) (char*, char*, char*, const char*);//定义函数

int main(){
	HMODULE hMod = LoadLibraryA("InI.dll");//导入运行库
	if (hMod == NULL)
	{
		cout << "Error: 找不到InI.dll文件";
		return 0;
	}
	readinia = (ptrSub)GetProcAddress(hMod, "ReadInI");//导入函数
	if (readinia == NULL)
	{
		cout << "InI.dll文件损坏";
		return 0;
	}
	wini = (ptrSub2)GetProcAddress(hMod, "WriteInI");//导入函数
	if (wini == NULL)
	{
		cout << "InI.dll文件损坏";
		return 0;
	}
	char* read=readinia("D:\\aa.sadas","afasf","fasfa");
	bool write=wini("d:\\sdasdas.fsa","sadsf","fasfd");
	return 0;
}
```


附赠:

char*到string
```C++
char* a;
string b(a);//利用string的重构
```

string到char*
```C++
string a;
char* b=a.c_str();//或a.data()等
```
