---
title: 概要
description: TransitCore とは何か、その仕組みと設計理念について説明します。
---

# 概要

**TransitCore** へようこそ。

TransitCore は Minecraft 向けのモジュラー式鉄道シミュレーションフレームワークで、強力な Addon システムと **LuaTC** スクリプト言語を通じて、リアルな鉄道ネットワークを構築できるように設計されています。

従来の鉄道 MOD とは異なり、TransitCore 自体は車両やインフラを直接提供しません。フレームワークはシミュレーションエンジンを提供し、列車、地下鉄、路面電車、軌道、信号機などのコンテンツは独立した Addon として配布されます。

<Alert severity="info">

TransitCore は **エンジン** と **コンテンツ** を完全に分離しています。フレームワークが各種シミュレーションシステムを提供する一方、Addon が車両、軌道、信号機、駅、その他すべての鉄道要素をもたらします。

</Alert>

## なぜ TransitCore なのか？

TransitCore は 4 つの基本原則に基づいて開発されました。

### リアリズム

TransitCore の目標は、鉄道ネットワークの運行を可能な限り忠実に再現しつつ、Minecraft に完全に統合することです。

このフレームワークは特に以下をサポートします：

- 高度な車両シミュレーション。
- リアルなブレーキシステム。
- 鉄道信号システム。
- 電気システム。
- 乗客管理。
- マルチプレイヤー同期。
- 高速鉄道路線。

### モジュール性

TransitCore のすべてはモジュラー式に設計されています。

フレームワーク自体には動作に必要なエンジンのみが含まれています。

車両、インフラ、サウンド、テクスチャ、ユーザーインターフェース、ゲームプレイ拡張は、それぞれ独立してインストール、更新、削除可能な Addon として配布されます。

### パフォーマンス

TransitCore は大規模な鉄道ネットワークを効率的に処理できるよう設計されています。

レンダリング、物理、ネットワーク、シミュレーションは、リアルな挙動を保ちながら不要な計算を抑えるよう最適化されています。

### 拡張性

TransitCore が提供するすべての機能は、フレームワークの公式スクリプト言語である **LuaTC** を通じてアクセスできます。

これにより開発者は、TransitCore の Java コードを変更することなく、完全な Addon を作成できます。

## アーキテクチャ

TransitCore は連携する複数の独立したシステムで構成されています。

```text title="TransitCore のアーキテクチャ"
TransitCore
├── Core Engine
├── Physics Engine
├── Rendering Engine
├── Railway Engine
├── Signaling Engine
├── Electrical Engine
├── Audio Engine
├── Animation Engine
├── Networking Engine
├── LuaTC Runtime
└── Addon Loader
```

各システムはフレームワークの特定の部分を担当し、他のシステムとは安定した公開 API を通じて通信します。

## LuaTC

LuaTC は TransitCore の公式スクリプト言語です。

Lua をベースにしつつ、鉄道シミュレーションのために特別に設計された API を追加しています。これにより開発者は Minecraft の内部メカニズムに直接アクセスすることなく、フレームワークとやり取りできます。

```luatc title="車両を作成"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

ほとんどの Addon は LuaTC のみで完全に開発できます。Java は TransitCore の内部動作を拡張する場合にのみ必要です。

</Alert>

## Addon

TransitCore は完全に Addon ベースのアーキテクチャに依存しています。

各 Addon は独立して読み込まれ、LuaTC を通じてフレームワークと通信します。

Addon は例えば以下を追加できます：

- 列車。
- 地下鉄。
- 路面電車。
- ケーブルカー。
- 鉄道軌道。
- 信号機。
- 架線。
- 駅。
- ユーザーインターフェース。
- サウンド。
- ゲームプレイ拡張。

読み込み中にエラーが発生した場合、TransitCore はフレームワークや他の Addon の起動を妨げることなく、その Addon を自動的に無効化します。

```text title="Addon の構成例"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Addon の隔離">

欠陥のある Addon があっても、TransitCore の起動は妨げられません。フレームワークはエラーを自動的に検出し、該当する Addon のみを無効化して、他のすべての Addon の読み込みを続行します。

</Alert>

## ドキュメント

ドキュメントはいくつかのセクションに分かれています。

| セクション | 説明 |
|---------|-------------|
| はじめに | TransitCore をインストールし、最初の Addon を作成する。 |
| LuaTC | フレームワークの公式スクリプト言語を学ぶ。 |
| ガイド | TransitCore の主要システムを網羅する詳細なチュートリアル。 |
| API リファレンス | サービス、クラス、メソッド、イベントの完全なドキュメント。 |
| 例 | ベストプラクティスとフレームワークの機能を示すサンプルプロジェクト。 |

## オープンソース

TransitCore は **Fire Sparks Studio** によって開発されるオープンソースプロジェクトです。

ソースコード、ドキュメント、問題追跡システムは公開されており、コミュニティが改善を提案したり、不具合を報告したり、フレームワークの開発に貢献したりできるようになっています。

## 次のステップ

TransitCore を初めてご利用になる方は、**インストール** に進んで開発環境を整え、最初の Addon を作成してください。