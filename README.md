# vscode-rmarkdown
use vscode to traslate `rmd` to `html`, `pdf`, `beamer`, `docx`, `ppt`

**HINT:**<br>
1. 感谢金林老师提供的模板，原模板可见金林老师的github账号`jinlin82`。
2. 本模板修改于2022/5/21，所有配置都基于当时最新的软件版本，版本一致可以直接使用。

## 软件安装
1. 安装Anaconda：官网 https://www.anaconda.com/products/distribution#Downloads 下载对应系统的Anaconda并安装，记得勾选`add to path`

2. 安装pandoc：启动`Anaconda Prompt`， 输入以下命令安装pandoc
  ```{python}
  conda install Pandoc
  ```
  
  打开`cmd`，输入以下命令，打开返回路径文件夹，比如我的是`D:\software\Anaconda3\Scripts\pandoc.exe`，那就打开`D:\software\Anaconda3\Scripts`文件夹。
  ```
  where pandoc
  ```
 
3. 安装pandoc-crossref:从 https://github.com/lierdakil/pandoc-crossref/releases 下载对应系统的压缩包，比如windows系统是`pandoc-crossref-Windows.7z`，解压后，将其中的`pandoc-crossref.exe`拷贝至步骤2打开的文件夹下，如我的是`D:\software\Anaconda3\Scripts`。

## VSCode配置
1. 打开VSCode下载拓展`Markdown All in One`和`Markdown+Math`，前者用来配置markdown所有需要的配置，后者用于markdown预览latex类型的数学公式。
2. 按`ctrl+,`并打开`settings.json`文件，在大括号`{}`中添加以下内容，具体可以参考本项目下的`settings.json`文件。
 ```
   "markdown.extension.toc.levels": "1..6",
   "markdown.extension.toc.unorderedList.marker": "-",
   "markdown.extension.toc.orderedList": false,
   "markdown.extension.toc.plaintext": false,
   "markdown.extension.toc.updateOnSave": true,
   "markdown.extension.toc.omittedFromToc": {},
   "markdown.extension.toc.downcaseLink": true,
   "markdown.extension.preview.autoShowPreviewToSide": true,
   "markdown.extension.orderedList.marker": "ordered",
   "markdown.extension.italic.indicator": "*",
   "markdown.extension.tableFormatter.normalizeIndentation": false,
   "editor.insertSpaces": true,
   "editor.tabSize": 4,
   "cSpell.userWords": [
     "booktabs",
     "dvamessage",
     "emcscmslib",
     "emcsvipagui",
     "emcsvipaguilib",
     "guijcop",
     "h",
     "idatabase",
     "kable",
     "knitr",
     "kpis",
     "matplotlib",
     "pyplot",
     "writer"
   ],
   "[markdown]": {
     "editor.defaultFormatter": "yzhang.markdown-all-in-one"
   },
   "[jsonc]": {
     "editor.defaultFormatter": "vscode.json-language-features"
   },
   "markdown.preview.breaks": true
 ```
3. 按`ctrl+k+s`并打开`keybindings.json`文件，在大括号`[]`中添加以下内容，具体可以参考本项目下的`keybindings.json`文件。

  ```
      {
          "key": "ctrl+m ctrl+p",
          "command": "type",
          "args": {
              "text": "```{python}\n\n```"
          }
      },
      {
          "key": "ctrl+m ctrl+r",
          "command": "type",
          "args": {
              "text": "```{r}\n\n```"
          }
      },
  ```
  该操作为配置快捷键`ctrl+m ctrl+p`为输入以下代码块(无最左边的`\`)
  ```
  
  \```{python}
  \
  \```
  
  ```
  快捷键`ctrl+m ctrl+r`为输入以下代码块(无最左边的`\`)
  ```
  
  \```{r}
  \
  \```
  
  ```

4. 找到`settings.json`和`keybindings.json`，所在的文件夹，如我的为`C:\Users\Geman Zou\AppData\Roaming\Code\User`，拷进本项目下的`tasks.json`文件，该文件夹下一般也有`globalStorage`, `History`, `snippets`, `workspaceStorage`等文件夹。


## 右键安装
`vsCode_addright.reg` 为右键安装注册表，将文件用记事本打开，将其中的路径改为自己的路径，修改完成后保存关闭文件，双击运行安装右键。

## 使用说明
1. 文件夹`rmd-article-template-xmu`为完整的模板，直接在里面的`.Rmd`文件撰写文本内容。<br>
2. 用配置好的VSCode，打开整个模板文件夹 **（注意是文件夹，不是单个文件）** ，在`.Rmd`页面按`ctrl + shift + p`，然后输入`run task`回车。在下拉框中选择相应的编译任务即可编译不同的文件，如：

 - 选择`rmd-html`，即编译成html文件
 - 选择`rmd-pdf`，即编译成A4大小pdf文件
 - 选择`rmd-beamer`，即编译成幻灯片版pdf文件
 - 选择`rmd-doc`，即编译成docx文件
 - 选择`rmd-ppt`，即编译成ppt文件
