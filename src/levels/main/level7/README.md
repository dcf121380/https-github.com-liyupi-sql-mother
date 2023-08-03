# 基础语法 - 条件查询 - 空值

## 教程

在数据库中，有时候数据表的某些字段可能没有值，即为空值（NULL）。

空值表示该字段的值是未知的、不存在的或者没有被填写的。在SQL查询中，我们可以使用 "IS NULL" 和 "IS NOT NULL" 来判断字段是否为空值或非空值。

空值的应用场景：假设你是一名考试老师，而数据表中的数据就像是你学生们的考试成绩。当某个学生没有参加考试或者成绩尚未出来时，他的考试成绩就是空值。你可以使用 "IS NULL" 来找出没有参加考试的学生，使用 "IS NOT NULL" 来找出已经有成绩的学生。



## 示例

假设有一张名为 `employees` 的数据表，它存储了员工信息，包括员工姓名（name）、年龄（age）、入职日期（hire_date）等：

数据表 `employees` ：

|   name   | age | hire_date  |
|----------|-----|------------|
|   小明   |  25 | 2020-01-01 |
|   小红   |  30 | 2020-02-15 |
|   小李   |  28 |   NULL     |
|   小张   | NULL| 2020-03-20 |

现在，我们使用 "IS NULL" 来查询出入职日期未填写的员工：

```sql
-- SQL查询语句
select name, age from employees where hire_date is null;
```

查询结果：

| name | age  |
| ---- | ---- |
| 小李 | 28   |



## 题目

请编写一条 SQL 查询语句，从名为 `student` 的数据表中选择出所有学生的姓名（name）、年龄（age）和成绩（score），要求学生年龄不为空值。