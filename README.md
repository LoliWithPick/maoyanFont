# 2020猫眼动态字体反爬

## 原理

首先下载一个字体文件，手动写个 unicode-数字 对应关系。每次打开页面时，下载页面中的字体文件，获取页面字体的坐标数组，使用欧式距离判断字体相似度。相似度最高的则是最有可能的字体，目前做 100 次爬取，没有看到误差。

## Example:

	import requests
	import font

	url = 'https://maoyan.com/query?kw=复仇者联盟'
	resp = requests.get(url)
	font_dict = font.getFont(resp)
	for key in font_dict.keys():
        resp = resp.replace(key, font_dict[key])
	
