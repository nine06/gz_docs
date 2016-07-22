##Client端命令
<br>
<hr style=" height:12px;border:none;border-top:4px solid #A9A9A9;" />  
客户端共包含10个常用命令。  
DataHub的数据结构由数据主题（ Repository ,简称 repo ）、数据项（ DataItem ，简称 item ）、数据包（ Tag ）三级结构构成，数据主题在DataHub网站创建，数据项、数据包在Client端发布。

###1、dp	数据池管理  
###2、ep 端口管理
###3、job 任务管理
###4、login 登录
###5、logout  退出
###6、pub  发布数据
###7、pull 获取数据
###8、repo  repo管理
###9、subs 订购
###10、version  版本
###11 、help  帮助

####说明
* 如果没有额外说明，所有的命令在没有错误发生时，不在终端输出任何信息，只记录到日志中。错误信息会打印到终端。
* 所有的命令执行都会记录到日志中，日志级别分[TRACE] [INFO] [WARNNING] [ERROR] [FATAL]。日志在DataHub网站监控中心查看。
* 参数支持全名和简称两种形式，例如--type等同于-t。详情见命令帮助。
* 参数赋值支持空格和等号两种形式，例如--type=file等同于--type file。
