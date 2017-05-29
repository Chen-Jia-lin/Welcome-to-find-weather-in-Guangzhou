# Welcome-to-find-weather-in-Guangzhou
This is our project for final exam
<!doctype html>
<html lang="zh-CN" >
    <head>
        <title>{{ the_title }}</title>
        <link rel="stylesheet" href="static/hf.css" />
    </head>
    <body>
        {% block body %}

        {% endblock %}
    </body>
</html>
{% extends 'base.html' %}

{% block body %}

<h2>{{ the_title }}</h2>

<form method='POST' action='/pick_a_date'>
<table>
<th colspan="2">请选取日期：</th>
<tr><td>日期: </td><td><input type="date" name="user_date" /></td></tr>
</table>
<p>准备就绪后, 单击此按钮：</p>
<p><input value='搞吧！' type='SUBMIT'></p>
</form>

{% endblock %}
{% extends 'base.html' %}

{% block body %}

<h2>{{ the_title }}</h2>

<p>您选取的是：</p>
<table>
<tr><td>日期：</td><td>{{ the_date }}</td></tr>
</table>

{% endblock %}
# -*- coding: utf-8 -*- 
from flask import Flask, render_template, request, escape

app = Flask(__name__)

@app.route('/')
@app.route('/entry')
def entry_page() -> 'html':
    """Display this webapp's HTML form."""
    return render_template('entry.html',
                           the_title='欢迎来到广州天气查询！')

@app.route('/pick_a_date', methods=['POST'])
def pick_a_date() -> 'html':
    """提取用户web 请求POST方法提交的数据（输入），不执行任何动作（处理），直接返回（输出）。"""
    user_date = request.form['user_date']	
    return render_template('results.html',
                           the_title = '以下是您选取的日期：',
                           the_date = user_date,
                           )

if __name__ == '__main__':
    app.run(debug=True)
    
  import requests
  url= "http://www.tianqi.com/plugin/"
  try:
     r=requests.get(url)
     r.raise_for_status()
     r.encoding=r.apprent_encoding
     print(r.text[:1000]
     
  
   


