# vscode-dev-containers

A repository of development container definitions for the VS Code Remote - Containers extension.
本仓库主要是用于使用 vscode + remote container 开发时初始化`.devcontainer`文件夹。

## Offical example

https://github.com/microsoft/vscode-dev-containers/tree/main/containers

## 官方教程

- [中文教程](https://docs.microsoft.com/zh-cn/learn/modules/use-docker-container-dev-env-vs-code/1-introduction)
- [英文教程](https://code.visualstudio.com/docs/remote/containers)

## 教程

1. 安装`vscode`和`docker`，`vscode`安装`Remote-Containers`扩展。
2. `git clone`克隆本仓库到本地。
3. `cd vscode-dev-containers && export PATH=$PATH:$(pwd)`，进入本项目根目录并添加临时PATH路径。
4. `cd /my-project && init-devcontainer js`，进入任意项目，进行初始化`.devcontainer`文件夹（如果是go语言项目，将js换成go），这时，`/my-project`项目根目录下将会有一个文件夹`.devcontainer`。
5. vscode打开`my-project`项目，按下快捷键`cmd`+`shift`+`p`，然后输入`Remore-Containers: Reopen in Container`并选择，这时vscode将会重启。
6. vscode重启成功后，此时`my-project`项目就已经在容器内运行。
7. 自行修改`my-project`根目录下的`.devcontainer`下面的`Dockerfile`、`docker-compose.yml`和`devcontainer.json`，然后重启vscode获得更丰富功能。

## Tips

如果容器内执行git远程相关命令，比如拉代码或者推代码，是不成功的，需要在宿主终端执行`ssh-add $HOME/.ssh/id_rsa`，将密钥加到代理。详见[官方文档](https://code.visualstudio.com/docs/remote/containers#_sharing-git-credentials-with-your-container)
