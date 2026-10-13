# 发布评审状态 / Release review status

日期 / Date: **2026-10-13, Asia/Shanghai**  
建议 / Recommendation: **私有仓库评审与备份 / Private repository review and backup**  
正式稳定版 / Stable release: **未就绪 / Not ready**  
远程状态 / Remote state: **生成时未上传；用户已授权私有 GitHub 备份，此后状态以仓库提交为准 / Not uploaded at generation; user authorized private GitHub backup; see subsequent repository commits**

| 核验 / Evidence | 状态 / Status |
|---|---|
| 类型检查 / Type checking | PASS |
| 隔离回归 / Isolated regression | 120 PASS / 0 FAIL / 0 SKIP |
| Gateway 0.1.9 / World 0.1.4 冻结包 / Frozen archive comparison | PASS，逐文件一致 / Per-file match |
| 原构建清单 / Original build manifest | 45 项一致；1 项私人交接文档在审计后变化；无执行源码/产物漂移 / 45 match; one private handoff changed after audit; no executable source/artifact drift |
| 真人 QQ 链 / Human QQ roundtrip | 一次 send 以 blocked 结束并回报原会话 / One send with confirmed blocked end and return to the original conversation |
| Codex 当前接入 / Current Codex access | 2026-10-13 22:52 Asia/Shanghai，现有桌面 IPC 发现 HTTP 200、无发现错误；历史原生 send/同ID/pause PASS；当前真人 QQ 全链待验 / Existing desktop discovery works; prior native send/same-ID/pause passed; current human QQ chain remains unaccepted |
| 底层长任务 / Underlying long task | 未在该操作中完成出包 / Build not completed in that operation |
| 连续监测 / Monitoring | 24h5m55s、1447 样本、一次查询超时 / 1447 samples with one read timeout |
| 24h 无异常稳定性 / 24h error-free stability | NOT ACCEPTED |
| 新机器安装、干净 clone、CI / Fresh install, clean clone, CI | NOT RUN；有本机路径/宿主依赖 / Host path and dependency constraints remain |
| 隐私扫描 / Privacy scan | 见 SANITIZATION.json；定向检查，不等于穷尽审计 / Targeted checks, not exhaustive assurance |
| 许可证和第三方说明 / License and notices | 待维护者补齐审阅 / Pending maintainer review |

公开通用发行前的工作 / Before a portable public release:

1. 修复 terminal blocked 后暗示自动继续的话术，重新测试真实分段任务与 QQ 回报。 / Correct terminal-blocked wording and verify separately authorized stages and QQ reports.
2. 把绝对路径、依赖与保护目录通用化，给出宿主版本/原生修复兼容矩阵和干净安装验证。 / Generalize paths/dependencies/protected roots and provide host compatibility and clean-install evidence.
3. 保留既有异常，补足所声明的稳定性与各后端验收，不将不同层次通过混合。 / Retain failures and complete the claimed stability and backend coverage without conflating acceptance layers.
4. 审阅完整许可、白名单、最终 README 和公开范围，再独立发布反向控制项目，避免与两个正向 World 重复打包。 / Review licensing, allowlist, README and disclosure scope before publishing reverse control independently, without duplicating the two forward Worlds.

准备本候选没有修改生产运行行为、启动模型工作、发送 QQ、改变授权/预算、迁移状态库或重投旧操作。快照生成时没有创建仓库、推送、发布 Release 或提交上游 issue；随后私有备份不代表公开稳定发行。

Preparation did not change production behavior, submit model work, send QQ messages, change scope/budgets, migrate state or replay operations. No repository, push, Release or upstream issue existed at snapshot generation; later private backup does not constitute a public stable release.
