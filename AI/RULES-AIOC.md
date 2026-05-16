# AIOC 子模块规则

- 子模块名：`AIOC`
- AIOC 是一个独立的子模块，专门讲述 OpenCode 相关的内容。

## 目录结构

- `./AI/AIOC/` - OpenCode课程内容
- `./AI/AIOC/assets/` - OpenCode图片资源
- `./AI/AIOC/backup/` - 用于版本更新时保存上一版本的所有md文档

## 生成步骤

- 当 `./AI/AIOC/backup/` 目录不存在时，说明是第一次生成该子模块的文档，按以下步骤进行：
  - 需要将生成过程存放在 `./AI/AIOC/log.md` 文件中
  - 各课件文件描述生成 `./AI/AIOC/README.md`
- 当 `./AI/AIOC/backup/` 目录存在时，说明不是第一次生成该子模块的文档，按以下步骤进行：
  - 创建 `./AI/AIOC/backup/` 目录
  - 将 `./AI/AIOC/*.md` 文档移动到 `./AI/AIOC/backup/` 目录中
  - 重新生成各 md 文档，各课件文件描述重新生成 `./AI/AIOC/README.md`
  - 对新生成的文档和原有的文档进行对比分析，并将对比分析结果存放在 `./AI/AIOC/log.md` 文件中

## 文件内容

- 从提供的网址中获取内容，并形成相应的文档

### ./AI/AIOC/OC11--快速起步.md

- 合并以下网页中的内容，生成 `./AI/AIOC/OC11--快速起步.md` 文件：
  - https://github.com/vbgate/learn-opencode/tree/main/docs/1-start/
- 网页中用到的所有图片，下载到 `./AI/AIOC/assets/` 目录中，文件名增加前缀 `OC11--` ，然后相应地调整 md 文件中的图片链接

### ./AI/AIOC/OC12--日常使用.md

- 合并以下网页中的内容，生成 `./AI/AIOC/OC12--日常使用.md` 文件：
  - https://github.com/vbgate/learn-opencode/tree/main/docs/2-daily/
- 网页中用到的所有图片，下载到 `./AI/AIOC/assets/` 目录中，文件名增加前缀 `OC12--` ，然后相应地调整 md 文件中的图片链接

### ./AI/AIOC/OC13--工作流程.md

- 合并以下网页中的内容，生成 `./AI/AIOC/OC13--工作流程.md` 文件：
  - https://github.com/vbgate/learn-opencode/tree/main/docs/3-workflow/
- 网页中用到的所有图片，下载到 `./AI/AIOC/assets/` 目录中，文件名增加前缀 `OC13--` ，然后相应地调整 md 文件中的图片链接

