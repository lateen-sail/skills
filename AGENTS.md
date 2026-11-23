# ガイドライン

## 作成・更新方針

- 文章は `my-writing` スキルの推奨事項と禁止事項に従う。
- スキル名は `my-xxx` とする。機能が伝わり、似た機能のスキルが名前順で近くなるように付ける。
- `SKILL.md` には、判断や実行に必要な内容だけを書く。
- `description` は、適用場面が伝わる表現にする。

## 禁止事項

- `my-` で始まらないスキルの作成、編集、削除。

## ファイル構成

```mermaid
treeView-beta
  ~/.agents/skills/my-xxx/
    SKILL.md ## 必須
    PFD.md ## 必須
    agents/openai.yaml ## 必須
    scripts/ ## 任意：実行するコード
    templates/ ## 任意：出力のひな形
    references/ ## 任意：必要なときに読む参考資料
```

## `SKILL.md` の骨格

```markdown
---
name: my-xxx
description: xxx
---

# スキル名

## 目的


## 制約

### 推奨事項

- xxx
- xxx

### 禁止事項

- xxx
- xxx

## ワークフロー

1. 
2. 

## 出力

- 場所
- 形式

## 検証

- xxx
- xxx
```

## `PFD.md` の骨格

```mermaid
swimlane-beta TD
  subgraph SAMPLE
    A[xxx]
    B[xxx]
  end
  A --> B
```

## `agents/openai.yaml` の骨格

```yaml
interface:
  display_name: "<表示名>"
  short_description: "<25字以内>"
  default_prompt: "$my-xxx を使って、<目的>してください。"
policy:
  allow_implicit_invocation: false
```

## 確認と続行

- 依頼の範囲内で元に戻せる操作は、確認せず進める。
- 元に戻せない操作、外部へ反映する操作、解釈によって結果が大きく変わる作業は、実行前に確認する。
