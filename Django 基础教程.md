# Django 基础教程

## Review

`django-admin.py startproject myproject`

`python namage.py startapp myapp`

* 视图 views.py 与 路由 `urls.py`

***

## views & urls

### url name

```
#urls.py
url(r'^add/$', calc_views.add, name='add')

```
`name`相当与给这个网址一个身份标识,之后可以在 templates, models, views ……中被引用

***

## Templates

**建议在每个 app 的 templates 文件夹下再建一个与 app 同名的文件夹,将与当前 app 相关的 templates 放在其中**

* 模板建立以后可以被继承
*  {{ 变量 }}
*  {% %}

