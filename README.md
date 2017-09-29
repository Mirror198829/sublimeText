# sublimeText
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
