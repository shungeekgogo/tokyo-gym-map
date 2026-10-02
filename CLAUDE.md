# 東京ジムマップ — 作業ルール

## GitHub と常に同期する（複数 PC で作業）
- 作業開始時は、まず GitHub の最新版（今のブランチの追跡先。通常は `origin/main`）とこの PC のファイルを同期する。`.claude/hooks/sync-from-github.sh`（SessionStart フック）が自動で fetch・fast-forward し、結果をセッション冒頭に表示する。未コミットの変更や競合で自動更新できなかったと表示されたら、作業に入る前にユーザーに伝えて解決する。
- ファイルを変更したら、そのたびにコミットして GitHub に push する。作業終了前に、すべての変更がコミット・push 済みであることを確認する（`.claude/hooks/check-pushed.sh`（Stop フック）が未反映の変更を検出すると差し戻す）。
