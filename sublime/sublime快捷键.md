1.alt+shift+数字：分栏

ctrl+shift+数字:将光标所在的文件移动到栏数字

ctrl+数字：定位到栏数字

2.ctrl+k+b:打开或关闭侧边栏

3.ctrl+/:注释一行或取消一行注释

ctrl+shift+/:注释一个标签内的内容

4.ctrl+f:查找；ctrl+h:全部替换；ctrl+k:选中之后跳过

ctrl+d:选择单词; 全选:alt+f3；ctrl+shift+d:复制这行文本

ctrl+l:选中一行；ctrl+shift+向上/向下:向上或向下移动该行

ctrl+shift+m:选中容器内的内容,选中括号,选中父级······

ctrl+shift+;  ：移除与光标相关的父元素

ctrl+shift+':选择标签   

ctrl+alt+f：格式化

ctrl+shift+v:粘贴时保持缩进

ctrl+shift+回车:上一行添加内容

5.使用标签包裹一行：先选中想要被标签包裹的内容，然后alt+shift+w,然最后输入你想要的标签

6.ctrl+p:快速跳转__行/文件名/文件路径/#标签名（在html文件中）/@class名（在css文件中）/@函数名（在js文件中）

7.设置跳出右括号方法。（Enter）

``` 
{ "keys": ["enter"], "command": "move", "args": {"by": "characters", "forward": true}, "context":   

    [
        { "key": "following_text", "operator": "regex_contains", "operand": "^[)\\]\\>\\'\\\"]", "match_all": true }, 
    ]  
} 
```
