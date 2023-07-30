# BlazorComponents.Terminal
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

# Terminology / 术语
在该组件的语境中，终端内的所有内容都被称为**段落(TerminalParagraph)**. 段落大致被分为两类：**命令(Command)段落**和**回复(Respond)段落**,其中回复段落内也可能需要输入内容，这杯称为**回复输入(Answer)**。


# API

| API| 类型|说明 |
| ----- | ---- | ----- |
|OnCommandEnter  | 事件  |  | 
| OnAnswerEnter | 事件 |  | 
| OnCommandKeyDown| 事件 |  | 
| OnAnswerKeyDown| 时间 |  | 
| GetCurrentParagraph| 方法 |  | 
| RespondText| 方法 |  | 
| RespondHtml| 方法 |  | 
| RespondImage| 方法 |  | 
| Return| 方法 |  | 
| Clear | 方法 |  | 
| ConfigPrompt| |  | 
| TerminalEventArgs| 类 |  | 
| TerminalParagraph| 类 |  | 


# Style







