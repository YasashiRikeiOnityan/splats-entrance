# ユーザーテーブル

## 概要

## 基本構造

| 属性名 | データ型 |
| -- | -- |
| PK | user_id (String) |
| SK | usergroup_id (String) |
| GSIPK1 | usergroup_id (String) |
| GSIPK2 | user_type (Enum) |
| GSIPK3 | phone_number (String) |
| TTL | expires_at (Number) |

## 属性

=== "`user_id`"

    ユーザーID

    ```ts
    user_id: string
    ```

=== "`usergroup_id`"

    ユーザーグループID

    ```ts
    usergroup_id: string
    ```

=== "`user_type`"

    ユーザー種別

    ```ts
    user_type: "admin" | "employee" | "visitor_badge" | "visitor_card"
    ```

    | 種類 | 説明 |
    | -- | -- |
    | `admin` | サービス管理者 |
    | `employee` | 社員 |
    | `visitor_badge` | 来客（一般） |
    | `visitor_card` | 来客（業者） |

=== "`phone_number`"

    電話番号

    ```ts
    phone_number: string
    ```

    社員は内線番号を来客（一般）は電話番号を登録する。

=== "`user_name`"

    ユーザー名

    ```ts
    user_name: string
    ```

=== "`company_name`"

    会社名

    ```ts
    company_name: string
    ```

    `user_type` が `visitor_badge` または `visitor_card` のときに登録されます。

=== "`destination`"

    訪問先

    ```ts
    destination: string
    ```

    `user_type` が `visitor_badge` または `visitor_card` のときに登録されます。

    `destination` には `usergroup_id` が入ります。登録時の情報を保持し、参照時に存在しない `usergroup_id` であった場合は登録情報を更新してもらいます。

=== "`business`"

    用件

    ```ts
    business: string
    ```

=== "`person_in_charge`"

    担当者

    ```ts
    person_in_charge: {
        user_id: string,
        usergroup_id: stinrg
    }
    ```

    登録時の情報を保持し、参照時に存在しない `usergroup_id` であった場合は登録情報を更新してもらいます。

=== "`created_at`"

    作成日時

    ```ts
    created_at: string
    ```

=== "`updated_at`"

    更新日時

    ```ts
    updated_at: string
    ```

=== "`expires_at`"

    削除予定日時

    ```ts
    expires_at: number
    ```

    `user_type` が `visitor_badge` のときに登録されます。

    登録日から1年後の時間をUNIXエポック時間形式で登録します。