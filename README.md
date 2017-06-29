## 前言
在测试的时候，特别是刚开始没有数据，或者要分页看效果时，需要大量的假数据，但是一个个的填充进去非常麻烦，遂写了一个`MySql`的脚本来帮忙自动填充。

## fill.sql 
这个文件主要是用来填充随机的数据，基本上的类型都有涉及，如需更改也非常方便。
第一个参数`num`指需要填充的数量，第二个参数`tbName`指要填充的表。

### 使用
直接执行[fill.sql](/fill.sql)的内容即可。

## make.sql 
这个文件主要是配合`schedule.sql`来使用，当我们增加索引，删除数据，或者没有自增的填充数据时，当我们对索引使用一段时间之后，我们的索引文件远比我们所需要的内容要多得多，因此我们需要定期对索引文件进行瘦身，遂配合定期脚本来执行，当然，这个文本定期一个月执行一次即可，因为执行时需要大量时间，也会锁表。

### 使用
先执行`make.sql`文件建立一个存储引擎，再根据[schedule.sql](/schedule.sql)中的提示配合执行即可。