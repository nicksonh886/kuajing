# Windows系统搭建Minecraft 1.19.4服务器教程（雨云VPS版）

本教程将详细介绍如何在**雨云VPS**上使用Windows系统搭建支持模组和插件的Minecraft 1.19.4服务器，特别适合新手用户快速入门。

## 服务端选择：Mohist介绍

我们选用**Mohist 1.19.4**服务端，这是一个高性能的Minecraft服务器解决方案，具有以下优势：

- **双模支持**：同时兼容Forge模组和Bukkit/Spigot插件
- **性能优化**：集成Paper核心提升运行效率
- **稳定可靠**：活跃开发者社区持续维护更新
- **简单易用**：中文文档完善，配置门槛低

👉 [【点击查看】2025年最新雨云优惠码及特价云服务器方案汇总](https://bit.ly/RainYun)

## 准备工作

### 硬件要求
- **推荐配置**：4核CPU/8GB内存（Windows系统本身占用较大内存）
- **存储空间**：建议预留20GB以上空间

### 软件环境
- 操作系统：Windows Server 2019
- Java环境：JDK 17（推荐阿里Dragonwell优化版）

## 详细搭建步骤

### 第一步：获取服务器
1. 登录雨云控制台
2. 选择「游戏云」→「VPS服务器」
3. 推荐配置：
   - CPU：5900X/7950X（高版本服首选）
   - 内存：8GB起
   - 系统：Windows Server 2019
4. 网络设置：NAT模式（可开通15个端口）

### 第二步：远程连接
1. 使用Windows自带的远程桌面连接（RDP）
2. 输入服务器IP和端口
3. 登录凭证：
   - 用户名：Administrator
   - 密码：购买时设置的密码

### 第三步：环境配置
1. **关闭防火墙**（或单独开放25565端口）
2. **设置端口映射**：
   - 内网端口：25565
   - 外网端口：自动生成（需记录）

### 第四步：安装Java
1. 下载阿里Dragonwell JDK 17
2. 解压至D盘目录
3. 配置环境变量：
   bash
   # 示例路径
   D:\dragonwell-jdk-17.0.8+7\bin
   
4. 验证安装：
   cmd
   java -version
   

## 服务器部署

### 服务端设置
1. 创建专用目录（如D:\mc）
2. 下载Mohist服务端jar文件
3. 创建启动脚本run.bat：
   bat
   java -Xms128M -XX:MaxRAMPercentage=95.0 -Dfile.encoding=UTF-8 -Duser.country=CN -jar mohist-1.19.4-192-server.jar
   pause
   

### 首次运行
1. 双击run.bat启动服务端
2. 同意EULA协议（输入true）
3. 等待显示"Done"表示启动成功

### 重要配置修改
编辑server.properties文件：
properties
# 关闭正版验证（可选）
online-mode=false
# 服务器端口
server-port=25565

## 客户端连接
1. 启动Minecraft客户端
2. 添加服务器地址：
   
   格式：映射公网IP:端口
   示例：f.rainplay.cn:38426
   
3. 首次进入后可通过控制台授予OP权限：
   mc
   op 你的游戏ID
   

## 运维建议
1. **定期备份**：压缩存档目录保存
2. **性能监控**：关注内存和CPU使用率
3. **安全更新**：及时升级服务端版本

## 常见问题解决
- **连接失败**：检查端口映射和防火墙设置
- **内存不足**：调整XX:MaxRAMPercentage参数
- **启动报错**：确认Java版本兼容性

通过本教程，您已成功在雨云VPS上搭建了功能完善的Minecraft服务器。如需更高性能的服务器方案，可以参考：

👉 [【点击查看】2025年最新雨云优惠码及特价云服务器方案汇总](https://bit.ly/RainYun)