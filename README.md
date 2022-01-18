# lerna-demo
this is a test demo

# 介绍
  lerna 是一个管理工具，用于管理包含多个软件包（package）的javaScript项目
  将大型代码仓库分割成多个独立版本化的软件包（package）对于代码共享来说非常有用（非常适合组件库）, 但是如果某些更改跨越了多个代码仓库的话将会变得麻烦且难以追踪，且会让测试变得非常复杂（webpack5 联邦拆分方案，就会遇到）
  
  为了解决这些问题，某些项目会将代码仓库分割成多个软件包（package），并将每个软件包存放到独立的代码仓库中，例如Bebel，React，等项目都是在一个代码库中包含了多个软件包，并进行开发

  lerna 是一种工具，针对使用git和npm管理多软件包代码仓库的工作流程进行优化

# 命令

## leran init
  将当前仓库转变为一个Lerna仓库
  
  参数 --independent / -i 使用独立的版本控制模式

## lerna bootstrap
  在当前lerna 仓库中执行引导流程（bootstrap）。安装所有依赖项，并链接任何交叉依赖
  注意： 它可以让你在require()中直接通过软件包的名称进行加载，就好像次软件包已经存在于你的node_modules目录一样

## lerna import <pathToRepo>
  将本地路径<pathToRepo>中的软件包导入packages/<directory-name>中并提交commit

## lerna publish 
  为已经更新过的软件包创建一个新版本，提示 输入新版本号，并更新git和npm上所有软件包

  参数 
  --npm-tag [tagname] 使用给定的npm dist-tag(默认为latest)发布到npm
  --canary / -c 创建一个canary（金丝雀，新内容比较多的）版本
  --skip-git 不运行任何git命令
  --force-publish [packages] 强制发布，制定一个或多个软件包（以逗号分割）或使用*表示所有软件包（跳过git diff检查）

## lerna changed
  检查自上次发布以来哪些软件包被修改过

## lerna diff [package?]
  列出所有或者某个自上次发布以来的修改情况

## lerna run [script]
  在每一个包含script脚本的软件包中运行此【npm】脚本

## lerna ls