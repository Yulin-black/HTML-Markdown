# HTML-Markdown

官网下载：

https://www.mdeditor.com/
https://github.com/pandao/editor.md
https://pandao.github.io/editor.md/examples/index.html

markdown将上传的图片发送给后端处理后的返回值。

```python
@csrf_exempt
def wiki_upload(request):
    # 接收 markdown传来的图片对象
    file = request.FILES.get('editormd-image-file')
    """ 对文件对象处理后 """
    # 处理成功
    # 生成文件 url，返回给前端
    url = MEDIA_URL+ 'uploads/' + new_file.name
    result = {
        "success":1,
        "message":None,
        "url": url  返回给markdown的图片url地址,
    }
    # 处理失败
    result = {
        "success":0,
        "message": 失败理由,
        "url": None,
    }
    return JsonResponse(result)
```
