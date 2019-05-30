# CPP-Quiz
考虑到编程语言有进入高考的倾向，特制作一系列C++题库供参考练习。 \
以下题型如无特别说明均使用C++11标准。 \
为了大家的刷题体验这里暂不提供答案。 \
如有疑问请提ISSUE \
欢迎大佬前来PULL REQUEST 

## 警告：本题库  ~~难度较低~~ 不适合新手入门，请谨慎入坑。 


### 1 ★☆	（重载函数） 

已知声明 ` auto &&p = NULL; `\
若以下重载函数声明同时存在，则f(p)会调用的函数是？ \
A. template<class T> void f(T *); \
B. void f(int &&); \
C. void f(nullptr_t &&); \
D. void f(void *); 

### 2 ★★	（变量的定义和初始化）
已知变量x的定义： 
```
static int x = (x+3)/2+1/2; 
```
则定义后x的值是？ \
A. 0 \
B. 1 \
C. 2 \
D. 4 

### 3 ★★☆	（auto与模板实参推导）
关于语句 
```
auto &&x = std::max(0.5, 1);
```
请问以下说法正确的是？ \
A. decltype(x)表示的类型是double && \
B. x是将亡值 \
C. 运行时x将会在语句结束后成为悬垂引用 \
D. 这段代码会引发一个编译错误 

### 4 ★	（左值、纯右值、将亡值的概念）
已知定义
```
int x;
int f();
int &&y=f();
```
以下哪个表达式是纯右值？ \
A. x \
B. y \
C. f \
D. f() 

### 5 ★★	（未定义行为）
以下代码片段中哪个选项不会导致潜在的未定义行为？ \
A. ` f(std::shared_ptr<int>(new int(1)), std::shared_ptr<int>(new int(2)));  ` \
B. ` std::vector<std::unique_ptr<std::string>> vec; ` \
C. ` std::copy (std::vector<int>{ 1, 2, 3, 4, 5 }.begin(), std::vector<int>{ 1, 2, 3, 4, 5 }.end(), std::ostream_iterator<int>(std::cout)); ` \
D. ` catch(std::auto_ptr<std::string> e) { cerr << *e <<endl; throw; } `
### 6 ☆	（默认构造函数）
以下哪个语句不能正确用默认构造函数创建对象（类型为T）？ \
A. T a; \
B. auto b = T(); \
C. T c{}; \
D. T d(); 

### 7 ☆		（std::map和范围for循环）
已知定义
```
std::map<std::string, int> kv; 
```
则范围for循环
```
for(auto x:kv){}
```
中x的静态类型是？ \
A.	std::string \
B.	int \
C.	std::pair<std::string, int> \
D.	std::pair<std::string, int>::iterator 

### 8 ★☆	（命名空间和前置声明）
```
namespace X {
    struct Y {
        void foo(struct Z *);
    };
}
```
中前置声明的Z是？ \
A. X::Y::foo::Z（foo的局部类） \
B. X::Y::Z（Y的嵌套类） \
C. X::Z（在X命名空间内和Y并列） \
D. ::Z （在全局命名空间）

### 9 ★★	（函数、数组、指针的const限定）
假如已有别名 ` typedef float vec3_t[3]; ` \
再定义函数 ` float VectorLength(const vec3_t v); ` \
请问得到的函数签名是？ \
A. VectorLength(const float *const v) \
B. VectorLength(float * const v) \
C. VectorLength(const float * v) \
D. VectorLength(float * v)

### 10 ★	（C++11综合）
已知定义 ` int a,b,c,d; ` 下列语句能为a,b,c,d分别赋值0的是？ \
A. ` [&](){a=b=c=d=0;}; ` \
B. ` std::tie(a, b, c, d) = std::make_tuple(0, 0, 0, 0); ` \
C. ` for(auto &x : {a,b,c,d}) { x=0; } ` \
D. ` struct A { int &x; int &y; int &m; int &n; }; A {a, b, c, d} = { 0, 0, 0, 0 }; `

### 11 ★★	（sizeof）
根据C++标准，下列关于sizeof（下称大小）的说法一定正确的是？ \
A. 派生类的大小 >= 其所有基类的大小之和 \
B. 在C++中所有指针的大小都相等，且等于 ` sizeof(void *) ` \
C. ` sizeof(bool) >= sizeof(char) ` \
D. 联合体（union）的大小等于它所有的成员中占用空间最大的一个成员的大小
