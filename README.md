# Ward_CN
Ward性能监控的中文版本

### 关于

Ward是一个简单而简约的服务器监控工具。Ward支持自适应设计系统。此外，它还支持黑暗主题。
它只显示主要信息，如果你想看到漂亮的仪表板，而不是看一堆数字和图表，可以使用它。
Ward在所有流行的操作系统上都运行良好，因为它使用[OSHI](https://github.com/oshi/oshi).

**所有功能都在以下平台上进行了测试：**“Windows”Linux`

![image](https://github.com/user-attachments/assets/fa63cbf2-0639-4277-bacb-f3e61460773b)


---

### 安装

    创建你的jar

    • 克隆项目
    • 将IDE中的项目作为Maven项目导入
    • mvn 构建

<br>

运行jar文件

  1.如上所述创建自己的罐子
  2.使用管理权限在Windows或Linux上执行jar
  3.输入localhost:4000并设置应用程序

<br>

    用Docker构建

    1. 克隆项目
    2. docker build --tag ward
    3. docker run --restart unless-stopped -it -d --name ward  -p 4000:4000 -e WARD_PORT=4000 -e WARD_THEME=dark --privileged ward
    4. 输入localhost:4000并设置应用程序

### Config

如果你想更改Ward的配置，你可以编辑`setup.ini `。使用Docker时，使用环境变量“WARD_NAME”、“WARD_THEME”和“WARD_PORT”在启动时自动重新生成此文件。使用列出的任何环境变量都将启用下面的默认值，并在没有GUI设置的情况下立即启动Ward。

| 设置            | 变量            | 描述                                         | 默认    |
|-----------------|-----------------|----------------------------------------------|---------|
| serverName      | WARD_NAME       | 服务器的名称.                                 | Ward    |
| port            | WARD_PORT       | 运行端口.                                     | 4000    |
| theme           | WARD_THEME      | 要么是“亮”，要么是“暗”.                        | light   |
| enableFog       | WARD_FOG        | 要么是“true”，要么是“false”.                   | true    |
| backgroundColor | WARD_BACKGROUND | 禁用雾时背景为HexColor.                        | default |

环境变量具有优先权，并将使用您的变量重新生成此文件。如果没有设置环境变量，则导航到Ward的网页并完成初始设置后，将生成“setup.ini”。您也可以在启动Ward之前自己制作此文件，并将其放置在同一目录中。

例如：

```ini
[setup]
serverName = my-server
theme = dark
port = 8200
enableFog = true
backgroundColor = #303030
```
