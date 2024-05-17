# golang基础
## go与其他语言相比有什么好处
+ Go 代码的设计是务实的。每个功能和语法决策都旨在让程序员的生活更轻松。
+ Golang 针对并发进行了优化，并且在规模上运行良好。
+ 由于单一的标准代码格式， Golang 通常被认为比其他语言更具可读性。
+ 自动垃圾收集明显比 Java 或 Python 更有效，因为它与程序同时执行。

## golang使用什么数据类型
+ Method
+ Bool
+ String
+ Array
+ Slice
+ Struct
+ Pointer
+ Function
+ Interface
+ Map
+ Channel

## Go程序中的包是什么
包(pkg)是Go工作区中包含Go源文件或其他包的目录。源文件中的每个函数、变量和类型都存储在链接包中。每个 Go 源文件都属于一个包，该包在文件顶部使用以下命令声明：
```golang
package <pkgname>
// package main
// package user

// 可以使用import导入包
import <pkgname>
// import "user"
// import "service"
```

## go支持什么形式的类型转换，例如将浮点数转化为整数
显式类型转换
```golang
i := 40 //int
j := 41.1 // float64
sum := i + int(j) // j is converted to int
```

# 指针
## go 中指针的作用，给出指针示例
指针是一种变量，存储了另一个变量的内存地址，通过指针我们可以直接访问和修改变量的值，而不是对变量进行拷贝。
```golang
package main
import "fmt"
func swap(a,b *int) {
    temp := *a
    *a = *b
    *b = temp
}

func main() {
    x := 10
    y := 20
    fmt.Println("before swap:", x, y) // 10, 20
    swap(&x, &y)
    fmt.Println("After swap:", x, y) // 20, 10
}
```
我们定义了一个swap函数，接收两个指针作为参数，并通过指针交换了两个变量的值。在主函数中，我们通过取地址操作符&获取变量的指针，并将指针传递给swap函数。通过使用指针，我们实现了变量值的交换。

