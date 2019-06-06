# 你应该试试 pipenv

[pipenv](https://docs.pipenv.org/en/latest/) 可以用来替代 pip 和 virtualenv，项目的目标是将包管理中最好的特性带到 Python 的世界，
pipenv 使用 Pipfile 和 Pipfile.lock 作为配置文件，同时支持 Python2 和 Python3 的环境初始化。

## 安装
+ Mac 使用 `brew install pipenv`
+ pip 使用 `pip install --user pipenv`

## 指定 Python 版本
+ Python 3 `pipenv --python 3`
+ Python3.6 `pipenv --python 3.6`
+ Python 2.7.14 `pipenv --python 2.7.14`

## 项目初始化、包的安装和删除
+ 项目初始化 `pipenv install`
+ 安装新包 `pipenv install Django requests`
+ 删除包 `pipenv uninstall Django`
+ 使用 requirements.txt `pipenv install -r requirements.txt`

## 进入项目虚拟环境
+ 使用命令 `pipenv shell`
+ 单次运行 `pipenv run python manage.py runserver`

## Pipfile 样例
```ini
[[source]]
url = "https://pypi.python.org/simple"
verify_ssl = true
name = "pypi"

[packages]
requests = "*"


[dev-packages]
pytest = "*"
```

国内建议将 url 修改为阿里云的源 `url = "https://mirrors.aliyun.com/pypi/simple"`

## 优点
1. 无需手动管理 pip 和 virtualenv。
2. 可以指定 python 版本。
3. 无需使用 `pip freeze` 生成 requirements.txt

## 缺点
部署环境生成 pipfile.lock 很慢，使用 `pipenv install --skip-lock` 先安装包，后续使用 `pipenv lock` 生成 pipfile.lock。

更多使用请参考 [官方文档](https://docs.pipenv.org/en/latest)
