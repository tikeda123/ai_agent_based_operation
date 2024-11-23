# AIマルチエージェント 運用管理システム

## システム概要

本システムは、システム運用管理を効率化・自動化するための3つのAIエージェントで構成された知的マルチエージェントシステムです。各エージェントが特定の役割を担い、相互に連携することで、システムの監視から問題解決までを一貫して実行します。

## システムアーキテクチャ

システムは以下の3つの専門AIエージェントで構成されており、それぞれが独自の役割と専門性を持ち、協調して動作します：

### 1. コミュニケーションエージェント (CA)
人間の運用者とシステムの橋渡し役として機能し、以下の役割を担います：
- 運用者とのインターフェースとして、対話的な情報のやり取りを実現
- システムの診断状況をIDAから受け取り、運用者に分かりやすく提示
- 解決策の提案をSRAから受け取り、運用者に提示
- 承認された復旧プロセスをSRAに転送して実行

### 2. インテリジェント診断エージェント (IDA)
システムの健全性監視と問題診断の中核として機能し、以下の役割を担います：
- Grafanaとサーバログを活用したリアルタイムのシステム監視
- 異常検知と根本原因分析の実施
- LLM（大規模言語モデル）を活用した高度な診断分析の実行
- 診断結果のCAへの報告

### 3. スマート解決策エージェント (SRA)
問題解決のための実行部隊として機能し、以下の役割を担います：
- LLM分析を用いた最適な対策案の生成と提案
- Ansible実行APIを利用した自動復旧手順の計画と実施
- 解決策の実行状況のモニタリングとフィードバック

## システムの特徴

### インテリジェントな自動化
- AIによる高度な診断と解決策の提案
- 運用タスクの自動化による効率化

### 柔軟な対応力
- LLMを活用した状況適応型の問題解決
- 過去の事例を学習した改善提案

### 安全性の確保
- 人間の運用者による承認プロセスの組み込み
- 段階的な実行と検証の仕組み

### 拡張性
- モジュール化された設計による機能追加の容易さ
- 新しいツールや技術の統合が可能

## 動作の流れ

### 1. システム監視とイベント検知
- IDAが継続的にシステムを監視
- 異常を検知した場合、詳細な診断を実行

### 2. 問題分析と解決策の生成
- IDAが診断結果をCAに報告
- SRAが適切な解決策を生成

### 3. 運用者との対話と承認
- CAが運用者に状況と解決策を提示
- 運用者の承認を得て実行プロセスを開始

### 4. 解決策の実行と検証
- SRAが承認された解決策を実行
- 実行結果を監視し、成功を確認

必要要件

Python 3.8以上
pip (Pythonパッケージ管理ツール)
OpenAI API キー（Chat GPT APIを使用するため）

インストール手順

このリポジトリをクローンします：

bashCopygit clone https://github.com/tikeda123/ai_agent_based_operation.git
cd ai_agent_based_operation

仮想環境を作成し、有効化します：

bashCopy# Windows の場合
python -m venv venv
.\venv\Scripts\activate

# macOS/Linux の場合
python3 -m venv venv
source venv/bin/activate

必要なパッケージをインストールします：

bashCopypip install -r requirements.txt

OpenAI APIキーを環境変数として設定します：

bashCopy# Windows の場合（コマンドプロンプト）
set OPENAI_API_KEY=your_openai_api_key

# Windows の場合（PowerShell）
$env:OPENAI_API_KEY="your_openai_api_key"

# macOS/Linux の場合
export OPENAI_API_KEY="your_openai_api_key"
※ your_openai_api_key は、OpenAIから取得したAPIキーに置き換えてください。
※ この環境変数は、システムを再起動すると消えるため、永続的に設定する場合は環境変数の設定をシステムの設定から行うか、起動スクリプトに追加してください。
使用方法

設定ファイルの準備：

config.example.yml を config.yml にコピーします
config.yml を自分の環境に合わせて編集します


プログラムの実行：

bashCopypython run.py
トラブルシューティング
よくある問題と解決方法：

モジュールが見つからないエラー

仮想環境が有効化されているか確認してください
pip install -r requirements.txt を再実行してください


設定ファイルエラー

config.yml の形式が正しいか確認してください


OpenAI API関連のエラー

環境変数 OPENAI_API_KEY が正しく設定されているか確認してください
APIキーが有効であることを確認してください
API使用量の制限に達していないか確認してください



ライセンス
このプロジェクトは MITライセンス の下で公開されています。