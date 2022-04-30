# 爬虫
1. 爬虫框架
scrapy是一个框架，往里填充网址，用来爬取网站的
2. 爬虫渲染（有些页面需要js渲染)才能得到
2.1 可以使用requeests_html  
```python
from requests_html import HTMLSession
session = HTMLSession()
res = session.get("http://sec.didichuxing.com/present")
res.html.render() # 动态渲染页面
print(res.html.html) # 输出渲染之后的页面
```
requests_html 里面包含了pyppeteer(chromium的核)，可以模拟浏览器的操作，得到渲染。

3. 接口初探
4. 多线程操作
5. 使用代理
