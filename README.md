# BlazorComponents.Terminal
这是一个基于Blazor的模拟终端样式的UI组件
a blazor components of  command line terminal on web

![image](https://github.com/wanglvhang/BlazorComponents.Terminal/assets/936437/3c08a3ac-c31e-4fc4-964d-bcca7470421a)

# TODO
1. auto complete 自动完成功能
2. more theme 更多样式

# Setup
在项目中引用 BlazorComponents.Terminal nuget 包，然后在项目中添加样式与组件，如下所示

```
//在head中添加所需样式
<HeadContent>
    <link href="_content/BlazorComponents.Terminal/style.css" rel="stylesheet" />
    <link href="_content/BlazorComponents.Terminal/theme.default.css" rel="stylesheet" />
</HeadContent>
//添加组件
<BlazorTerminal @ref="blazorTerminal" Style="height:600px;" OnCommandEnter="commandEnter" OnAnswerEnter="answerEnter"></BlazorTerminal>
```
添加完上面的代码后就可以通过 `blazorTerminal` 引用进行操作，首先需要进行的操作就是**配置提示符**的内容并**添加事件监听**,

```
//config prompt
blazorTerminal.ConfigPrompt(new CommandPrompt()
    {
        Name = "visitor",
        Host = "blazor.terminal",
        Path = "~",
        Separator1 = '@',
        Separator2 = ':',
        Prompt = '#',
        AnswerPrompt = ">"
    });

//OnCommandEnter event
async void commandEnter(TerminalEventArgs evenArgs)
{
    //your code
｝

//OnAnswerEnter event
async void answerEnter(TerminalEventArgs evenArgs)
{
    //your code
｝

```


# Terminology / 术语
在该组件的语境中，终端内的所有内容都被称为**段落(TerminalParagraph)**. 段落大致被分为两类：**命令(Command)段落**和**回复(Respond)段落**,其中回复段落内也可能需要输入内容，这被称为**回复输入(Answer)**。


# API

| API| 类型|说明 |
| ----- | ---- | ----- |
| OnCommandEnter  | 事件  | 命令输入Enter事件 | 
| OnAnswerEnter | 事件 | 回复输入Enter事件 | 
| OnCommandKeyDown| 事件 |命令输入按键(除了Enter键)事件  | 
| OnAnswerKeyDown| 时间 | 回复输入按键(除了Enter键)事件 | 
| GetCurrentParagraph| 方法 | 获取当前段落，也就是最后一个段落 | 
| RespondText| 方法 | 回复文本内容 | 
| RespondHtml| 方法 | 回复Html内容 | 
| RespondImage| 方法 | 回复图像内容 | 
| Return| 方法 | 终端返回，立即添加一个命令段落并等待输入 | 
| Clear | 方法 | 清空终端中的所有内容 | 
| ConfigPrompt| 类型 | 配置终端提示符的内容 | 
| TerminalEventArgs| 类型 | 终端事件返回对象类型 | 
| TerminalParagraph| 类型 | 终端中显示的段落 | 


# Style

目前只包含一个默认样式 theme.defualt.css, 你可以通过引用自定义的 css 来修改终端样式，样式结构如下


```
.bc-terminal-theme {

}

    .bc-terminal-theme > .bc-paragraph {
    }

    .bc-terminal-theme .bc-terminal-input {

    }


    .bc-terminal-theme > .bc-paragraph-command > .bc-prompt > .bc-prompt-name {

    }

    .bc-terminal-theme > .bc-paragraph-command > .bc-prompt > .bc-prompt-spr1 {
    }

    .bc-terminal-theme > .bc-paragraph-command > .bc-prompt > .bc-prompt-host {

    }

    .bc-terminal-theme > .bc-paragraph-command > .bc-prompt > .bc-prompt-spr2 {
    }

    .bc-terminal-theme > .bc-paragraph-command > .bc-prompt > .bc-prompt-path {
    }

    .bc-terminal-theme > .bc-paragraph-command > .bc-prompt > .bc-prompt-pmt {
    }


    .bc-terminal-theme > .bc-paragraph-response > .bc-command-content {
    }

```






