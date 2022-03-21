
name - 名称
brew - OS X 缺失的包管理器
synopsis - 摘要，大纲
brew --version  // brew的版本概要
brew command [--verbose|-v] [options] [formula] ...// brew的命令格式：brew 命令 [详情] [可选参数] [具体查看的软件名]
description - 描述
Homebrew 是在苹果系统上，安装UNIX工具的最简单、最灵活的方式
essential commands - 基本命令(重要命令)
全部的命令列表，可查看 'commands' 章节
使用 '--verbose | -v' 选项，许多命令可以打印出额外的调试信息。注意：这个选项，必须放在命令后面(例如：brew install -v)
install 软件名 // 安装软件
remove  软件名  // 卸载软件
update // 通过git从github上获取最新版本的homebrew
list // 列出全部安装的软件
search text|/text/  // 执行一个软件名子串的搜索。支持2种：1.字符串；2.正则，以'//'包围。注意：search命令，倾向在线搜索一些受欢迎的软件(例如：github上评分较高的等)，如果没有搜索到，才会列出本地搜索到的软件
commands - 命令列表
1.audit [--strict] [--online] [软件名]  // 审查[某个软件]
1>Homebrew审查软件的编码风格是否符合规范，应该在提交一个软件之前运行此命令来进行检查
2>如果没有提供 '软件名'，则所有的软件都会被检查
3>使用 '--strict' 选项，会运行额外的检查(更严格)。创建新软件时应该使用
4>使用 '--online' 选项，会运行额外的慢检查(需要一个网络连接)。创建新软件时应该使用
5>运行audit命令，出现错误时，会以一个 '非0' 的状态退出！这是非常有用的，例如：实现预提交
2.cat 命令
显示命令的来源(github的来源？？，可能还有其他来源？？)
3.cleanup [--prune=days] [--dry-run] [-s] [软件名]
1>针对所有或指定的某个已安装的软件，从 'cellar' 中移除所有旧版本。另外，从homebrew下载缓存中，删除所有的旧版本的下载包
2>指定 '--prune=days' 选项，移除指定日期之前的所有缓存文件
3>指定 '--dry-run | -n' 选项，显示哪些文件将会被移除，但并不实际操作
4>指定 '-s' 选项，移除缓存，删除下载包，甚至是软件最新版本的下载包(有些还未安装，就会被删除)。注意：对于任何已安装软件的下载包，并不会被删除。如果你也想删除这些，使用命令：'rm -rf $(brew --cache)'
4.command cmd 
当调用brew cmd，显示正在使用文件的路径
5.commands [--quiet [--include-aliases]]
1>显示内置的&外部的命令列表
2>指定 '--quiet' 选项，仅仅列出命令的名称，没有头部(header)
3>指定 '--quiet --include-aliases' 选项，外部命令的别名也会被显示出来
6.config
显示 homebrew&系统 调试的有用的配置信息。如果你提交一个错误报告，你可能会被要求提供这方面的信息，如果你未提供
7.create URL [--autotools | --cmake] [--no-fetch] [--set-name name] [--set-version version]
1>生成一个软件的可下载文件的URL，并在编辑器中打开。Homebrew将尝试自动获取软件名和版本，但是如果失败，则需要你提供你自己的模板。wget软件做为一个简单的例子。对于完整的api，可查看 'http://www.rubydoc.info/github/Homebrew/homebrew/master/Formula'。
2>指定 '--autotools' 选项，创建一个 'Autotools-style' 风格的基本模板， '--cmake'，创建一个 'CMake-style' 风格的基本模板
3>指定 '--no-fetch' 选项，Homebrew将不会下载URL到缓存中，也因此不会对软件添加'SHA256'
4>'--set-name' & '--set-version' 选项，允许你明确的设置你创建的包的名字和版本
8.deps [--1] [-n] [--union] [--tree] [--all] [--installed] [--skip-build] [--skip-optional] 软件名(可多个软件名参数)
1>显示软件的依赖包。当传递了 '多个软件名参数'，只会显示这些软件共有的依赖包(除非我们传递了 '--tree' | '--all' | '--installed'，这几个选项，会列出每个软件各自的依赖包)
2>指定 '--1' 选项，仅仅显示一级依赖包，而不会向下递归查找依赖
3>指定 '-n' 选项，显示拓扑顺序的依赖关系
4>指定 '--union' 选项，显示软件的联合的依赖关系，而不是交集
5>指定 '--tree' 选项，显示树形结构的依赖关系
6>指定 '--all' 选项，显示所有软件的依赖关系
7>指定 '--installed' 选项，显示所有已安装软件的依赖关系
8>deps命令，默认显示软件的依赖关系，指定 '--stip-build' 选项，跳过 '构建类型的依赖关系(只显示可选的依赖？？不懂)' | 指定 '--skip-optional' 选项，跳过 '可选的依赖关系'
9.desc 软件名
显示软件名称&一行描述
10.desc [-s | -n | -d] pattern
1>指定 '-s' 选项，在 'name'&'description' 搜索
2>指定 '-n' 选项，只在 'name' 搜索
3>指定 '-d' 选项，只在 'description' 搜索
4>pattern支持两种方式：1.文本；2.正则，使用 '//' 包围
5>软件的描述会被缓存，缓存会在第一次搜索时创建，使得第一次搜索相对较慢
11.diy [--name=name] [--version=version]
1>自动确定 '非Homebrew' 软件的安装前缀，使用该命令的输出，你可以将你自己的软件安装到 'Cellar' 中，之后链接它到Homebrew的链接前缀(也就是可以用Homebrew这套机制吧)
2>'--name'&'--version'选项，允许明确设置你正在安装的包的名字和版本
12.doctor
检测系统潜在的问题，如果发现问题，该命令会以一个 '非0' 的状态退出
13.edit
打开所有的Homebrew，进行编辑
14.edit 软件名
在编辑器中打开软件
15.fetch [--force] [-v] [--devel | --HEAD] [--deps] [--build-from-source | --force-bottle] 软件名
1>下载给定软件名的源码包，对于tar压缩包，也会打印 'SHA-1'&'SHA-256' 校验
2>指定 '--HEAD'| '--devel' 选项，获取 '最新版' 而非 '稳定版'
3>指定 '-v' 选项，如果URL代表一个VCS，进行一个详细的VCS检出。当一个存在的VCS缓存被更新，这会很有用(VCS就是版本控制程序，获取更新提交的文件)
4>指定 '--force' 选项，移除之前缓存的版本，重新获取新的
5>指定 '--deps' 选项，'也' 会下载所有列出软件的依赖(也，表示不仅下载软件，也下载软件的依赖)
6>指定 '--build-from-source' 选项，下载源码而不是安装包？
7>指定 '--force-bottle' 选项，如果OS X已经存在当前版本，仍旧下载。即使在安装过程中，还未使用。
16.home
在浏览器中打开 'Homebrew' 的主页
17.home 软件名
在浏览器中打开 '软件' 的主页
18.info 软件名
显示软件的相关信息
19.info --github 软件名
打开软件在github上的历史页面，查看软件的本地历史，使用：brew log -p 软件名
20.info --json=version (--all | --installed | 软件名)
1>打印软件的json表示，目前version只支持 'v1'
2>指定 '--all' 选项，获取所有软件的信息
3>指定 '--installed' 选项，获取已安装的所有软件的信息
4>查看使用json的示例文档：https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Querying-Brew.md
21.install [--debug] [--env=std | super] [--ignore-dependencies] [--only-dependencies] [--cc=compiler] [--build-from-source | --force-bottle] [--devel | --HEAD] 软件名
1>安装软件的详细参数，软件名可被指定为几种不同的方式，查看 'specifying formulae'
2>指定 '--debug' 选项，当brew失败时，在临时构建的目录中，打开一个访问IRB|shell的交互式的调试会话
3>指定 '--env=std' 选项，使用 '标准构建环境' 代替 'super环境'
4>指定 '--env=super' 选项，使用 'super环境'，即使 软件本身指定了 '标准构建环境'
5>指定 '----ignore-dependencies' 选项，跳过软件的任何依赖的安装。如果这些依赖并不存在，软件将可能安装失败
6>指定 '--only-dependencies' 选项，只安装软件的依赖，而不安装软件自身
7>指定 '--cc=compiler' 选项，尝试使用 'compiler' 编译。'compiler' - 具体的编译器，例如：gcc-4.2等
8>指定 '--build-from-source' 选项，即使提供了软件的 'bottle' 版，也从源代码编译安装
9>指定 '--force-bottle' 选项，即使已经给出了自定义的安装选项，如果软件的 'bottle版' 存在，强制安装 'bottle版'
10>指定 '--devel' 选项，软件定义了 'devel版'，安装 'devel版'(开发版)
11>指定 '--HEAD' 选项，软件定义了 'HEAD版'，安装 'HEAD版'(最新版，又名：master, trunk, unstable)
12>为了安装 'HEAD版' 中更新版本(是这样么，看后面的命令，也仅仅是安装head版啊)，使用 'brew rm 软件名 && brew install --HEAD 软件名'
22.install --interactive [--git] 软件名
1>下载并修补软件，接着打开一个shell。这允许用户运行'./configure --help'，同时除此以外，还可以确定如何将一个软件包转换为一个 'Homebrew软件'
2>指定 '--git' 选项，Homebrew将创建一个Git仓库，对于创建软件的补丁很有帮助
23.irb [--examples]
1>进入交互的 'Homebrew Ruby shell'
2>指定 '--example' 选项，将显示几个示例
24.leaves
显示已安装的软件(并不依赖另外的已安装软件)，可理解为 '独立的软件'。leaves并非离开，而是leaf(叶子)的复数形式，表示分支结构中最尖端的软件，所以不会依赖其他软件
25.ln(简写)，link [--overwrite] [--dry-run] [--force] 软件名
1>链接软件的所有安装文件到 'Homebrew prefix'，当你安装软件时，这个会自动完成，但是对于DIY安装是非常有用的
2>指定 '--overwrite' 选项，当链接时，Homebrew将删除 'Homebrew prefix' 中已经存在的文件，会重新生成链接文件
3>指定 '--dry-run | -n' 选项，Homebrew将列出所有将要生成连接的文件，并不会真正执行。获取传递了 '--overwrite' 选项，将会列出要删除的文件，但并不会真正删除
4>指定 '--force' 选项，Homebrew将允许keg-only软件被链接(默认情况下，keg-only不能被链接)
/*
keg-only fomulae 是什么意思
---------------------------
For a software to be "keg-only" means it is installed in /usr/local/Cellar but not linked into places like /usr/local/bin, /usr/local/lib, etc. That means other software that depends on it has to be compiled with specific instructions to use the files in /usr/local/Cellar. That's done automatically by brew install when a formula specifies keg-only dependencies.


Formulas that specify keg-only dependencies make sure that the equivalent system libraries are not used. Your installation of vips is linked against a specific version of pixman in /usr/local/Cellar/pixman/version, so it isn't affected by the system version of pixman or any other Homebrew versions of pixman you might install.
*/
26.linkapps [--local] [软件名]
1>查找OS X已编译为 'app-style' 风格的应用包的已安装的软件，链接这些apps应用到 '/Applications'，提供了更简单的访问
2>如果没有指定软件名，所有软件将会有它们的 '.apps' 符号链接
3>指定 '--local' 选项，将移动它们到 用户的'~/Applications' 目录，而不是系统目录。这种方式可能需要被首先创建
27.ls，list [--full-name]
1>列出所有已安装的软件
2>指定 '--full-name' 选项，打印软件的全称
28.ls，list --unbrewed
列出所有 'Homebrew prefix' 中并未通过 Homebrew 进行安装的文件!!
29.ls，list [--version [--multiple]] [--pinned] [软件名]
1>指定了 '软件名'，会列出软件已安装的文件
2>指定 '--verbose' 选项，会递归列出，每个软件的所有子模目录的内容
3>指定 '--version' 选项，显示所有已安装软件的版本号
4>指定 '--version 软件名'，只显示该软件的版本号
5>指定 '--version --multiple' 选项，只显示多版本安装的软件
6>指定 '--pinned' 选项，列出 'pinned 软件'的版本
30.log [git-log-options] 软件名 ...  // 可多个软件
1>显示指定软件的git log日志
2>指定 'git-log-options' 选项，应该是日志本身的选项
31.missing [软件名]
检查指定软件的丢失的依赖！如果没有提供 '软件名'，检查所有通过brew安装的软件
32.migrate [--force] 软件名
1>将重命名的包命名为新的名字，针对软件的包名字为旧名称
2>指定 '--force' 选项，将处理已安装的软件&指定的软件，就像它们来自相同的taps(补丁)，并迁移它们
33.options [--compact] (--all | --installed | 软件名)
1>显示指定的软件的安装参数
2>指定 '--compact' 选项，在一个已空格分隔的单行上，显示所有的选项
3>指定 '--all' 选项，显示所有软件的选项
4>指定 '--installed' 选项，显示所有已安装软件的选项
34.outdated [--quiet | --verbose | --json=v1]
1>显示有一个可更新版本的软件列表
2>默认情况下，版本信息将显示在交互的外壳中，并在其他情况下被抑制
3>指定 '--quiet' 选项，只显示软件列表的名称(优先于 --verbose 选项)
4>指定 '--verbose' 选项，展示详细的版本信息
5>指定 '--json=version' 选项，输出格式为json。有效的版本目前只能是 'v1'
35.pin 软件名
'pin'(锁，订，把...别住，可理解为:不允许改动软件)指定的软件，当发布brew升级命令，阻止软件被更新
36.unpin 软件名
'unpin'(与pin相反，解锁软件)，发不brew升级命令，允许软件被更新
37.prune [--dry-run]
1>从 'Homebrew prefix' 中，移除无效的符号链接。通常不需要，但是当执行了DIY安装时，会非常有用
2>指定 '--dry-run | -n' 选项，只显示哪些链接会被移除，并不会执行真正的删除
38.reinstall 软件名
先卸载，再安装软件
39.rm, remove, uninstall [--force] 软件名
1>卸载软件 
2>指定 '--force' 选项，如果软件安装了多个版本，移除所有的安装版本
40.search，-S
展示所有本地通过brew安装的软件(包括：打补丁(tapped)的软件)。当没有传递参数，不会执行线上(online)搜索
41.search，-S text | /text/
执行一个软件名子串的搜索。支持2种：1.字符串；2.正则，以'//'包围。注意：search命令，倾向在线搜索一些受欢迎的软件(例如：github上评分较高的等)，如果没有搜索到，才会列出本地搜索到的软件
42.search (--debian | --fedora | --fink | --macports | --opensuse | --ubantu) text
在指定的包管理器的列表中搜索
43.sh [--env=std]
实例化一个Homebrew构建环境。使用我们的 'years-battle-hardened' Homebrew构建逻辑帮助你 ./configure && make && make install 或者 甚至你的gem安装成功。如果你运行 Homebrew，在一个仅配置了Xcode的环境中，由于它添加了工具(例如：创建你的PATH)，否则编译系统会找不到
44.switch name version
链接指定名称的具体版本到 'Homebrew prefix'
45.tap
显示所有已安装的taps列表
46.tap [--full] user/repo [URL]
1>查找软件的远程仓库
2>未指定URL，通过https从github上查找软件仓库。由于有如此多的taps存在于github上，这个命令是一个捷径：tap <user>/<repo> => https://github.com/<user>/homebrew-<repo>
3>如果指定了URL，将会从任意位置，使用各种传输协议，只要是git支持的方式，tap一个命令仓库。1个参数形式的tap最简单，但是有限制。2个参数的命令不会假定，因此taps可以从任意位置，任意协议克隆得到。而不是仅从github&https协议得到。
4>默认情况，仓库被克隆作为一个浅层副本(--depth=1)，指定 '--full' 选项，将会使用一个完全克隆！
47.tap --repair
迁移tapped软件，从基于符号链接结构，到基于目录结构
48.tap --list-official
列出所有官方的taps
49.tap --list-pinned
列出所有pinned(锁定)的taps
50.tap-info tap(补丁名)
显示tap的相关信息
51.tap-info --json=version (--installed | taps)
1>打印taps的json格式，当前版本仅仅能接受的值是 'v1'
2>指定了 '--installed' 选项，获取所有已安装的taps信息
3>查看使用JSON示例的文档：https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Querying-Brew.md
52.tap-pin tap
pin tap(锁定tap)，使它的软件优先于用户提供的软件
53.tap-unpin tap
unpin tap(解锁tap)，使它的软件不在优先
54.test [--devel | --HEAD] [--debug] 软件名
1>一部分软件提供了一个测试方法。'brew test 软件名' 运行测试方法。没有标准的输出或返回码，但是它通常会提示用户，安装的软件存在错误。
2>指定 '--devel | --HEAD' 选项，用于测试软件的 '开发版' 或 'HEAD版'
3>指定 '--debug' 选项，当测试失败，在临时构建的目录中，打开一个访问IRB|shell的交互式的调试会话
55.unlink [--dry-run] 软件名
1>从 'Homebrew prefix' 中删除软件的符号链接。这对于临时禁用一个软件很有帮助：'brew unlink 软件名 && commands && brew link 软件名'
2>指定 '--dry-run | -n' 选项，将会列出所有将要删除的文件，但是并不会真正执行删除
56.unlinkapps [--local] [软件名]
1>移除通过 'brew linkapps' 创建的链接，如果没有指定软件，则所有的app链接都会被删除
2>指定 '--local'，会删除本地的链接
57.unpack [--git | --patch] [--destdir=path] 软件名
1>解压软件的源代码到当前工作目录的子目录。
2>指定 '--destdir=path' 选项，子目录将被创建为给定的目录名
3>指定 '--patch' 选项，软件的patches(补丁)将会被应用到解压到源代码中
4>指定 '--git' 选项，git仓库将会被初始化到解压的源代码中。这对于创建软件的patches(补丁)很有用
58.untap tap
移除一个tap仓库
59.update [--rebase]
1>通过git获取 'Homebrew' 的最新版本，以及所有软件的最新版从github上
2>指定 '--rebase' 选项，'git pull --rebase' 将被调用
60.upgrade [install-options] [--cleanup] [软件名]
1>升级过时的，unpinned(未锁定)的brew安装的软件
2>安装时的选项，在这里也有效(升级和安装时，都可使用软件安装时的参数)
3>指定 '--cleanup' 选项，将移除之前安装的软件所有版本
4>指定 '软件名'，仅升级指定的软件(即使该软件被pin-锁定，也可以升级)
61.uses [--installed] [--recursive] [--skip-build] [--skip-optional] [--devel | --HEAD] 软件名
1>指定的软件名是作为某个软件的依赖，列出所有依赖此软件的软件列表。当指定了多个软件名，显示依赖全部指定软件的软件列表
2>指定 '--recursive' 选项，解决多余一级的依赖
3>指定 '--installed' 选项，仅列出已经安装的软件
4>指定 '--skip-build' 选项，跳过将此软件作为 'build type' 依赖的软件列表
5>指定 '--skip-optional' 选项，跳过将此软件作为 'optional type' 依赖的软件列表
6>默认，uses显示的是稳定版软件的使用，指定 '--devel | --HEAD' 选项，显示 '开发版 ｜ HEAD版' 软件列表
62.--cache [软件名]
1>显示 'Homebrew' 的下载缓存，可查看 'HOMEBREW_CACHE'
2>指定 '软件名'，显示用于缓存软件的文件或目录
63.--cellar [软件名]
1>显示 'Homebrew' 的 'Cellar' 路径。默认：$(brew --prefix)/Cellar，如果这个目录不存在，则为：$(brew --repository)/Cellar
2>指定 '软件名'，显示软件将被安装到 'Cellar' 中的位置，没有任何版本目录的排序，作为最终的路径
64.--env
显示 'Homebrew' 构建环境的一个简介
65.--prefix [软件名]
显示 'Homebrew' 的安装路径，默认是：/usr/local
66.--repository
显示 'Homebrew' 的 '.git' 目录路径。对于标准安装，'prefix' 和 'repository' 是相同的目录
67.--version
打印brew的版本到标准错误输出并退出
external commands - 外部命令
Homebrew，同 'git' 一样，支持外部命令。这些命令是可执行的脚本，位于 'PATH' 的某个地方，以 'brew-cmdname' 或 'brew-cmdname.rb' 命名。可以被例如：'brew cmdname' 的命令调用。这就允许我们可以创建自己的命令，而不用修改 'Homebrew' 的内部实现
创建自己的命令的操作指南，可以查看文档：https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/External-Com-mands.md
specifying formulae - 指定formulae 
许多 'Homebrew' 的命令，可以接受一个或多个 'formula'(软件名) 参数，这些参数可以是以下几种形式：
1>一个软件的名称，例如：git, node, wget
2>一个完整的tapped软件名
有时，一个来源于一个tapped仓库的软件，可能与 'Homebrew/homebrew' 的软件冲突。你仍然可以访问这些软件，通过食用一个特殊的语法解析，例如：'homebrew/dupes/vim' 或者 'homebrew/versions/node4'
3>一个任意的URL
'Homebrew' 可以通过URL安装软件，例如：'https://raw.github.com/Homebrew/homebrew/master/Library/Formula/git.rb'。这个软件的文件将被缓存起来，为以后使用
environment - 环境变量
1.AWS_ACCESS_KEY_ID, AWS_RECRET_ACCESS_KEY
当使用S3下载策略，Homebrew将在这些变量中查找访问证书(查看：https://docs.aws.amazon.com/cli/latest/user-
              guide/cli-chap-getting-started.html#cli-environment，从AWS去检索这些访问证书)。如果未设置这些变量，S3下载策略将从一个公共的(未签名的)URL执行下载
2.BROWSER
未设置 'HOMEBREW_BROWSER'，则使用该选项设置的浏览器，打开项目主页
3.EDITOR
未设置 'HOMEBREW_EDITOR' 和 'VISUAL'，则使用该选项设置的编辑器作为文本编辑器
4.GIT
当使用git，Homebrew将优先使用我们设置的 'GIT'，其次使用Homebrew-build(Homebrew内置)的git(如果安装了)，最后使用system-provided(系统提供)的二进制软件。设置该选项，强制Homebrew使用一个特殊的二进制git
5.HOMEBREW_BROWSER
当设置了该选项，优先使用该选项设置的浏览器打开项目主页，代替了系统默认浏览器
6.HOMEBREW_BUILD_FROM_SOURCE
当设置了该选项，要求Homebrew从源代码编译安装软件(即使软件提供了bottle版)。这个环境变量倾向于开发者。当使用这个环境变量发生错误时，请不要上传issues(github上的问题)
7.HOMEBREW_CACHE
当设置了该选项，要求Homebrew使用给定的目录作为下载缓存目录。默认：~/Library/Caches/Homebrew(用户目录)，目录不存在，则使用/Library/Caches/Homebrew(系统目录)
8.HOMEBREW_CURL_VERBOSE
当设置了该选项，当调用curl命令时，将传递 '--verbose' 选项
9.HOMEBREW_DEBUG
当设置了该选项，Homebrew所有命令的调用都会打印调试信息
10.HOMEBREW_DEBUG_INSTALL
当使用 'brew install -d | brew install -i'，会打开一个新shell，'HOMEBREW_DEBUG_INSTALL'将被设置给正在安装的软件名
11.HOMEBREW_DEBUG_PREFIX
当使用 'brew install -d | brew install -i'，会打开一个新shell，'HOMEBREW_DEBUG_PREFIX'将被设置给正在安装的软件在 'Cellar' 中的 'target prefix'(目标prefix)
12.HOMEBREW_DEVELOPER
当设置了该变量，Homebrew将打印出关于'Homebrew开发者' 相关的警告信息(active or budding)
13.HOMEBREW_EDITOR
设置了该变量，在编辑一个软件|相同目录下的几个软件时，Homebrew将使用该变量设置的编辑器。
14.HOMEBREW_GITHUB_API_TOKEN
可以通过：https://github.com/settings/tokens，创建一个个人的Github API访问token。设置了该变量，github允许我们发起大量的API请求。可查看：https://developer.github.com/v3/#rate-limiting 获取更多信息。Homebrew使用很多 Github API，例如：brew search。注意：Homebrew在任何时候都不需要权限认证
15.HOMEBREW_LOGS
设置了该变量，Homebrew将使用给定的目录存储log文件
16.HOMEBREW_MAKE_JOBS
设置了该变量，当通过 'make命令' 编译时，通知Homebrew可使用 'HOMEBREW_MAKE_JOBS' 设置的值，作为可并行的jobs数量(线程|进程)。默认是：可用的CPU核心数量
17.HOMEBREW_NO_EMOJI
设置了该变量，当构建成功，Homebrew将不会打印 'HOMEBREW_INSTALL_BADGE' 设置的字符串。注意：Homebrew仅尝试打印emoji on Lion or newer(不知道什么意思)
18.HOMEBREW_NO_INSECURE_REDIRECT
设置了该变量，Homebrew将不允许从安装的HTTPS，重定向到不安全的HTTP。确保你的下载是绝对的安全，这可能会导致基于'Sourceforge&GNOME'软件的下载失败.Apache软件目前不会受该变量的影响，可以重定向到plaintext(这都是啥意思)
19.HOMEBREW_NO_GITHUB_API
设置了该变量，Homebrew将不会使用 'Github API'，例如：搜索 | 获取安装失败的issues
20.HOMEBREW_INSTALL_BADGE
每次成功构建，在输出安装小结前，都会输出该选项设置的文本！默认是 'beer emoji'(啤酒emoji表情)
21.HOMEBREW_SVN
当从SVN导出时，Homebrew首先使用 'HOMEBREW_SVN' 设置的SVN，其次使用 'Homebrew-build'(homebrew内置) 的SVN，最后尝试 'system-provided'(系统提供) 的SVN软件。设置该选项，强制使用本选项设置的SVN软件
22.HOMEBREW_TEMP
如果设置了，要求Homebrew使用设置的目录作为构建软件包的临时目录。当你系统临时目录和 'Homebrew Prefix' 在不同的volumes(分区)，这个选项必需设置。因为OS X在跨分区移动符号链接有问题！
当使用 'FileVault' 或 '自定义SSD配置' 经常出现这个问题！
23.HOMEBREW_VERBOSE
如果设置了，当运行命令时，Homebrew总是假定使用了 '--verbose' 选项
24.VISUAL
如果设置了，同时未设置 'HOMEBREW_EDITOR'，则使用它设置的编辑器作为文本编辑器
using homebrew behind a proxy - 通过代理使用homebrew
1>'Homebrew' 使用几个名下载文件(例如：curl, git, svn)。这些工具中的许多可以通过代理下载。这些工具从环境变量中读取代理参数是很平常的。
2>对于多数情况下，设置 'http_proxy' 已足够了。你可以在你的shell中设置这些(类似全局设置)，或者你可以在一个brew命令前来使用它(每个brew命令前都得使用)，例如：
'http_proxy=http://<host>:<port> brew install foo'
3>如果代理需要认证，可以如下使用：
'http_proxy=http://<user>:<password>@<host>:<port> brew install foo'
