# yyko1
# string infile;//代表文件名
ifstream in(infile);//ifstream定义了一个输入流in(文件流)，它被初始化从文件中读取数据
if (in)//
{
    //......
}
else
{
    cerr<<"cannot open this file: "<<infile<<endl;
}
in.close();//关闭文件
in.open(infile + ".copy");//关闭文件后，才可以打开另一个文件

ofstream out;//ofstream不与任何文件相关联，只定义了一个输出流out(文件流)
if (out)
{
}
else
{
    cerr<<"sorry"<<endl;
}
out.open(file + ".copy");
/*当一个fstream对象被销毁时，close函数会被自动调用*/
7.fstream out(argv[2])
9.#include<iostream>
#include<fstream>
#include<sstream>
#include<string>
#include<vector>
using namespace std;

istream& func(istream& is)
{
string buf;
while (is >> buf) 
    std::cout << buf << std::endl;
is.clear();
return is;
}

int main(int argc, char**argv)
{
/*两种文件流皆有open和close函数，之后视情况打开读或者写模式*/
string infile = "1.txt";//代表文件名
vector<string> vec;//声明一个vector
ifstream in(infile);//ifstream定义了一个输入流in(文件流)，它被初始化从文件中读取数据
istringstream iss("hello");
func(iss);
if (in)//
{
    string buf;
    while (in >> buf)//
    {
        vec.push_back(buf);
    }
}
else
{
    cerr<<"cannot open this file: "<<infile<<endl;
}
for (int i = 0;i < vec.size();++i)
{
    cout<<vec[i]<<endl;
}

return 0;
}
16
11.#ifndef CLASS_TYPENAME_H
#define CLASS_TYPENAME_H
 
template <typename T> class Blob
{
public:
	Blob();
	void check(size_t,const string&) const;
private:
	shared_ptr<vector<T>> data;
};
 
template <typename T> Blob<T>::Blob():data(make_shared(vector<T>)){}//类外定义构造函数
template <typename T> void Blob<T>::check(size_t i,const string& msg)//类外定义成员函数
{
	if (i > data->size())
	{
		throw out_of_range(msg);
	}
}

19.

#ifndef HAVE_H
#define HAVE_H
 
template <typename T> void Have(T &t)
{
	for (size_t i = 0; i < t.size(); ++i)
	{
		cout<<t[i]<<endl;
	}
}
#endif HAVE_H


#include <iostream>
#include <vector>
#include <list>
#include <string>
#include "Have.h"
using namespace std;
 
int main(int argc,char** argv)
{
	vector<int> vec1;
	vec1.push_back(2);
	vec1.push_back(3);
	Have(vec1);
	system("pause");
	return 0;
}

41.
#ifndef REU_TYPE_H
#define REU_TYPE_H
 
template <typename T> auto sum(const T&a,const T&b) ->decltype(a+b)//将函数的返回类型指定为a+b的类型
{
	return a+b;
}
#endif REU_TYPE_H
main.cpp

#include <iostream>
#include <vector>
#include <list>
#include <string>
#include "Reu_type.h"
using namespace std;
 
 
int main(int argc,char** argv)
{
	int a = 566669;
	int b = 595955;
	cout<<sum(a,b);
	cin.get();
	return 0;
}

62.

template <> int compare(const int&p1, const int&p2)
{
	//
}
12 1.

shared_ptr<string> p1;//定义一个智能指针，指向对象为string类型
shared_ptr<list<int>> p2;
 
vector<string> p1;//智能指针也是模版
vector<list<int>> p2;
10.正确无误
15.[](connection *p){ disconnect *p; }
17.(a)：不合法，ix不是new返回的指针

(b)：同上

(c)：合法，unique_ptr必须采用直接初始化

(d)：不合法，同(a)

(e)：合法

(f)：不合法，必须使用new返回的指针进行初始化，赋值和拷贝的操作也不包含get()方法。



18.release()函数的作用就是放弃对指针指向对象的控制权，但shared_ptr是多对一的关系，其他的智能指针仍然可以删除这个对象，所以这个函数的话对shared_ptr没意义
