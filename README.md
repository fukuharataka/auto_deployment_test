# auto_deployment_test

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


## 参考

- [CodePipeline を使った Gitブランチ運用をまとめてみた](https://dev.classmethod.jp/articles/various-git-branch-flows-for-aws-codepipeline/)
- [AWS CodePipeline で CI/CD の仕組みを構築したお話](https://blog.spacemarket.com/code/ci-cd-codepipeline/)