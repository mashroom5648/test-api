# test-api

ビービーメディア テスト用API

## 概要

このリポジトリは、[my-json-server.typicode.com](https://my-json-server.typicode.com/) を利用した簡易APIのテスト環境です。  
GitHub上のJSONファイルをREST APIとして利用できるため、モックサーバとして手軽にAPIの動作検証が行えます。

APIパーミッション・ロール管理システムのサンプルデータも含んでおり、権限管理機能の開発・テストに利用できます。

## 使用方法

### 基本的な使用方法

1. 本リポジトリをフォークし、`db.json` など任意のJSONファイルを作成してデータを用意します。
2. 下記のURL形式でAPIを利用できます：

```
https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/<エンドポイント>
```

### 例

- ユーザー一覧取得

  ```
  GET https://my-json-server.typicode.com/mashroom5648/test-api/users
  ```

- 特定ユーザー取得

  ```
  GET https://my-json-server.typicode.com/mashroom5648/test-api/users/1
  ```

## API パーミッション・ロール管理システム

このリポジトリには、APIのパーミッション・ロール管理システムのサンプルデータが含まれています。

### ディレクトリ構造

```
api/
├── permissions/
│   ├── operations.json      # 基本操作権限（作成、閲覧、更新、削除）
│   ├── list.json           # パーミッション一覧
│   └── groups.json         # パーミッショングループ
└── roles/
    ├── admin/
    │   ├── detail.json     # 管理者ロール詳細
    │   └── update.json     # 管理者ロール更新用データ
    └── director/
        ├── detail.json     # ディレクターロール詳細
        └── update.json     # ディレクターロール更新用データ
```



### 利用可能なエンドポイント

- **パーミッション一覧**
  ```
  GET https://my-json-server.typicode.com/mashroom5648/test-api/permissions
  ```

- **パーミッショングループ一覧**
  ```
  GET https://my-json-server.typicode.com/mashroom5648/test-api/permissionGroups
  ```

- **パーミッション操作一覧**
  ```
  GET https://my-json-server.typicode.com/mashroom5648/test-api/permissionOperations
  ```

- **ロール一覧**
  ```
  GET https://my-json-server.typicode.com/mashroom5648/test-api/roles
  ```

> ※ `/roles/admin/detail` などの階層パスではデータは取得できません。`/roles` で全ロールを取得し、必要に応じてクライアント側でフィルタしてください。


### データ構造の説明

#### パーミッション操作 (`permissionOperations`)
基本的なCRUD操作の定義：
- `CREATE`: 作成権限
- `READ`: 閲覧権限
- `UPDATE`: 更新権限
- `DELETE`: 削除権限

#### パーミッション一覧 (`permissions`)
システム内の具体的なパーミッション：
- オーディション管理（作成・閲覧・更新・削除）
- タレント管理（作成・閲覧・更新・削除）
- キャスティング管理（作成・閲覧・更新・削除）
- レポート閲覧（閲覧のみ）
- システム設定（作成・閲覧・更新・削除）

#### パーミッショングループ (`permissionGroups`)
関連するパーミッションをグループ化：
- 基本管理: オーディション、タレント、キャスティング管理
- システム管理: レポート閲覧、システム設定

#### ロール一覧 (`roles`)
- **管理者**: 全権限を持つロール（permissions: [1, 2, 3, 4, 5]）
- **ディレクター**: オーディション管理・タレント管理・レポート閲覧の権限を持つロール（permissions: [1, 2, 4]）

## 参考リンク

- [my-json-server.typicode.com公式ドキュメント](https://github.com/typicode/json-server)
