## 一、初识Go
1. 每个Go源代码文件开头都是一个**package**声明要生 成Go可执行程序，必须建立一个名字为**main**的包，   并在该包中包含一个**main()函数**。
2. Go语言的main()函数不能带参数，也不能定义返回值。
3. 命令行传入的参数在**os.Args**变量中保存，如果需 要命令行参数，使用**flag**包。
4. 函数以关键字func开头；Go支持多返回值，并不是所有的都需要返回值都必须赋值，未明确的返回值被设置为默认值。
   ```
   func 函数名(参数列表)(返回值列表)
   ```
5. **go run**将编译、链接、运行合并为一步；**go build**生成编译结果，不运行；**6g和6l**是64位的Go编译器和链接器；**8g和8l**是32位的编译器和链接器。
6. xxx_test.go是对xxx.go的单元测试。
## 二、顺序编程
---
#### 变量
1. 对于纯粹的变量声明，Go语言引入var，将类型信息放变量名之后：
```
   var v1 int
   var v2 string
   var v3 [10]int //数组
   var v4 []int   //数组切片
   var v5 struct{
       f int
   }
   var v6 *int    //指针
   var v7 map[string] int //map,key为string类型,value为int类型
   var v8 func(a int) int
```
2. var还可将需要声明的变量放一起：
```
   var (
       v1 int
       v2 string
   )
```
3. 变量初始化，已声明的变量不能出现在**:=**左侧：
```
var v1 int = 10
var v2 = 10  //编译器自动推到v2
v3 := 10     //编译器自动推到v3
```
4. 变量赋值，实现多重赋值，如交换i和j的语句：
```
var v1 int
v1 = 123
i,j = j,i
```