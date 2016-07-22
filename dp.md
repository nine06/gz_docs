##dp	数据池管理
<br>
<hr style=" height:12px;border:none;border-top:4px solid #A9A9A9;" />     
###1.1 列出所有数据池
#####命令  

	datahub dp  
#####输出  
输出datahub数据池名称DPNAME ,每个数据池类型DPTYPE	  
  
		{%DPNAME    %DPTYPE}
	
#####例子  
	bash-3.2# datahub dp
	DATAPOOL            TYPE    
	------------------------
	datahubdp1          file    
	datahubdp2          file    
	datahubdp3          S3   
	datahubdp3          HDFS  


###1.2 列出某个具体数据池详情
#####命令  

	datahub dp  $DPNAME
#####输出	  
	输出datahub数据池名称DPNAME ,每个数据池类型DPTYPE	  
  
		%DPNAME          %DPTYPE        %DPCONN
	{%REPOSITORY/%DATAITEM:%TAG  %LOCAL_TIME        %T}
	
#####例子  
	bash-3.2# datahub dp
	DATAPOOL            TYPE    
	------------------------
	datahubdp1          file    
	datahubdp2          file    
	datahubdp3          S3   
	datahubdp3          HDFS  