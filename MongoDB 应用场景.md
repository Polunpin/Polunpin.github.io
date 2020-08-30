# MongoDB

+ 业务应用场景

> 解决三高需求：高并发、高效率存储和访问的需求、高可扩展性和高可用性的需求。

+ MongDB是一个开源、高性能、无模式的文档型数据库。

+ 特点：高性能、高可用、高扩展、丰富的查询支持

+ mongoDB应用场景特点：

  ``` tex
  1. 数据量大
  2. 写入操作频繁（读写都很频繁）
  3. 价值较低的数据，对事务性要求不高
  ```

对于这样的应用场景，我们则可以选择MongoDB来实现数据的存储。



+ 相关术语对比

| SQL术语/概念 | MongoDB术语/概念 | 解释/说明                           |
| :----------- | ---------------- | ----------------------------------- |
| database     | database         | 数据库                              |
| table        | collection       | 数据库表/集合                       |
| row          | document         | 数据记录行/文档                     |
| column       | field            | 数据字段/域                         |
| index        | index            | 索引                                |
| table joins  |                  | 表连接/MongoDB不支持                |
|              | 嵌入文档         | MongoDB通过嵌入式文档来替代多表连接 |
| primary key  | primary key      | 主键/MongoDB自动将_id字段设置为主键 |



同 `Redis `都是BSON 数据格式