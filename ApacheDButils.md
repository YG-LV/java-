# Apache Commons DButils

## Handler用法简介

|      Handler      | 语法                                                         | 返回值                         | 说明                                                         |
| :---------------: | ------------------------------------------------------------ | ------------------------------ | ------------------------------------------------------------ |
|  BeanMapHandler   | BeanMapHandler<键类型,值类型> beanMap = new BeanMaphandler<>(值类型.class,键取值列); | Map<Object,值类型>             | 可读取数据库多行多列的值，键类型通用Object，值类型要求类的属性名与搜索出的表的列名一致，否则返回null，键值默认为第一列可选，键值不能重复，重复返回重复的最后一条记录 |
|   Keyed Handler   | Map<Object,Map<String,Object>> keyed = new KeyedHandler<>(键取值列); | Map<Object,Map<String,Object>> | 可读取数据库多行多列的值，内嵌Map固定类型<String,Object>，外部Map键值类型通用Object，键值默认为第一列可选，键值不能重复，重复返回重复的最后一条记录 |
| ArrayListHandler  | ArrayListHandler arrayList = new ArrayListHandler();         | List<Object[]>                 | 可读取数据库多行多列的值，返回Object数组的集合，List内部为Object数组 |
| ColumnListHandler | ColumnListHandler<Object> clumnList = new ColumnListHandler(列取值); | List<Object>                   | 可读取数据库多行单列的值，返回Object集合，通用Object类型，列可取数字或列名 |
|  MapListHandler   | MapListHandler mapList = new MapListHandler();               | List<Map<String,Object>>       | 可读取数据库多行多列的值，返回Map的集合，内嵌Map固定类型<String,Object>，键值为列名 |
|   ArrayHandler    | ArrayHandler array = new ArrayHandler();                     | Object[]                       | 可读取数据库单行多列的值，返回Object数组，数据库查询多行时返回第一行数据 |
|    BeanHandler    | BeanHandler<值类型> bean = new ArrayHandler(值类型.class);   | 值类型                         | 可读取数据库单行多列的值，返回多个值的类型，值类型要求类的属性名与搜索出的表的列名一致，否则返回为null |
|  BeanListHandler  | BeanListHandler<值类型> beanList = new BeanListHandler(值类型); | List<值类型>                   | 可读取数据库多行多列的值，返回值类型的集合，值类型要求类的属性名与搜索出的表的列名一致，否则返回为null |
|    MapHandler     | MapHandler map = new MapHandler();                           | Map<String,Object>             | 可读取数据库单行多列的值，返回Map集合，固定类型<String,Obejct>,键值为列名 |
|   ScalarHandler   | ScalarHandler sclar = new ScalarHandler(列取值);             | Object                         | 可读取数据库单行单列的值，返回Object单个值，列取值可取数字或列名，数据库查询多行多列时，无列取值默认返回第一行第一列的第一个值 |
