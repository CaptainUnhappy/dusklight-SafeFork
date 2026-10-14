# dusklight-SafeFork

这是 [TwilitRealm/dusklight](https://github.com/TwilitRealm/dusklight) 的 SafeFork。

- [main](https://github.com/CaptainUnhappy/dusklight-SafeFork/tree/main) 及其他上游分支：保留源码和原始 Git 历史，沿用各文件原有许可；主仓库许可证见 [LICENSE.md](https://github.com/CaptainUnhappy/dusklight-SafeFork/blob/main/LICENSE.md)。
- `sync-control`：默认控制分支，仅保存安全同步工作流和说明。

## 同步规则

- 计划每小时检查全部上游分支和标签；GitHub 定时运行可能延迟或跳过。
- 只新增缺失引用、快进更新分支；不合并、不强推、不删除已有引用，也不创建自动备份分支。
- 上游不可访问、分支历史分叉或未经审核的标签冲突时停止，保留 Fork 现状。
- 同步使用短期 `GITHUB_TOKEN`；上游继承的构建、发布工作流默认不启用。
- 只同步 Git 分支和标签，不复制 Releases、发布附件、Issues、Actions 历史或 Git LFS 对象。

## 子模块边界

主仓库中的子模块引用会原样保留，但以下四个独立仓库的内容和引用不属于本次同步范围：

- `extern/aurora`
- `extern/borealis`
- `mods/randomizer`
- `mods/cosmetics`

子模块地址见 [.gitmodules](https://github.com/CaptainUnhappy/dusklight-SafeFork/blob/main/.gitmodules)。

可在 [Safe Fork Sync](https://github.com/CaptainUnhappy/dusklight-SafeFork/actions/workflows/safe-fork-sync.yml) 查看记录或手动运行；选择 `dry_run` 仅检查、不写入。

完整规则见 [SafeFork 规范](https://github.com/CaptainUnhappy/SafeFork/blob/main/skills/safefork/references/spec.md)。控制分支的同步工作流采用 [MPL-2.0](LICENSE)，不改变上游源码许可证。
