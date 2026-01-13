AI编程工具里面,我最近一直在用OpenCode。我有三个必须选择OpenCode的理由:

1. 100%开源
2. 不被任何厂商绑架
3. 功能比Claude Code还要强

Claude Code虽然很强大,但它是闭源的,而且深度绑定了Anthropic。如果你想用其他模型,或者担心某天Anthropic倒闭了怎么办?OpenCode完全不存在这个问题。它是完全开源的,代码托管在GitHub上,任何人都可以审查、修改、Fork。

更关键的是,OpenCode支持所有主流AI模型。Claude、GPT、Gemini、甚至本地模型都可以直接用。你今天用Claude,明天觉得GPT便宜,后天想试试本地模型,随时切换,没有任何锁定。这种自由度,是闭源工具永远给不了的。

而且OpenCode的功能一点也不弱。它内置了LSP支持,双Agent设计,还有桌面应用。这些功能组合起来,完全不输Claude Code,某些方面甚至更强。接下来我会从安装、Agent设计、还有与Claude Code的对比等角度,深入讲讲OpenCode到底好在哪。

## 安装简单到爆

OpenCode的安装简直是我见过最友好的。一行命令就能搞定。

如果你用的是Mac或者Linux,直接跑这个命令:

```bash
curl -fsSL https://opencode.ai/install | bash
```

一行命令,自动检测你的系统,自动安装到合适的位置。它会按照XDG标准,优先安装到`$HOME/bin`或者`$HOME/.local/bin`,如果你想自定义安装路径,设置一下`OPENCODE_INSTALL_DIR`环境变量就行。

如果你是Windows用户,可以用Scoop或者Chocolatey:

```bash
scoop bucket add extras; scoop install extras/opencode
# 或者
choco install opencode
```

如果你用包管理器,npm、bun、pnpm、yarn都支持:

```bash
npm i -g opencode-ai@latest
```

Arch Linux用户直接用paru:

```bash
paru -S opencode-bin
```

macOS用户最推荐用Homebrew,因为更新最及时:

```bash
brew install anomalyco/tap/opencode
```

除了命令行版本,OpenCode还提供了桌面应用。直接去opencode.ai/download下载dmg、exe或者AppImage,双击安装,就能用了。桌面应用目前是Beta版,但已经很稳定了。

## 双Agent设计很聪明

OpenCode内置了两个Agent,这个设计非常聪明。

第一个是build agent,这是默认的开发Agent。它拥有完整的权限,可以读写文件、执行命令、安装依赖、跑测试、提交代码。你平时写代码、改Bug、加功能,全都用它。

第二个是plan agent,这是只读分析Agent。它默认不能编辑文件,运行Bash命令之前会先问你要不要执行。这个Agent特别适合用来分析陌生代码库,或者在动手之前先规划一下思路。

这两个Agent可以用Tab键随时切换。比如你刚接手一个新项目,先切到plan agent,让它帮你分析代码结构、找出关键模块、梳理业务逻辑。等你心里有数了,再切回build agent开始干活。

除了这两个内置Agent,OpenCode还有一个general subagent,专门用来处理复杂搜索和多步骤任务。你可以在消息里用`@general`来调用它。这个subagent会在后台自动工作,帮你完成那些需要多轮交互的任务。

这种多Agent的设计,比单一Agent要灵活太多了。你可以根据不同场景选择不同工具,而不是让一个Agent包打天下。

## 为什么不用Claude Code

很多人会问,Claude Code已经很好用了,为什么要换OpenCode?

核心区别就三点:100%开源、不绑定供应商、内置LSP。

Claude Code是闭源的。你不知道它到底在做什么,不知道你的代码会不会被上传,不知道哪天Anthropic会不会改规则或者涨价。OpenCode是完全开源的,代码全在GitHub上,想看就看,想改就改。这种透明度,是闭源工具永远做不到的。

Claude Code只能用Anthropic的模型。OpenAI出了新模型?对不起,用不了。Google发布了更便宜的Gemini?也用不了。想跑本地模型?更不可能。OpenCode完全没有这个限制。你可以同时配置多个Provider,Claude用来写代码,GPT用来写文档,Gemini用来做翻译,本地模型用来保护隐私。随时切换,完全自由。

而且OpenCode自带LSP支持。LSP就是Language Server Protocol,它能提供代码补全、跳转定义、查找引用这些IDE才有的功能。有了LSP,OpenCode不只是一个聊天机器人,而是真正懂你的代码库的开发工具。

随着AI模型的发展,各家模型之间的能力差距会越来越小,价格会越来越低。在这个趋势下,不被任何一家厂商锁定,才是最重要的。OpenCode给了你这个自由。

如果你现在还在用Claude Code,或者在观望AI编程工具,我强烈建议试试OpenCode。它不会让你失望。
