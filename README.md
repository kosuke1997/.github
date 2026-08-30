# `<org>/.github` — 組織共通ワークフロー

このディレクトリの中身を GitHub Organization 直下の **`.github` という名前のリポジトリ**に置く。

```
<org>/.github
└── .github/workflows/autopilot.yml   ← 再利用ワークフロー（workflow_call）
```

パスが `.github/.github/workflows/` と二重になるのは仕様。外側がリポジトリ名。

## 前提

- Organization Secrets に `ANTHROPIC_API_KEY` を登録する（全リポジトリで共有される）
- 各プロダクトリポジトリで `claude /install-github-app` を実行済みであること

## 呼び出し側

各プロダクトの `.github/workflows/autopilot.yml` から呼ぶ。
[repos/product-template/.github/workflows/autopilot.yml](../product-template/.github/workflows/autopilot.yml) を参照。

## このファイルだけでは何も起きない

Phase 2 でプロダクト側から呼び出して初めて動く。
