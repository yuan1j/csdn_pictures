### sqlserver安装与使用
1. 登录sql server官方下载界面：
https://www.microsoft.com/zh-cn/sql-server/sql-server-downloads  
下载Developer版本即可
![image](./picture/sqlserver_0_download.PNG)
2. 点击"SQL2019-SSEI-Dev.exe",安装  
选择基本
![image](./picture/sqlserver_1_install.PNG)
![image](./picture/sqlserver_2_install.PNG)
![image](./picture/sqlserver_3_install.PNG) 
![image](./picture/sqlserver_4_install.PNG) 
3. 安装SSMS（SQL Server Management Studio 管理工具）
紧接第2步，点击安装"SSMS(I)"，跳转网页后，点击"SQL Server Management Studio (SSMS) 18.11.1 的免费下载"下载SSMS。
（也可以点击右方链接，直接下载：https://aka.ms/ssmsfullsetup）
下载完成后，点击"SSMS-Setup-CHS.exe"安装
![image](./picture/ssms_0_install.PNG) 
![image](./picture/ssms_1_install.PNG) 
打开ssms：
![image](./picture/ssms_2_setup.PNG) 
点击连接
![image](./picture/ssms_3_setup.PNG) 
4. 创建新用户
新建登录名jerry
![image](./picture/ssms_4_createuser.PNG) 
设置用户名和密码
![image](./picture/ssms_5_createuser.PNG) 
点击"服务器角色"，勾选public和sysadmin
![image](./picture/ssms_6_createuser.PNG) 
点击"用户映射"，勾选所有数据库，角色成员身份，勾选public和db_owner
![image](./picture/ssms_7_createuser.PNG) 
然后点击"确定"
接下来开启SQL Server身份验证模式
点击服务器"jerry(SQL Server 15.0....)"，右键 属性，然后选择"安全性"，服务器身份验证选择"SQL Server和windows身份验证模式"，点击确定
![image](./picture/ssms_8_createuser.PNG) 
![image](./picture/ssms_9_createuser.PNG) 
点击服务器"jerry(SQL Server 15.0....)"，右键 "重新启动"
![image](./picture/ssms_10_createuser.PNG) 
点击“是”
![image](./picture/ssms_11_createuser.PNG)
测试是否可以登录
点击服务器，右键"连接"
![image](./picture/ssms_12_createuser.PNG)
身份验证选择 “SQL Server身份验证”，登录名和密码为刚刚设置的，然后点击“连接”
![image](./picture/ssms_13_createuser.PNG)
![image](./picture/ssms_14_createuser.PNG)
可以看到对象资源管理器有了一个新的连接，
![image](./picture/ssms_15_createuser.PNG)
我们可以点击旧连接，右键“断开连接”，便可保留我们自己刚新登录的用户
![image](./picture/ssms_16_createuser.PNG)
5. 创建测试数据
创建数据库：点击数据库，右键，“新建数据库”
![image](./picture/ssms_generate_data_0.PNG)
输入数据库名称：“test_db”
![image](./picture/ssms_generate_data_1.PNG)
创建表：点击表，右键，“新建”，“表”
![image](./picture/ssms_generate_data_2.PNG)
输入列名和数据类型，如下：
![image](./picture/ssms_generate_data_3.PNG)
点击左上方“保存”按钮，然后输入表名“test_table"，确定
![image](./picture/ssms_generate_data_4.PNG)
点击左上方“新建查询”，输入如下sql，点击上方“执行”，我们可以看到我们插入的数据
```sql
insert into  test_db.dbo.test_table(ftime,name,age) values(20200101,'张三',20),(20200101,'李四',25),(20200101,'王五',28);
select * from test_db.dbo.test_table;
```
![image](./picture/ssms_generate_data_5.PNG)

