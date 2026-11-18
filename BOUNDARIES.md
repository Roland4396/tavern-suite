# 组件关系
浏览器 → 入口及登录 → 上游酒馆（单独安装）。自研传输补丁由 frontend-patches 提供。文本请求经 Stream → Account Pool → CLI 或单独部署的 Gproxy。浏览器受限 Stream 代理不替代登录入口。
托管图片由 hosted-media 接收和交付；本地媒体由 compute-controller 管队列、持久状态和放置。只有需要文本计划的流程才调用 media-planner。graph-gateway、compute-gateway、tts-runtime、gpu-node 各自运行。gpu-platform 管节点部署，不代发用户生成。
新仓库不携带生产身份、凭据、挂载或业务数据。仓库不是整机备份。第三方 tt-sync 自行安装，仅绑定只读工作区。官方二进制、模型和私人工作流自行提供。
