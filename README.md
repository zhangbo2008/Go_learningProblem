# Go_learningProblem

go get问题:

cmd里面水下面命令
终极方案-goproxy代理
go env -w GOPROXY=https://goproxy.cn,direct
一条命令搞定






Fixing go: inconsistent vendoring in C:\Go\src:


https://stackoverflow.com/questions/58511588/fixing-go-inconsistent-vendoring-in-c-go-src








https://github.com/zhangbo2008/Go_learningProblem




我就使用者羡慕来学习o语言了
学这儿https://golang.google.cn/doc/


1.把gcc配置到环境变量path中.




2. go install 把文件编译成为.exe
go run 是直接运行.

  
3. go 的项目必须放到gopath/src/go 里面才行!!!!!!!







go语言的继承:

package main

import "fmt"

/*
继承
一个结构体嵌到另一个结构体，称作组合
匿名和组合的区别
如果一个struct嵌套了另一个匿名结构体，那么这个结构可以直接访问匿名结构体的方法，从而实现继承
如果一个struct嵌套了另一个【有名】的结构体，那么这个模式叫做组合
如果一个struct嵌套了多个匿名结构体，那么这个结构可以直接访问多个匿名结构体的方法，从而实现多重继承
*/

type Car struct {
    weight int
    name   string
}

func (p *Car) Run() {
    fmt.Println("running")
}

type Bike struct {
    Car
    lunzi int
}
type Train struct {
    Car
}

func (p *Train) String() string {
    str := fmt.Sprintf("name=[%s] weight=[%d]", p.name, p.weight)
    return str
}

func main() {
    var a Bike
    a.weight = 100
    a.name = "bike"
    a.lunzi = 2
    fmt.Println(a)
    a.Run()

    var b Train
    b.weight = 100
    b.name = "train"
    b.Run()
    fmt.Printf("%s", &b)
}




