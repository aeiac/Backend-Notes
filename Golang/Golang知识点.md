

<h1 style="text-align: center;font-weight: bold; font-size: 2em;">Golang入门基础</h1>

------

## 1、Golang的常用个关键字	

- **详情：**Go语言设计非常简洁，只有25个关键字，用于控制程序结构，声明变量，定义函数等，举例常用关键字。

- **变量与类型声明：**

  1. **var：**声明变量，可指定或自动推断（ var x int = 10  |  var x = 10 ）
  2. **const：**声明变量，不可更改的值  ( const x = 3.14) 
  3. **type：**定义新类型 ，如结构体，接口，别名等

- **函数与控制流：**

  1. **func：** 声明函数与方法

     ```go
     func add (a int , b int) int { return  a + b }
     ```

  2. **if：**条件判定

     ```go
     if a > = 2 { } else {}
     ```

  3. **range：**遍历数组，切片，映射

     ```go
     for k ,v:= range map{}
     ```

  4. **goto：** 跳转到指定标签，注意作用域

     ```go
     goto End   End：loading......
     ```

- **并发编程：**

  1. **go：**启动 Goroutine（轻量级并发）

  2. **chan：**声明通道 用于 Goroutine 通信

  3. **select：**监听多个通道操作，类似于 switch 但专用于通道 谁快谁触发

     ```go
     ch1 := make(chan string)  ch2 := make(chan string)
     	go func() {
     		time.Sleep(2 * time.Second)
     		ch1 <- "来自 ch1 的消息"
     	}()
     	go func() {
     		time.Sleep(1 * time.Second)
     		ch2 <- "来自 ch2 的消息"
     	}()
     	select {
     	case msg1 := <-ch1:
     		fmt.Println("收到：", msg1)
     	case msg2 := <-ch2:
     		fmt.Println("收到：", msg2)
     	}
     ```

- ###  **接口与结构体：**

  1. **inteface：**	定义接口，抽象方法

     ```go
     type writer inteface { witer () }
     ```

  2. **struct：**定义结构体符合数据类型

     ```go
     type User struct { Name string }）
     ```

- **fallthrough：** 在 `switch` 中强制执行下一个 `case`（默认不穿透）

- **map：** 声明映射（键值对集合）

  ```go
  （m := make(map[string]int)）
  ```

