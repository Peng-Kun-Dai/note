go Test   

命令参数介绍  
* -bench regexp 对应执行相应的基准测试benchmark,example: go test -bench=.;
* -benchmem 显示内存使用情况
* -cover 开启测试覆盖率
* -run regexp 只运行与表达式相匹配的函数，example： go test -run=Xxx就是只运行含有Xxx开头的函数。
* -v 测试的详细信息

```
Fail: 测试失败，后续代码继续执行
FailNow： 测试失败，测试中断

SkipNow： 跳过测试，测试中断

Log： 输出信息
Logf: 


Skip: Log+SkipNow
Skipf: Logf+SkipNow

Error: Log+Fail
Errorf: Logf+Fail

Fatal: Log+FailNow
Fatalf: Logf+FailNow

Parallel: 代码可能并行运行时使用，测试多线程问题。

Example 需要在最后用注释的方式确认控制台输出和预期是不是一致的
 func Example_GetScore() {
        score := getScore(100, 100, 100, 2.1)
        fmt.Println(score)
        // Output:
        // 31.1
    }
```