*************************************************
*����:Eritque arcus                             *
*Time:2020/2/5        							*
*CSDN��ַ:https://me.csdn.net/qq_40832960 		*
*����:��дini���п�              				*
*�人����!!!        							*
*************************************************

ʹ��˵��:

����̬����Զ�д�κκ�׺��ini��ʽ�������ļ��������к�׺����û�к�׺��������.xxx,.sdasa,.dasasf�ȣ�ֻҪ����Ϊini��ʽ��
����ʹ������������(�ص㣺�������������728KB)
����2��������


ReadInI(path,F,S)//��
path�Ƕ�ȡ�ļ���·���������Ǿ���·�����̷���ʼ��
F�ǽ���
S�Ǽ���
���ؼ�ֵ


WriteInI(path,F,S,Z)//д
path�Ƕ�ȡ�ļ���·���������Ǿ���·�����̷���ʼ��
F�ǽ���
S�Ǽ���
Z��д��ֵ
���ؼ�ֵ



C++ʾ������:
[code]
#include <Windows.h>

typedef char* (WINAPI* ptrSub) (char*, char*, const char*);//���庯��
typedef bool (WINAPI* ptrSub2) (char*, char*, char*, const char*);//���庯��

int main(){
	HMODULE hMod = LoadLibraryA("InI.dll");//�������п�
	if (hMod == NULL)
	{
		cout << "Error: �Ҳ���InI.dll�ļ�";
		return 0;
	}
	readinia = (ptrSub)GetProcAddress(hMod, "ReadInI");//���뺯��
	if (readinia == NULL)
	{
		cout << "InI.dll�ļ���";
		return 0;
	}
	wini = (ptrSub2)GetProcAddress(hMod, "WriteInI");//���뺯��
	if (wini == NULL)
	{
		cout << "InI.dll�ļ���";
		return 0;
	}
	char* read=readinia("D:\\aa.sadas","afasf","fasfa");
	bool write=wini("d:\\sdasdas.fsa","sadsf","fasfd");
	return 0;
}
[/code]


����:

char*��string
char* a;
string b(a);//����string���ع�

string��char*
string a;
char* b=a.c_str();//��a.data()��
