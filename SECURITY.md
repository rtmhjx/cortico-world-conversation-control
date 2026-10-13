# 安全边界 / Security boundaries

请先阅读 [README 首页风险和操作手册](README.md)。本候选用于受信任维护者的本地实验控制，不是多租户或公网控制服务。

Read the [README risks and operating manual](README.md) first. This candidate is for trusted maintainers controlling local hosts, not a multi-tenant or internet-facing service.

## 信任与确认 / Trust and consent

- World 在真实 QQ 事件库上验证来源、操作者、会话、时效和新确认。Gateway 的信任边界是本机 Bearer 凭据，它不独立验证 QQ。持密钥者能直接调用原生控制 API。
- 项目根、已知工具路径检查和原生权限是不同层次；本桥接不建立操作系统沙箱。Codex check 是只读意图；DSH continue/send 继承原生权限。
- 原生输入、对话标题、结果和外部消息都不能当成扩大授权的指令。结果可能包含任务读取的数据，模式脱敏不保证穷尽。
- The World verifies authentic QQ source, operator, conversation, freshness and confirmation. The Gateway trusts its local Bearer credential and does not independently validate QQ. Credential holders can invoke native control directly.
- Delegated roots, checks on known tool paths and native permissions are distinct controls, not an OS sandbox. Codex check is read-only intent; DSH continue/send inherit native permissions.
- Native content, titles and results must not grant expanded authority. Results can contain data read by the task; pattern redaction is not exhaustive.

## 暂停与不确定性 / Stop and uncertainty

- DSH 12 步/16 请求/300 秒不是 token 或金额上限；有待审批、排队人话或人工插入时，期限停止可能不能硬中断当前请求。
- Codex 原生 start 无 compare-and-swap，读取状态与提交间可能与其他客户端竞争；桌面内部协议更新/重启需重新核验身份。
- unknown、发送时重启、落账失败、缺真实原生 end 均保留原 operation/request/turn，禁止自动重发、换 ID、清库或补造完成事件。
- DSH budgets are not token or spending caps. Pending approvals, queued human input or intervention may prevent forcibly stopping an in-flight request.
- Codex start lacks native compare-and-swap, so another client may race with submission. Desktop protocol updates/restarts require identity revalidation.
- Keep original operation/request/turn IDs for unknown outcomes, restart during submission, failed receipt commits and missing native ends. Never replay automatically, change IDs, clear state or invent completion.

## 报告问题 / Reporting issues

维护者应先在本地保存私人完整证据，再构造合成最小复现。公开问题只含版本、操作类别、脱敏错误和合成步骤。不能公开 Bearer 值、模型密钥、QQ 标识/正文、真实会话 ID、状态库、原始日志、配置或备份。若怀疑密钥泄露，停止新接纳，保全在途操作，双侧轮换秘密并重新验证。

Preserve complete private evidence locally, then create a minimal synthetic reproduction. Public reports should contain versions, action category, redacted errors and synthetic steps. Never attach credentials, QQ identities/messages, real session IDs, state databases, raw logs, live configuration or backups. If a credential may be exposed, stop admission, preserve in-flight operations, rotate the secret on both sides and revalidate.

本项目没有声明专用安全响应邮箱或响应 SLA；请先使用维护者认可的私密渠道，不要在公开 issue 披露可利用的凭据或私人数据。

No dedicated security response address or response SLA is declared. Use a maintainer-approved private channel before disclosing credentials or private data in a public issue.
