# 安装mysql
## 配置mysql下的ini文件
重点是以下两个路径，其他的默认即可
```
basedir = D:\MySql5.6\mysql-5.6.24-winx64
datadir = D:\MySql5.6\mysql-5.6.24-winx64\data
```
## 安装mysql服务
切换到mysql路径下的bin目录下运行
```
mysqld -install
```
安装成功后，启动mysql
```
net start mysql
```
同理，停止命令
```
net stop mysql
```
# 导入数据库
 登陆数据库：
```
 mysql -h localhost -uroot -p
```
输出：
```
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.6.24-log MySQL Community Server (GPL)

Copyright (c) 2000, 2015, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
```
输入：
```
show databases
```
输出：
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| dcc_core        |
| dcc_job         |
| dcc_result         |
| dcc_webservice   |
| mysql              |
| performance_schema |
+--------------------+
11 rows in set (0.11 sec)
```
如果没有存在dcc_core\dcc_job\dcc_result\dcc_webservice,则先创建
创建dcc_core
```
create database dcc_core;
```
输出
```
Query OK, 1 row affected (0.00 sec)
```
切换数据库dcc_core
```
use dcc_core;
```
输出
```
Database changed
```
导入数据dcc_core
```
source D:\MySql5.6\mysql-5.6.24-winx641\bin\back_dcc_core20170315.sql
```
输出一堆
```
Query OK, 0 rows affected (0.00 sec)
.....
Query OK, 0 rows affected (0.00 sec)
```
创建dcc_job
```
create database dcc_job;
```
输出
```
Query OK, 1 row affected (0.00 sec)
```
切换数据库dcc_job
```
use dcc_job;
```
输出
```
Database changed
```
导入数据dcc_job
```
source D:\MySql5.6\mysql-5.6.24-winx641\bin\back_dcc_job20170315.sql
```
输出一堆
```
Query OK, 0 rows affected (0.00 sec)
.....
Query OK, 0 rows affected (0.00 sec)
```
创建dcc_result
```
create database dcc_result;
```
输出
```
Query OK, 1 row affected (0.00 sec)
```
切换数据库dcc_result
```
use dcc_result;
```
输出
```
Database changed
```
导入数据dcc_result
```
source D:\MySql5.6\mysql-5.6.24-winx641\bin\back_dcc_result20170315.sql
```
输出一堆
```
Query OK, 0 rows affected (0.00 sec)
.....
Query OK, 0 rows affected (0.00 sec)
```
创建dcc_webservice
```
create database dcc_webservice;
```
输出
```
Query OK, 1 row affected (0.00 sec)
```
切换数据库dcc_webservice
```
use dcc_webservice;
```
输出
```
Database changed
```
导入数据dcc_webservice
```
source D:\MySql5.6\mysql-5.6.24-winx641\bin\back_dcc_webservice20170315.sql
```
输出一堆
```
Query OK, 0 rows affected (0.00 sec)
.....
Query OK, 0 rows affected (0.00 sec)
```
导入数据库结束，查看数据库是否存在
查看数据库
```
show databases;
```
输出
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| dcc_core           |
| dcc_job            |
| dcc_result         |
| dcc_webservice     |
| mysql              |
| performance_schema |
+--------------------+
7 rows in set (0.00 sec)
```
查看数据库中是否存在表
切换数据库
```
use dcc_core;
```
输出
```
Database changed
```
查看dcc_core中的表
```
show tables;
```
输出
```
+--------------------------------+
| Tables_in_dcc_core             |
+--------------------------------+
| dcc_algorithm_algorithm        |
| dcc_algorithm_algorithmcode    |
| dcc_algorithm_algorithminput   |
| dcc_algorithm_algorithmoutput  |
| dcc_algorithm_assembly         |
| dcc_algorithm_interfaceversion |
| dcc_bom_class                  |
| dcc_bom_classgraph             |
| dcc_bom_fields                 |
| dcc_bom_instance               |
| dcc_bom_instancevalue          |
| dcc_bom_properties             |
| dcc_dicitem                    |
| dcc_dictionary                 |
| dcc_j_mrule                    |
| dcc_job_datacon                |
| dcc_job_job                    |
| dcc_job_jobitem                |
| dcc_job_model                  |
| dcc_job_rule                   |
| dcc_job_ruleitem               |
| dcc_model_model                |
| dcc_model_modelgraph           |
| dcc_model_modelrule            |
| dcc_model_modelruleitem        |
| dcc_model_rulegraph            |
| dcc_model_ruleinputs           |
| dcc_model_ruleiteminputs       |
| dcc_model_ruleitemoutputs      |
| dcc_model_ruleoutputs          |
| dcc_standard_datastandard      |
| dcc_standard_dictionary        |
| dcc_standard_dictionaryitem    |
| dcc_standard_standardfield     |
| dcc_standard_standardlayer     |
| dcc_standard_standardlayerset  |
+--------------------------------+
36 rows in set (0.02 sec)
```
依次查看其他数据库中的表
选择dcc_job
```
use dcc_job
```
查看表
```
show tables;
```
输出
```
+-------------------+
| Tables_in_dcc_job |
+-------------------+
| dcc_dicitem       |
| dcc_dictionary    |
| dcc_j_mrule       |
| dcc_job_datacon   |
| dcc_job_job       |
| dcc_job_jobitem   |
| dcc_job_model     |
| dcc_job_rule      |
| dcc_job_ruleitem  |
+-------------------+
9 rows in set (0.00 sec)
```
选择dcc_result
```
use dcc_result;
```
查看表
```
show tables;
```
输出
```
+------------------------+
| Tables_in_dcc_result   |
+------------------------+
| cdcp_checkmodelschema  |
| cdcp_checkruleassembly |
| dcc_dic_enum           |
| dcc_result_feature     |
| dcc_result_map         |
| dcc_result_nbmodel     |
| dcc_result_record      |
| dcc_result_zbresult    |
| dcc_t_ritem            |
| dcc_task_data          |
| dcc_task_item          |
| dcc_task_result        |
| dcc_task_rule          |
| dcc_task_task          |
| dcc_task_zb            |
+------------------------+
15 rows in set (0.00 sec)
```
选择dcc_webservice
```
use dcc_webservice;
```
查看表
```
show tables;
```
输出
```
+--------------------------+
| Tables_in_dcc_webservice |
+--------------------------+
| cdcp_checkmodelschema    |
| cdcp_checkruleassembly   |
+--------------------------+
2 rows in set (0.00 sec)
```
至此，数据库安装完毕，退出mysql
```
exit;
```

