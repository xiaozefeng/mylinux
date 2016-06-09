### CENTOS6.5安装与配置jdk
- 查询系统jdk版本

		 java -version
	<img src="http://7xv4mv.com1.z0.glb.clouddn.com/nike/1465465608466.png" width="573"/>
- 查看jdk安装的软件详细信息

		rpm -qa |grep java
	
- 卸载原来版本的jdk  

卸载原jdk（OpenJDK）注意下面文件的名称和上图查询出来的一致  

	rpm -e --nodeps tzdata-java-2013g-1.el6.noarch	
	rpm -e --nodeps java-1.6.0-openjdk-1.6.0.0-1.66.1.13.0.el6.i686
	rpm -e --nodeps java-1.7.0-openjdk-1.7.0.45-2.4.3.3.el6.i686

	
- 安装自己的jdk

		 rpm -ivh  jdk-7u45-linux-i586.rpm
		
- 查看jdk安装情况
 
 		java-version
		
	<img src="http://7xv4mv.com1.z0.glb.clouddn.com/nike/1465466060632.png" width="550"/>

- 配置环境变量
 	1. 修改系统环境变量文件
 	
 			 JAVA_HOME=/usr/java/jdk1.7.0_45
			 JRE_HOME=/usr/java/jdk1.7.0_45/jre
  			 PATH=$PATH:$JAVA_HOME/bin:$JRE_HOME/bin
			 CLASSPATH=:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar:$JRE_HOME/lib
			 export JAVA_HOME JRE_HOME PATH CLASSPATH  
	
		<img src="http://7xv4mv.com1.z0.glb.clouddn.com/nike/1465466706542.png" width="721"/>

			
 	
 	2. 让配置立刻生效
 	
 			 source /etc/profile
 	3. 查看系统PATH值
 	
	 		echo $PATH
	 		
	 	<img src="http://7xv4mv.com1.z0.glb.clouddn.com/nike/1465467164437.png" width="971"/>
