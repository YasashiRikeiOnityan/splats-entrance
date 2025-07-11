# ユーザーグループテーブル

## 概要

## 基本構造

| 属性名 | データ型 |
| -- | -- |
| PK | usergroup_id (String) |
| SK | なし |
| GSIPK1 | usergroup_type (Enum) |

## 属性

=== "`usergroup_id`"

    ユーザーグループID

    ```ts
    usergroup_id: string
    ```

=== "`usergroup_type`"

    ユーザー種別

    ```ts
    user_type: "department" | "destination"
    ```

    | 種類 | 説明 |
    | -- | -- |
    | `department` | 部署 |
    | `destination` | 訪問先 |

=== "`usergroup_name`"

    ユーザーグループ名

    ```ts
    usergroup_name: string
    ```

=== "`guide_type`"

    案内タイプ

    ```ts
    guide_type: "phone_number" | "image"
    ```

    | 種類 | 説明 |
    | -- | -- |
    | `phone_number` | 社員の内線番号を表示 |
    | `image` | 案内画像を表示 |

=== "`guide_image`"

    案内画像

    ```ts
    guide_image: {
        name: string,
        key: string
    }
    ```

    `name` はアップロード時のファイル名です。 `key` はデータを保持しているS3オブジェクトのプレフィックスキーです。