### powerbi报表服务器的安装和使用  
1. 登录powerbi官网： https://powerbi.microsoft.com/zh-cn/  
2. 进入Power BI 报表服务器下载界面：https://www.microsoft.com/zh-CN/download/details.aspx?id=56722  
下载"PBIDesktopRS_x64.msi"和"PowerBIReportServer.exe"
![image](./picture/powerbi_report_0_download.PNG)
3. 安装powerbi报表服务器
点击"PowerBIReportServer.exe"，安装
![image](./picture/powerbi_report_install_0.PNG)
安装的版本选择 免费版： “开发人员”
![image](./picture/powerbi_report_install_1.PNG)
![image](./picture/powerbi_report_install_2.PNG)
![image](./picture/powerbi_report_install_3.PNG)
![image](./picture/powerbi_report_install_4.PNG)
点击“配置报表服务器”
![image](./picture/powerbi_report_install_5.PNG)
连接
![image](./picture/powerbi_report_install_6.PNG)
点击“Web服务URL”，然后点击“应用”
![image](./picture/powerbi_report_install_7.PNG)
点击“数据库”，然后点击“更改数据库”
![image](./picture/powerbi_report_install_8.PNG)
点击下一步
![image](./picture/powerbi_report_install_9.PNG)
身份验证类型选择“SQL Server 账户”，输入自己的用户名和密码，测试连接成功后，点击下一步
![image](./picture/powerbi_report_install_10.PNG)
![image](./picture/powerbi_report_install_11.PNG)
凭据，身份验证类型选择“SQL Server凭据”，输入自己的用户名和密码，然后点击下一步
![image](./picture/powerbi_report_install_12.PNG)
点击下一步
![image](./picture/powerbi_report_install_13.PNG)
完成
![image](./picture/powerbi_report_install_14.PNG)
点击“Web门户URL”，然后点击“应用”
![image](./picture/powerbi_report_install_15.PNG)
点击连接“（http://jerry/Reports）”，输入windows用户和密码
![image](./picture/powerbi_report_install_16.PNG)
![image](./picture/powerbi_report_install_17.PNG)


4. 安装powerbi desktop
点击第2步下载的"PBIDesktopRS_x64.msi"
![image](./picture/powerbi_desktop_install_0.PNG)
![image](./picture/powerbi_desktop_install_1.PNG)
![image](./picture/powerbi_desktop_install_2.PNG)
点击安装
![image](./picture/powerbi_desktop_install_3.PNG)
点击完成
![image](./picture/powerbi_desktop_install_4.PNG)
此时会提示你需要下载”WebView2"，我们进入以下网址下载即可：
https://developer.microsoft.com/zh-cn/microsoft-edge/webview2/consumer/
![image](./picture/powerbi_desktop_install_5.PNG)
![image](./picture/powerbi_desktop_install_6.PNG)
点击“MicrosoftEdgeWebview2Setup.exe"，即可自动安装
然后我们重新打开powerbiDesktop，注意：第一次打开要以管理员身份运行，否则后面获取数据可能报无法连接的异常（参考： https://docs.microsoft.com/zh-cn/power-bi/connect-data/desktop-error-launching-desktop#resolve-issues-when-connecting-to-sql-server）
![image](./picture/powerbi_desktop_install_7.PNG)
点击获取数据
![image](./picture/powerbi_desktop_install_8.PNG)
选择，数据库——SQL Server数据库，点击连接
![image](./picture/powerbi_desktop_install_9.PNG)
服务器：输入我们的电脑名，数据库：输入我们自己创建的test_db
![image](./picture/powerbi_desktop_install_10.PNG)
windows凭据使用其他凭据，输入我们登录电脑的用户名和密码
![image](./picture/powerbi_desktop_install_11.PNG)
然后左侧选择 数据库，输入我们数据库的用户名和密码，然后点击连接
![image](./picture/powerbi_desktop_install_12.PNG)
点击确定，使用不加密连接访问数据源
![image](./picture/powerbi_desktop_install_13.PNG)
勾选我们之前创建的测试表"test_table"，可以预览看到之前insert进去的测试数据，然后点击"加载"
![image](./picture/powerbi_desktop_install_14.PNG)
右侧“字段”栏，选择“test_table”，然后依次勾选“ftime",“name”，"age",
![image](./picture/powerbi_desktop_install_15.PNG)
右侧“可视化”栏，选择“ftime”，右键选择“不汇总”，选择“age”，右键“不汇总”，这样就是一个普通表格形式了。
![image](./picture/powerbi_desktop_install_16.PNG)
接下来，我们将其发布到我们的“报表服务器”上，点击上方“文件”
![image](./picture/powerbi_desktop_install_17.PNG)
另存为，选择“PowerBi报表服务器”
![image](./picture/powerbi_desktop_install_18.PNG)
输入我们第3步的url：“http://jerry/Reports”
![image](./picture/powerbi_desktop_install_19.PNG)
点击确定
![image](./picture/powerbi_desktop_install_20.PNG)
可以看到“保存成功”，我们点击前往，或浏览器输入powerbi报表服务器的url “http://jerry/Reports”
![image](./picture/powerbi_desktop_install_21.PNG)
可以看到，powerBi的数据已经在web端展现
![image](./picture/powerbi_desktop_install_22.PNG)

参考：
PowerBI开发者文档： https://docs.microsoft.com/zh-cn/power-bi/developer/

关于数据源刷新，权限设置等，可参考官方文档：

