[English](https://github.com/siyuan-note/template-sample/blob/main/README.md)

# 思源笔记模板示例

## 开始

* 通过 <kbd>Use this template</kbd> 按钮将该库文件复制到你自己的库中，请注意库名必须和模板名称一致，默认分支必须为 `main`
* 将你的库克隆到本地开发文件夹中，为了方便可以直接将开发文件夹放置在 `{workspace}/conf/appearance/templates/` 下

## 开发

* template.json
* icon.png (160*160)
* preview.png (1024*768)
* README*.md
* *.md

## template.json

```json
{
  "name": "template-sample",
  "author": "Vanessa",
  "url": "https://github.com/siyuan-note/template-sample",
  "version": "0.0.3",
  "minAppVersion": "2.9.0",
  "displayName": {
    "default": "Template Sample",
    "zh_CN": "模板示例"
  },
  "description": {
    "default": "This is a template sample",
    "zh_CN": "这是一个模板示例"
  },
  "readme": {
    "default": "README.md",
    "zh_CN": "README_zh_CN.md"
  },
  "funding": {
    "openCollective": "",
    "patreon": "",
    "github": "",
    "custom": [
      "https://ld246.com/sponsor"
    ]
  },
  "keywords": [
    "sample", "示例"
  ]
}
```

* `name`：模板名称，必须和库名一致，且全局唯一（集市中不能有重名模板）
* `author`：模板作者名
* `url`：模板仓库地址
* `version`：模板版本号，建议遵循 [semver](https://semver.org/lang/zh-CN/) 规范
* `minAppVersion`：模板支持的最低思源笔记版本号
* `displayName`：模板显示名称，主要用于模板集市列表中显示，支持多语言
    * `default`：默认语言，必须存在
    * `zh_CN`、`en_US` 等其他语言：可选，建议至少提供中文和英文
* `description`：模板描述，主要用于模板集市列表中显示，支持多语言
    * `default`：默认语言，必须存在
    * `zh_CN`、`en_US` 等其他语言：可选，建议至少提供中文和英文
* `readme`：自述文件名，主要用于模板集市详情页中显示，支持多语言
    * `default`：默认语言，必须存在
    * `zh_CN`、`en_US` 等其他语言：可选，建议至少提供中文和英文
* `funding`：模板赞助信息
    * `openCollective`：Open Collective 名称
    * `patreon`：Patreon 名称
    * `github`：GitHub 登录名
    * `custom`：自定义赞助链接列表
* `keywords`：搜索关键字列表，用于集市搜索功能

## 打包

无论使用何种方式编译打包，我们最终需要生成一个 package.zip，它至少包含如下文件：

* icon.png
* preview.png
* README*.md
* template.json
* *.md

### 使用 Github Action 打包

需要发布版本的时候, push 一个格式为 `v*` 的 tag, github 就会自动打包发布 release（包括 package.zip）


## 上架集市

* 生成 package.zip
* 在 GitHub 上创建一个新的发布，使用模板版本号作为 “Tag
  version”，示例 https://github.com/siyuan-note/template-sample/releases
* 上传 package.zip 作为二进制附件
* 提交发布

如果是第一次发布版本，还需要创建一个 PR 到 [Community Bazaar](https://github.com/siyuan-note/bazaar) 社区集市仓库，修改该库的
templates.json。该文件是所有社区模板库的索引，格式为：

```json
{
  "repos": [
    "username/reponame"
  ]
}
```

PR 被合并以后集市会通过 GitHub Actions 自动更新索引并部署。后续发布新版本模板时只需要按照上述步骤创建新的发布即可，不需要再
PR 社区集市仓库。

正常情况下，社区集市仓库每隔 1 小时会自动更新索引并部署，可在 https://github.com/siyuan-note/bazaar/actions 查看部署状态。
