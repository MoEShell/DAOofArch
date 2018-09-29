# Arch 中文输入问题
##  表现
 * konsole 无法将中文字符当单个字符处理，一个中文字符对应两个或三个英文字符，konsole 每次仅处理一个字符。在删除字符时最明显
 * Intellij Idea 无法输入中文字符
## 解决
 * 在 .bash_profile 中加入
 > export LC_CTYPE=zh_CN.UTF-8
