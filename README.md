# 介绍 #
- 本代码是图书管理系统。面向管理员部分有学生的增删改查、书籍的增删改查、学生对书籍操作请求的确认；面向学生部分有书籍的查询、对书籍借阅、续借、归还的操作请求。
- 本代码前端额外添加了用户（学生）注册和登录的功能。
- 使用了基于python的django框架和bootstrap框架。

# 语义同义 #
在本代码的中文表述中，以下词汇会进行混用。它们是同义的：
- “用户”与“学生”
- “超级用户”与“管理员”
- “请求确认”与“审批”（只实现了approved，没有实现rejected）
- “BorrowAndReturn”与“bar”

# 测试步骤 #
1. 下载django相关库；
2. 修改book_management_system\settings.py内数据库相关字段DATABASES，连接到你的数据库；
3. 在book_management_system\下进入终端，进行表的生成与迁移。依次运行：
   - ```python manage.py makemigrations```
   - ```python manage.py migrate```
4. 生成管理员。运行：
   - ```python manage.py createsuperuser``` 
5. 运行程序：
   - ```python manage.py runserver```
6. 可以进入下面的URL。记得向学生表和书籍表内插入数据，和注册用户账号。

# 前端URL #
- [管理员页面](http://127.0.0.1:8000/admin/)-对学生和书籍的增删改查。
- [管理员审批页面](http://127.0.0.1:8000/confirm/)-对学生请求的确认。
- [用户主界面](http://127.0.0.1:8000/accounts/index/)-学生注册、登录、进行借续还请求。

# 额外说明 #
- 登录时间默认为一个小时，之后清空cookie。该参数在book_management_system\settings.py内，设置为SESSION_COOKIE_AGE=3600；
- 用户注册时，会检查学号是否与数据库内student.sno匹配。注册用户前请注意这点。
