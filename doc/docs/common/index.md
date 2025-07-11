## 略語の対応表

システム上で使用する略語と本来の名称を一覧にまとめます。

| 略語 | 本来の名称 |
| -- | -- |
| spe | SPLATS ENTRANCE |
| Amazon DynamoDB | dynamodb |
| Amazon S3 | s3 |

## AWSサービスの命名規則

以下の規則でAWSサービスを命名します。

```txt
{AWSサービス名}-{サービス名}-{環境}-{用途}
```

例えば、`Amazon DynamoDB` でユーザーテーブルを定義する際、その名称は `dynamodb-spe-main-user` となります。