##应用场景一 ： 发布数据
<br>
<hr style=" height:12px;border:none;border-top:4px solid #A9A9A9;" /> 
下面介绍从 DataHub 网站发布名为 datahubrepo1 的数据主题，在客户端发布名为 datahubitem1 的数据集、名为 datahubtag1 的数据包。

###第一步 在 DataHub 网站发布名为 datahubrepo1 的数据主题
在网站上发布名为 datahubrepo1 的数据主题  

* 在 DataHub 网站（hub.dataos.io）上 我的发布 中查看，确认 datahubrepo1 的发布状态。  

###第二步 通过 longin 命令登录 Client 端
#####输入
	datahub login
#####输出	  
	login as: ********@*******.com
	password: ******
	DataHub : login success.  
	
###第三步 设置端口
端口（ Entry Point ）需要在发布数据时设置，供后续数据需求方在得到认证和鉴权后获得下载数据的入口。端口包括协议、ip 、port 三部分。设置协议为 http、 ip 为192.168.3.255、端口为1000。
#####输入（设置端口）  
	datahub ep http://192.168.3.255:1000
#####输出
 	OK. your entrypoint is: http://192.168.3.255:1000
	The entrypoint is setted successfully.  You can check whether it is available in one minute.
#####输入（确认端口有效性）
	datahub ep
#####输出
	http://192.168.3.255:8088 

	
  

###第四步 指定数据的存放目录（数据池， datapool ）
在本地创建一个名叫 datahubdp1 的数据池，指定存储类型为文件（ file ），路径为 /var/lib/datahub 。 

* 对于新用户，若无数据池，先创建数据池，现支持  file 、 S3 、 HDFS  等三种类型。对于已经创建过数据池的用户，可直接进入到第五步。  


#####输入  

	datahub dp create datahubdp1 file:///var/lib/datahub
#####输出
	DataHub : Datapool has been created successfully. 	Name:datahubdp1 Type:file Path:/var/lib/datahub. 

###第五步 在客户端发布名为 datahubitem1 的数据集
在客户度端发布名为 datahubitem1 的数据集，指定发布在数据主题datahubrepo1下，存放目录为数据池 datahubdp1 下的 decitem1 ，描述为"帮助文档样例 item 描述"，属性为私有，类型为批量（ batch ）类型。
#####输入
	datahub pub datahubrepo1/datahubitem1 datahubdp1://decitem1 -m="帮助文档样例item描述" -t=private -s=batch
#####输出
	Successed in publishing.

###第六步 在客户端发布名为 datahubtag 的数据包
在客户端指定发布名为 datahubtag1 的 tag 。 tag 的存放地址在其对应的 item 目录 datahubdp1://decitem1 下，文件名为 datahubtag.png ，发布时将其描述设置为帮助文档样例描述。
#####输入
	datahub pub datahubrepo1/datahubitem1:datahubtag1 datahubtag.png -m=“帮助文档样例tag描述”
#####输出
	 Successed in publishing.

####备注
至第六步完成，一个完整的数据发布过程就结束了。发布的结果后续查看 ：  
  
* 可通过命令行 datahub repo datahubrepo1/datahubitem1 查看。  
* 或者到 DataHub 网站 hub.dataos.io ，“我的发布”中查看。