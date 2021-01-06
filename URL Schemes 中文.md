
# URL Schemes

## 前言

### 支持的 Schemes（URL链接前缀）
#### spring
可能打开一个旧版本、不支持 URL Schemes 的 Spring。

#### spring2
仅当Spring已更新到支持版本后，才能被打开。

### 通用参数
#### account
使用由您的账号名（用户@名称）作为区分的特定账号来执行任务。 account对应的内容无需区分大小写。

例如，@theSpringApp 的账号名是 “theSpringApp”。

#### account-id
使用由您的 Twitter 用户编号作为区分的特定账号来执行任务。 

要获取用户编号，请先打开用户页面，然后点击右上角的“动作”按钮，然后点击“拷贝”并选择“拷贝用户编号”。

除非本文档另有说明，您只需提供“account”或“account-id”参数。

推荐使用“account-id”而不是“account”，因为该ID是一个与您的Twitter账号绑定的稳定编号，而账号名可以随时在Twitter.com上更改，这意味着使用“account-id”作参数时，您不必在更改 Twitter 账号名后更新您的 URL Scheme 配置。

## 切换账号
请提供 "account" 或 "account-id" 作为参数。如果当前 app 窗口登录的账号与 URL 账号相同，Spring 不会作任何变动。

#### 示例
spring2://switch?account=theSpringApp

spring2://switch?account-id=886626176751546368

## 打开推文编辑器
可提供两个选填的参数：text, account/account-id

text参数对应的内容会被填入推文编辑器。如果未提供账号参数，Spring 会自动选取一个基于当前打开窗口的默认的账号。

#### 示例
spring2://post?text=hello

spring2://post?text=hello&account-id=886626176751546368

## 打开搜索视图
可提供两个选填的参数：text, account/account-id

text参数对应的内容会被填入搜索栏。

### 示例
spring2://search?text=hello

spring2://search?text=hello&account-id=886626176751546368

## 打开 Twitter 链接
目前支持推文链接 (如 https://twitter.com/thespringapp/status/1344625888449556480), 用户主页链接 (如 https://twitter.com/thespringapp), 和 Twitter 列表链接 (如 https://twitter.com/i/lists/1344918930687729664)

### 简单
将 Twitter URL 的前缀 “https” 替换为 “spring” 即可。

例如，通过默认账号打开 @theSpringApp 的用户主页：

spring://twitter.com/theSpringApp

### 进阶
如果您希望一次打开多个页面，或通过特定账号打开页面，请使用 “open” URL。

可提供 2 个 URL 参数： url (必填), account/account-id (选填)。

您可指定多个 url 参数。url 参数的内容必须经过百分比编码（percent encoding）否则 Spring 可能无法识别。

#### 示例
通过已登录的 @theSpringApp 账号打开 @twitter 和 @jack 的用户主页：

spring://open?account=theSpringApp&url=https%3A%2F%2Ftwitter.com%2Ftwitter&url=https%3A%2F%2Ftwitter.com%2Fjack
