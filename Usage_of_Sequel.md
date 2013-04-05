Usage of Sequel
===============

需要经常翻看文档

## Database

## Dataset

1. 对于数据集，需要先获取数据，如`dataset.all`可以获取全部数据。获取之后才可以进行count，last等操作。

## Model

### Instance

1. new创建一个实例，可以有参数直接赋值。
2. refresh从数据库获取实例的更新
3. delete从数据库总删除
4. destroy可以执行钩子函数
5. save保存实例到数据库中
6. update更新数据库中的项目
