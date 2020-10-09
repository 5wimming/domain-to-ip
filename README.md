# domain-to-ip

批量将域名转成ip，为了避免误差，该工具同时使用dig工具和python自带的gethostbyname_ex工具解析域名，并且最大化的收集所有ip。

安装dig
mac或者linux忽略此步骤，如果使用windows需要安装dig工具。
安装教程：https://blog.csdn.net/qq_34101364/article/details/108978948
安装完成后记得重启cmd或者ide。

脚本说明
首先使用dig工具解析域名的ip，通过参数dns_name可指定dns服务器(也可以不指定，默认为空)，如果指定得恰当（如域名所属公司自己的dns服务器），可避免将域名解析到cdn；如果dig无法解析时，会自动使用python自带的gethostbyname_ex函数解析，该函数可能将域名解析至cdn上。
对于一个域名有多个ip的，会使用；号隔开。
环境：python3
输入：domain.txt #域名列表，格式为一个url为一行
输出：domain2ip.txt #格式使用\t隔开，直接复制到excel实现自动分列
