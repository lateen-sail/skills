```mermaid
swimlane-beta TD
  subgraph USER[ユーザー]
    A[対象と目的を依頼]
    F[結果を確認]
  end
  subgraph AGENT[エージェント]
    B[推奨事項と禁止事項を確認]
    C[文章を編集]
    D{検証}
    E[既存は上書き・新規はケバブケースで作成]
  end
  A --> B --> C --> D
  D -- 問題あり --> C
  D -- 問題なし --> E --> F
```
