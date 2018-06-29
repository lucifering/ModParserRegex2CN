# ModParserRegex2CN
ModParser.lua文件的正则表达式汉化文档工程


#### 程序（其实就是简单的文本替换程序）从 【英汉对照.json】文件读取中英对译，然后处理对应的lua文件（ModParser-3_0.lua）。


把类似：
```
	["英文的正则表达式"] = "INC",
```
翻译为：
```
	["中文的正则表达式"] = "INC",
```

然后保存为 :处理_对应的lua文件名（如：处理_ModParser-3_0.lua）。
*如果你在目录下新建一个"特别保存路径.txt"，里面填写保存路径（比如：../../Modules/），那么程序会直接把处理后的文件保持原有名字保存到该路径下（不会加 "处理_"前缀）

其中没有对照的内容保存会在 【未处理.json】。


*注意所有文件 utf8编码。
*以后pob更新，ModParser变更的话，可以直接下载pob英文项目的这个文件，然后执行程序，查看哪些未处理，处理后自动翻译。



##### 需要处理的：

将【未处理.json】里面的东西，编写出对应的中文正则表达式（根据国服词缀的语法（注意：必须根据国服的用词和语法）），
填入【英汉对照.json】中。


在pob中，能够正确解析的词缀会以【绿色】显示（红色的就是不支持的 或者正则表达式错误的）。


![image](https://github.com/lucifering/ModParserRegex2CN/blob/master/ScreenShot/showline.png)





##### 另外一些词缀是英文版没有的 需要额外插入到对应的 就写入到 对应的txt中。

比如 ModNameList需要加入一句：
```
["总魔力保留"] = "ManaReserved",
```

那么 ModNameList.txt中就有一行  ：
```
["总魔力保留"] = "ManaReserved",
```
处理 处理_ModParser-3_0.lua的时候会插入到 “local modNameList = {”的后面




