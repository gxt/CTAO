# 版本管理

## git入门

更多 Git 入门教程可参考：
- [菜鸟教程 Git 指南](https://www.runoob.com/git/git-tutorial.html)
- https://learnopencode.com/2-daily/06-git-basics.html

- github上的git介绍：
  - https://docs.github.com/zh/get-started/git-basics
  - https://docs.github.com/zh/get-started/using-git

### 本地使用 Git

- **Mac/Linux**：系统自带 `git` 命令，可直接使用。常用命令有：

```bash
git add .
git commit -m "提交说明"
git push
git pull
```

- **Windows**：需要先安装 Git 客户端，安装完成后会提供 Git Bash 窗口，命令与 Linux 相同。

### 在 clab 虚拟机中使用 Git

1. **安装 git**

   ```bash
   sudo apt install -y git
   ```

2. **登录网关**

   ```bash
   python login.py   # 登录网关
   ```

3. **设置代理与配置**
    编辑配置文件：

   ```bash
   vim ~/.gitconfig
   ```

   示例配置：

   ```
   [http "https://github.com"]
       proxy = https://www.XXXXX.ltd/local.pac
   [user]
       email = ABC@pku.edu.cn
   [http]
       postBuffer = 524288000
   ```

4. **克隆仓库**

   ```bash
   git clone http://github.com/gxt/CTAO/   # 克隆到本地
   ```

## github 使用方法

### 注册账号

- [Github 官网](https://github.com/) 注册一个账号
  - 可以直接在网页端上传、修改文件，也可以通过本地命令行来操作。

