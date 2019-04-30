# Flask简介

Flask诞生于2010年，是用Python语言基于Werkzeug工具箱编写的轻量级Web开发框架。

Flask本身相当于一个内核，其他几乎所有的功能都要用到扩展（邮件扩展Flask-Mail，用户认证Flask-Login），都需要用第三方的扩展来实现。

其WSGI工具箱采用Werkzeug（路由模块），模板引擎则使用Jinja2，这两个也是Flask框架的核心。

Python是出名的框架要数Django，此外还有Flask、Tornado等框架。虽然Flask不是最出名的框架，但是Flask应该算是最灵活的框架之一，这也是Flask收到广大开发者喜爱的原因。

## Flask常用扩展包

- Flask-SQLalchemy：操作数据库；
- Flask-migrate：管理迁移数据库；
- Flask-Mail：邮件；
- Flask-WTF：表单；
- Flask-Bable：提供国际化和本地化支持，翻译；
- Flask-script：插入脚本；
- Flask-Login：认证用户状态；
- Flask-OpenID：认证；
- Flask-RESTful：开发REST API的工具；
- Flask-Bootstrap：集成前端Twitter Bootstrap框架；
- Flask-Moment：本地化日期和时间；
- Flask-Admin：简单而课扩展的管理接口的框架

> 扩展列表：http://flask.pocoo.org/extensions/

1. 中文文档（http://docs.jinkan.org/docs/flask/）
2. 英文文档（http://flask.pocoo.org/docs/0.12/）

## Flask与Django对比

- Django vs Flask

![](chapter3.assets/timg.jpg)

- Flask

![](chapter3.assets/timg-1556093679820.jpg)

## 框架之间的差别

- Django功能大而全，Flask只包含基本的配置

  Django的一站式解决的思路，能让开发者不用再开发之前就选择应用的基础设置上花费大量的时间。

  Django有模板、表单、路由、认证，基本的数据库管理等等內建功能。与之相反，Flask只是一个内核，默认依赖于两个外部库：Jinja2模板引擎和Werkzeug WSGI工具集，其他很多功能都是以扩展的形式进行嵌入使用。

- Flask比Django更灵活

- Flask在Django之后发布，现阶段有大量的插件和扩展满足不同需要

  Django发布于2005年，Flask创始于2010年。