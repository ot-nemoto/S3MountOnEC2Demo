# S3MountOnEC2Demo

## はじめに

- Regionは `us-east-1` を利用（東京リージョンでは、S3Bucketがすぐにマウントできないため）
- デプロイ後は、SSMセッションマネージャからログイン可能（CloudFormationのOutputsでURLは確認）
- マウント先は `/mnt/s3`

## デプロイ

s3fsを使ってS3をマウントするデモ

```sh
aws cloudformation create-stack \
    --region us-east-1 \
    --stack-name s3-mount-by-s3fs-demo \
    --capabilities CAPABILITY_IAM \
    --template-body file://template-s3fs.yaml
```

goofysを使ったS3をマウントするデモ

```sh
aws cloudformation create-stack \
    --region us-east-1 \
    --stack-name s3-mount-by-goofys-demo \
    --capabilities CAPABILITY_IAM \
    --template-body file://template-goofys.yaml
```
