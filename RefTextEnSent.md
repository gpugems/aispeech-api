## 英文句子评分refText设置规则 ##

  1. 英文单词序列,如 hello, how are you?
  1. 单词之间使用空格，允许标点有,;.'-?
  1. 重音和升降调标注： s:1表示重音，t:1表示升调。 如hello(s:1)表示重音，hello(s:1,t:1)表示升调。
  1. 单词之前要有空格。（比如hello.world是不允许的）
  1. 句子中必要的标点可以保留

## 英文识别语法设置 ##
  1. 只能小写字母和‘-
  1. 其他标点符号不支持
  1. 单词之间空格连接