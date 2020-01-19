# maoyanFont
## 例子
## Example:

	import requests
	import font

	url = 'https://maoyan.com/query?kw=复仇者联盟'
	resp = requests.get(url)
	font_dict = font.getFont(resp)
	for key in font_dict.keys():
        resp = resp.replace(key, font_dict[key])
	
