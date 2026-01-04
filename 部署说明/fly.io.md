# 1. 生成新的UUID（必须执行）
cat /proc/sys/kernel/random/uuid
# 或访问：https://www.uuidgenerator.net/
# 复制生成的UUID替换配置文件中的UUID

# 2. 修改 fly.toml 中的 app 名称
# 改成唯一名称，如：v2ray-nrt-2026

# 3. 安装 Fly CLI（如已安装跳过）
curl -L https://fly.io/install.sh | sh

# 4. 登录
fly auth login

# 5. 创建应用
fly apps create your-app-name-here  # ← 使用你设置的app名称

# 6. 分配免费共享IPv4
fly ips allocate-v4 --shared -a your-app-name-here

# 7. 部署
fly deploy

# 8. 查看部署结果
fly status
fly logs

# 9. 测试访问（浏览器打开）
https://your-app-name-here.fly.dev
