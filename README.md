# test-api

Generic Test API Template

## 概要

このリポジトリは、[my-json-server.typicode.com](https://my-json-server.typicode.com/) を利用した簡易APIのテンプレートです。  
GitHub上のJSONファイルをREST APIとして利用できるため、モックサーバとして手軽にAPIの動作検証が行えます。

基本的なAPIデータ構造のサンプルが含まれており、様々な開発・テストプロジェクトに利用できます。

## 使用方法

### 基本的な使用方法

1. 本リポジトリをフォークし、`db.json` など任意のJSONファイルを作成してデータを用意します。
2. 下記のURL形式でAPIを利用できます：

```
https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/<エンドポイント>
```

### 例

- データ一覧取得

  ```
  GET https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/items
  ```

- 特定データ取得

  ```
  GET https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/items/1
  ```

## API データ構造のサンプル

このリポジトリには、基本的なAPIデータ構造のサンプルが含まれています。

### ディレクトリ構造

```
api/
├── sample/
│   ├── items.json           # サンプルアイテムデータ
│   ├── list.json           # リストデータ
│   └── config.json         # 設定データ
└── templates/
    ├── basic/
    │   ├── detail.json     # 基本詳細データ
    │   └── update.json     # 更新用データ
    └── advanced/
        ├── detail.json     # 高度な詳細データ
        └── update.json     # 高度な更新用データ
```



### 利用可能なエンドポイント

- **アイテム一覧**
  ```
  GET https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/items
  ```

- **サンプルデータ一覧**
  ```
  GET https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/samples
  ```

- **設定データ一覧**
  ```
  GET https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/config
  ```

- **テンプレート一覧**
  ```
  GET https://my-json-server.typicode.com/<GitHubユーザー名>/<リポジトリ名>/templates
  ```

> ※ `/templates/basic/detail` などの階層パスではデータは取得できません。`/templates` で全テンプレートを取得し、必要に応じてクライアント側でフィルタしてください。


### データ構造の説明

#### 基本操作 (`operations`)
基本的なCRUD操作の定義：
- `CREATE`: 作成
- `READ`: 閲覧
- `UPDATE`: 更新
- `DELETE`: 削除

#### アイテム一覧 (`items`)
システム内の基本的なアイテム：
- アイテム管理（作成・閲覧・更新・削除）
- カテゴリ管理（作成・閲覧・更新・削除）
- タグ管理（作成・閲覧・更新・削除）
- 設定管理（作成・閲覧・更新・削除）

#### サンプルグループ (`samples`)
関連するデータをグループ化：
- 基本サンプル: アイテム、カテゴリ管理
- 高度なサンプル: タグ、設定管理

#### テンプレート一覧 (`templates`)
- **基本テンプレート**: 基本的な権限を持つテンプレート（items: [1, 2, 3, 4]）
- **高度なテンプレート**: より多くの機能を持つテンプレート（items: [1, 2, 3, 4, 5]）

## 参考リンク

- [my-json-server.typicode.com公式ドキュメント](https://github.com/typicode/json-server)
