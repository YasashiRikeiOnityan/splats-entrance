# 予約テーブル

## 概要

予約情報を管理するテーブルです。部署内の人がした予約、自身がした予約のアクセスパターンをサポートし、来客者が端末上で予約番号を入力して予約情報を取得できるように設計されています。

## 基本構造

| 属性名 | データ型 |
| -- | -- |
| PK | reservation_id (String) |
| SK | usergroup_id#user_id (String) |
| GSIPK1 | usergroup_id (String) |
| GSIPK2 | user_id (String) |
| GSIPK3 | reservation_number (String) |
| TTL | expires_at (Number) |

## 属性

=== "`reservation_id`"

    予約ID

    ```ts
    reservation_id: string
    ```

=== "`usergroup_id`"

    ユーザーグループID

    ```ts
    usergroup_id: string
    ```

=== "`user_id`"

    ユーザーID

    ```ts
    user_id: string
    ```

=== "`reservation_number`"

    予約番号

    ```ts
    reservation_number: string
    ```

    6桁の数字で構成される予約番号です。来客者が端末上で入力して予約情報を取得する際に使用されます。

=== "`reservation_date`"

    予約日

    ```ts
    reservation_date: string
    ```

    YYYY-MM-DD形式で予約日を記録します。

=== "`reservation_time`"

    予約時間

    ```ts
    reservation_time: string
    ```

    HH:MM形式で予約時間を記録します。

=== "`user_name`"

    来客者名

    ```ts
    visitor_name: string
    ```

=== "`company_name`"

    来客者会社名

    ```ts
    visitor_company: string
    ```

=== "`phone_number`"

    来客者電話番号

    ```ts
    visitor_phone: string
    ```

=== "`destination`"

    訪問先

    ```ts
    destination: string
    ```

    `usergroup_id` が入ります。登録時の情報を保持し、参照時に存在しない `usergroup_id` であった場合は登録情報を更新してもらいます。

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
        usergroup_id: string
    }
    ```

    登録時の情報を保持し、参照時に存在しない `usergroup_id` であった場合は登録情報を更新してもらいます。

=== "`status`"

    予約ステータス

    ```ts
    status: "pending" | "confirmed" | "cancelled" | "completed"
    ```

    | ステータス | 説明 |
    | -- | -- |
    | `pending` | 予約待ち |
    | `confirmed` | 予約確定 |
    | `cancelled` | 予約キャンセル |
    | `completed` | 訪問完了 |

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

    予約日から1年後の時間をUNIXエポック時間形式で登録します。
