# vscode-rmarkdown
use vscode to traslate `rmd` to `html`, `pdf`, `beamer`, `docx`, `ppt`

**HINT:**<br>
1. 感谢金林老师提供的模板，原模板可见金林老师的github账号`jinlin82`。
2. 本模板修改于2022/5/21，所有配置都基于当时最新的软件版本，版本一致可以直接使用

## 使用说明
1. 文件夹`rmd-article-template-xmu`为完整的模板，直接在里面的`.Rmd`文件撰写文本内容。<br>
2. 用配置好的VSCode，打开该文件夹 **（注意是文件夹，不是单个文件）** ，在`.Rmd`页面按`ctrl + shift + p`，然后输入`run task`回车。在下拉框中选择相应的编译任务即可编译不同的文件，如：

 - 选择`rmd-html`，即编译成html文件
 - 选择`rmd-pdf`，即编译成A4大小pdf文件
 - 选择`rmd-beamer`，即编译成幻灯片版pdf文件
 - 选择`rmd-doc`，即编译成docx文件
 - 选择`rmd-ppt`，即编译成ppt文件

## 软件安装
暂时略

## VSCode配置
1. 打开VSCode下载相关拓展（暂时略，后续补充）。
2. 将三个json文件`settings.json`，`tasks.json`，`keybindings.json`，拷进VScode的用户文件`.\...\Code\User`下，该文件夹下一般有`globalStorage``History``snippets``workspaceStorage`等文件夹下。
3. 将三个json文件打开，依次修改掉其中对应的绝对路径，均改成自己软件的安装路径，修改后保存关闭文件。

## 右键安装
`vsCode_addright.reg`为右键安装注册表，将文件用记事本打开，将其中的路径改为自己的路径，修改完成后保存关闭文件，双击运行安装右键。
