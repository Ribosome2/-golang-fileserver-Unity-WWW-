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

启动exe 
在随便一个浏览器输入地址 http://127.0.0.1:8080/
就可以看到浏览器列出了我们的文件列表


最后我们在Unity里面用这样的地址 string url = "http://127.0.0.1:8080/test.png";
经实验， 成功下载到了目标图片， 
嘻嘻， 可以做资源测试了
