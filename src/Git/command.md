# Gitコマンド

- [cherry-pick](#cherry-pick) 
　
## cherry-pick  
ローカルリポジトリに登録された任意のブランチのコミットを適用したい場合に使う。

コミットしたいブランチ上で以下のコマンドを打つ。
```
git cherry-pick (適用したいコミットID)
```
複数コミットの場合  
&emsp;コミットAからコミットBまでの間のコミットを、取り込む場合は以下のコマンド
```
git cherry-pick (コミットA ID)..(コミットB ID)
```

## 参考
[git cherry-pickを完全マスター!特定コミットのみを取り込む方法](https://www.sejuku.net/blog/71544)


