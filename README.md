# BlazorComponents.Terminal
a blazor components of  command line terminal on web

![image](https://github.com/wanglvhang/BlazorComponents.Terminal/assets/936437/3c08a3ac-c31e-4fc4-964d-bcca7470421a)

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

# API

