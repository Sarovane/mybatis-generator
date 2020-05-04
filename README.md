# mybatis-generator

## 项目介绍

 此项目为mybatis的逆向工程，项目通过逆向工程，指定项目的数据库链接地址，用户名，密码。指定位置为项目根目录下面的generatorConfig.xml。

##  generatorConfig.xml文件

此文件中首先配置通用mapper所在目录，尽量和项目保持一致。之后配置数据库连接，数据库如果高版本的数据库链接是不一样的

```xml
<!--低版本mysql -->
com.mysql.jdbc.Driver
<!--高版本mysql -->
com.mysql.cj.jdbc.Driver
```

在url配置中高版本的connectionURL在连接后面需要添加后缀，使得mysql可以用来解析。在项目中是以高版本配置的。下面是需要添加的后缀。

```xml
?&amp;autoReconnect=TRUE&amp;useSSL=FALSE&amp;serverTimezone=GMT"                     
```

下面就是需要配置

- pojo所在的目录包，和项目保持一致。

- 对应的mapper.xml所在的文件目录。
- mapper对应的java映射的目录。

之后将需要映射的表进行配置，配置表所对应的表名即可。

配置结束以后，找到GeneratorDisplay.java文件。执行内部的MAIN方法，即可逆向生成所需要的配置。

