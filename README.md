# sublimeText 3
### sublimeText3（中文版）换行无法自动缩进的问题
解决方案：
首选项->按键绑定 用户(preferences-key binding-user):输入以下内容
```javascript
[
    { "keys": ["enter"], "command": "auto_indent_tag", "context":
        [
            { "key": "setting.auto_indent", "operator": "equal", "operand": true },
            { "key": "selection_empty", "operator": "equal", "operand": true, "match_all": true },
            { "key": "selector", "operator": "equal", "operand": "punctuation.definition.tag.begin", "match_all": true },
            { "key": "preceding_text", "operator": "regex_contains", "operand": ">$", "match_all": true },
            { "key": "following_text", "operator": "regex_contains", "operand": "^</", "match_all": true },
        ]
    }
]
```
### sublimeText3 Tab缩进bug
解决方案：
首选项->按键绑定 用户(preferences-key binding-user):输入以下内容
```javascript
{ "keys": ["tab"], "command": "reindent", "context":
	[
	    { "key": "setting.auto_indent", "operator": "equal", "operand": true },
	    { "key": "selection_empty", "operator": "equal", "operand": true, "match_all": true },
	    { "key": "preceding_text", "operator": "regex_match", "operand": "^$", "match_all": true },
	    { "key": "following_text", "operator": "regex_match", "operand": "^$", "match_all": true }
	]
}
```
### Vue Syntax Highlight
vue代码高亮
``` javascript
ctl+shift+p
package install packages
Vue Syntax Highlight 
//安装成功后，重新打开vue文件（如果你之前开了vue文件，一定要关闭重新打开才会变为高亮)
```
### BracketHighlighter
类似于代码匹配，可以匹配括号，引号等符号内的范围
### AutoFileName
快速帮助你在文件中写路径
### HTML-CSS-JS Prettify
全能序列化
### less
高亮less代码
### All autocomplete
帮助查找css选择器对应的名称
### DocBlockr
用于自动注释
