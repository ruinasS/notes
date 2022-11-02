---
title: GitHub自定义徽章
time: 2022-10-31 21:51:00
tab: 
---

GitHub自定义徽章
==

在markdown文本中添加自定义徽章可更直观说明项目的相关信息，这里主要使用**Shields**来说明

[Shields](https://shields.io/)是帮助在markdown文件中生成自定义徽章的项目，可通过该项目提供的链接语法来制定想要的徽章

比如：

![shields: hello](https://img.shields.io/badge/shields-hello-ff69b4)
```markdown
![shields: hello](https://img.shields.io/badge/shields-hello-ff69b4)
```

以下说明一些简单的徽章的定制



# 1.静态徽章

两种语法：

```markdown
https://img.shields.io/badge/<LABEL>-<MESSAGE>-<COLOR>
https://img.shields.io/static/v1?label=<LABEL>&message=<MESSAGE>&color=<COLOR>
<LABEL>指定标题
<MESSAGE>指定信息
<COLOR>指定颜色
```

项目网站对颜色有以下的示例：

![image-20221101135006707](https://raw.githubusercontent.com/ruinasS/imgs/main/image-20221101135006707.png)

可用表示颜色的词也支持rgb形式

如：

![eg1](https://img.shields.io/badge/eg1-badge-red)
![eg2](https://img.shields.io/static/v1?label=eg2&message=static&color=blue)

```markdown
![eg1](https://img.shields.io/badge/eg1-badge-red)
![eg2](https://img.shields.io/static/v1?label=eg2&message=static&color=blue)
```



# 2.样式

在你的徽章代码后加上`?style=<STYLE>`可定义样式，共有五种样式

![eg3](https://img.shields.io/badge/style-plastic-important?style=plastic)
![eg4](https://img.shields.io/badge/style-flat-important?style=flat)
![eg5](https://img.shields.io/badge/style-flat_square-important?style=flat-square)
![eg6](https://img.shields.io/badge/style-for_the_badge-important?style=for-the-badge)
![eg7](https://img.shields.io/badge/style-social-important?style=social)

```markdown
![eg3](https://img.shields.io/badge/style-plastic-important?style=plastic)
![eg4](https://img.shields.io/badge/style-flat-important?style=flat)
![eg5](https://img.shields.io/badge/style-flat_square-important?style=flat-square)
![eg6](https://img.shields.io/badge/style-for_the_badge-important?style=for-the-badge)
![eg7](https://img.shields.io/badge/style-social-important?style=social)
```



# 3.动态徽章

需要调动其它数据，随着你的项目或数据的变化自动更改的徽章，Shield主要通过json、xml、yaml来调用数据，具体用法参考网站示例



# 4.其它

若需对徽章进行更进一步的定制，如调整徽章左侧的颜色、添加图标等等，可参考网站的语法介绍：

[Shields.io: Quality metadata badges for open source projects](https://shields.io/)



除**Shields.io**外，还有其它的自定义徽章网站项目：

[Badgen - Fast badge generating service](https://badgen.net/)：与Shields类似的，个人感觉语法更“简单”，动态徽章的参考较多

[For the Badge](https://forthebadge.com/)：与另两个不同，色彩定制更简单，但好像没有动态徽章
