--修改数据库连接配置
D:\Tomcat8.0\webapps\ssmCRUD\WEB-INF\classes\dbconfig.properties

jdbc.jdbcUrl=jdbc:mysql://localhost:3306/ssm_crud
jdbc.driverClass=com.mysql.jdbc.Driver
jdbc.user=root
jdbc.password=123456

--数据库
ssm_crud

--部门表

CREATE TABLE `t_dept` (
  `dept_id` int(11) NOT NULL AUTO_INCREMENT,
  `dept_name` varchar(255) NOT NULL,
  PRIMARY KEY (`dept_id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8

--员工表

CREATE TABLE `t_emp` (
  `emp_id` int(11) NOT NULL AUTO_INCREMENT,
  `emp_name` varchar(255) NOT NULL,
  `gender` char(1) DEFAULT NULL,
  `email` varchar(255) DEFAULT NULL,
  `d_id` int(11) DEFAULT NULL,
  PRIMARY KEY (`emp_id`),
  KEY `fk_emp_dept` (`d_id`),
  CONSTRAINT `fk_emp_dept` FOREIGN KEY (`d_id`) REFERENCES `t_dept` (`dept_id`)
) ENGINE=InnoDB AUTO_INCREMENT=2520 DEFAULT CHARSET=utf8


该模块是基于SpringMVC+Spring+Mybatis框架整合的对员工数据基本的CRUD操作，前端UI界面使用Bootstrap+jQuery，使用Eclipse+Maven作为项目管理工具；
主要的功能点是员工新增、查询，信息修改，员工单个删除、批量删除，分页显示；
主要技术点有分页查询显示，jQuery前端校验+JSR303后端校验，Ajax等

