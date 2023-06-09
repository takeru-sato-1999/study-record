# 第三章クラス設計

## 3.1 クラス単体で正常に動作するように設計する

- 頑強なクラスの構成要素
  - インスタンス変数
  - インスタンス変数を不正状態から防御し、正常に操作するメソッド
- 自己防衛責務

## 3.2 成熟したクラスへ成長させる設計術

- コンストラクタで確実に正常値を設定する
  - ガード節
- 計算ロジックをデータ保持側に寄せる
- 不変で思わぬ動作を防ぐ
- 変更したい場合新しいインスタンスを作成する

  ```
  class Money {
      //省略
      Money add(int other) {
          int added = amount + other
          return new Money(added, currency)
      }
  }

  ```

- メソッド引数やローカル変数にも final を付け不変にする
- 値の渡し間違いを型で防止する
- 現実の営みにないメソッドを追加しないこと

## 3.3 まとめ

- クラス設計とは、インスタンス変数を不正状態に陥らせないための仕組みづくり
- 高凝集
- カプセル化

## 3.4 設計パターン

- 完全コンストラクタ
  - インスタンス変数数＝コンストラクタの引数数
  - ガード節
  - インスタンス変数に final 修飾子
- 値オブジェクト
  - アプリケーションで取り扱う値、概念
