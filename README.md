# -golang-fileserver-Unity-WWW-
用golang 的http.FileServer()接口来实现一个简单的fileServer
golang 的代码如下
package main
import (
	"net/http"
	"fmt"
)
func main() {
	fmt.Println("start file server")
	http.Handle("/", http.FileServer(http.Dir("tmp/")))
	http.ListenAndServe(":8080", nil)
	fmt.Println("ServerClose")
}
然后 go install xxx.go

在bin目录可以看到生成了xxx.exe
在这个目录下创建tmp文件夹，然后往里面放几个测试文件
