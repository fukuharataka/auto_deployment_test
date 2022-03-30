。# auto_deployment_test

## 概要

デプロイを自動化してみるテストブランチ。
今回は、DjangoのDockerコンテナをGitHubでpushして、それを自動でデプロイまでしてみる。
できればフロントエンドもやりたい。


## 使用技術（予定）

- インフラ周り
  - CodePipeline
  - CodeBuild
  - AWS ECR
  - AWS ECS
  - Docker
- コード周り
  - Django
  - Python3


## 詳細など

### ブランチ戦略

開発するブランチのパターンとして以下の表のような3つが存在する。
それぞれ、デプロイタイミングでデプロイされる。
マージに関しての制限(例として、featureからmainにマージするときレビュー必須など)は、GitHub側で対応するようにする。


| ブランチ名 | デプロイタイミング | 概要 |
| -- | -- | -- |
| production | mainからマージされた時 | 本番環境。ステージングであるmainからしかマージされない。 |
| main | 各featureブランチからマージされた時 | ステージング環境。本番にマージする前featureブランチを一旦マージするブランチ。本番との差分は、デプロイする分のみ。デプロイする分は速やかにマージする。 |
| feature (ブランチ名は任意) | pushされたとき | 各々開発するためのブランチ。ブランチ名は任意。 無数にブランチがある。|

※ レビュー必須などはgithub側で対応する
※ TODO: ブランチ戦略の図作って載せる。




## 参考

- [CodePipeline を使った Gitブランチ運用をまとめてみた](https://dev.classmethod.jp/articles/various-git-branch-flows-for-aws-codepipeline/)
- [AWS CodePipeline で CI/CD の仕組みを構築したお話](https://blog.spacemarket.com/code/ci-cd-codepipeline/)