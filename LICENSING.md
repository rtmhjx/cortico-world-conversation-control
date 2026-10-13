# 许可元数据与发布前审阅 / License metadata and review gate

三个组件的现有 package.json 均声明 MIT，但源工作台没有完整根 LICENSE 文本，也没有完整第三方说明。这份候选保留原声明，不代表替维护者新增授权或确认全部权利归属。

The existing manifests of all three components declare MIT. The source workbench does not provide a complete root LICENSE or complete third-party notices. This candidate preserves those declarations without making a new license grant or establishing all ownership rights on the maintainer's behalf.

公开发布前由维护者确定并补齐完整许可证、必要的作者/第三方声明，核对扩展代码来源及与宿主接口的关系。宿主 DSH/Cortico 源码、原生补丁、第三方 node_modules 均未打入本候选。source map 只包含本候选扩展/共享核心来源。

Before public publication, the maintainer should determine and supply the complete license text and required attribution/notices, reviewing code provenance and host-interface dependencies. DSH/Cortico host source, native patches and third-party node_modules are excluded. Source maps contain only the included extension/shared-core source.

`private:true` 阻止意外 npm 发布，不限制文件被复制到 GitHub；它也不是 GitHub 仓库可见性配置。仓库可见性由维护者在远程发布时单独选择。

`private:true` prevents accidental npm publication; it does not prevent copying files to GitHub and does not configure GitHub repository visibility. The maintainer chooses remote visibility separately.
