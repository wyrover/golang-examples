# golang-examples


这个项目放在 github 上，所以项目的路径是 `%GOPATH%/src/wyrover/golang-examples`


- example01 基本 golang 例子

第一个例子写一个命令行程序

```
cd %GOPATH%/src/wyrover/golang-examples/example01
dep init
```

添加一个包

```
dep ensure -v -add github.com/fatih/color
```


> dep 更新是相当的慢，还的挂代理，shadowsocks 的 socket5 转 http 代理，再设置环境变量
> 转 http 带来用 cow 实现， http 代理地址 `http://127.0.0.1:7777`， 在 cow 配置文件里设置

设置环境变量
```
set http_proxy=http://127.0.0.1:7777
set https_proxy=http://127.0.0.1:7777

```

设置 git 代理

```
git config --global http.proxy 'socks5://127.0.0.1:1080'
git config --global https.proxy 'socks5://127.0.0.1:1080'
```

> dep 安装相关的包，还的有 `main.go` 文件存在


```go
package main

import (
    "fmt"

    "github.com/fatih/color"
)

func main() {
    fmt.Println("Hello World!")

    color.Cyan("Prints text in cyan.")
}
```

```
go run main.go
```

测试 `dep ensure -v`，删除 vendror 目录，再次执行 `dep ensure -v` 更新包





