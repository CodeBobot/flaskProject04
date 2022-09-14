1.模板
网页 ----》 模板引擎处理 ----》 模板
            render_template
{{ 变量 }}

{% if 条件 %}  {% endif %}
for、block、macro、with

{% extends '' %}
{% include '' %}
{% import '' %}
{% set username =  '' %}

过滤器：
。。。。
自定义过滤器
1.通过方法添加
2.装饰器

2.蓝图

1.flask-script
pip install flask-script

使用里面的Manager进行命令得到管理和使用：
manager = Manager(app=app)

manager.run()  ----->启动

使用命令在终端：
python app.py runserver

python app.py runserver -h 0.0.0.0 -p 5001

自定义添加命令：
@manager.command
def init():
    print('初始化')

python app.py init

2.数据库：
mtv
model   模型  ---->数据库
template    模板
view    视图

安装：
pip install pymysql

pip install flask-sqlalchemy

pip install flask-migrate

步骤：
1.配置数据库的连接路径
# mysql+pymysql://user:password@hostip:port/databasename
SQLALCHEMY_DATABASE_URI = 'mysql+pymysql://root:mysql@127.0.0.1:3306/flaskday04'

2.创建ext
    __init__.py中添加

    db = SQLALchemy() -----与app关联

    def create_app():
        ...
        db.init_app(app)

        return app
3.migrate:
