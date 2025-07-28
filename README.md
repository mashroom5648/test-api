# test-api

ビービーメディア テスト用API

## 概要

このリポジトリは、[my-json-server.typicode.com](https://my-json-server.typicode.com/) を利用した簡易APIのテスト環境です。  
GitHub上のJSONファイルをREST APIとして利用できるため、モックサーバとして手軽にAPIの動作検証が行えます。

## 使用方法

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

## 参考リンク

- [my-json-server.typicode.com公式ドキュメント](https://github.com/typicode/json-server)
