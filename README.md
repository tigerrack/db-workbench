# DB Workbench

PostgreSQL / MySQL 用のデスクトップDBクライアントです（Windows x64、macOS Apple Silicon / Intel）。
このリポジトリは配布専用で、Releases にインストーラーとアプリを公開しています。

> リリース候補（rc）の段階です。コード署名・公証済みの正式版ではありません。

## ダウンロード

[Releases](https://github.com/tigerrack/db-workbench/releases) の最新版から、使うPCに合うファイルを選びます。

| 対象 | おすすめ | ほかの形式 |
|---|---|---|
| Windows x64 | `db-workbench-windows-x64-setup.exe` | `db-workbench-windows-x64.zip` |
| macOS Apple Silicon（M1以降） | `db-workbench-macos-arm64.dmg` | `db-workbench-macos-arm64.zip` |
| macOS Intel | `db-workbench-macos-x64.dmg` | `db-workbench-macos-x64.zip` |

各ファイルには `.sha256` が付いています。使う前に照合してください。

- Windows: `Get-FileHash <ファイル> -Algorithm SHA256`
- macOS: `shasum -a 256 <ファイル>`

## インストール

### Windows

1. `db-workbench-windows-x64-setup.exe` を実行します。管理者権限は不要で、このユーザーにだけインストールします。
2. 署名がないため「WindowsによってPCが保護されました」と表示された場合は、配布元とSHA256を確認したうえで「詳細情報」→「実行」を選びます。
3. スタートメニューの「DB Workbench」から起動します。アンインストールは「設定 → アプリ」から行えます。

### macOS

1. DMGを開き、「DB Workbench」を「Applications」へドラッグします。
2. Apple Developer ID の署名・公証がないため、初回は「検証できません」と表示されます。「完了」で閉じ、「システム設定 → プライバシーとセキュリティ」の「このまま開く」で許可します。
3. アンインストールは「Applications」の「DB Workbench」をゴミ箱へ入れます。

## 更新

アプリは起動時に1日1回このリポジトリのRelease一覧を確認し、新しい版があれば画面右下に知らせます（「使い方」で確認をオフにできます）。
自動ではダウンロード・インストールしません。新しい版のインストーラーまたはDMGで上書きしてください。

- 確認で送るのは、このリポジトリのRelease一覧への問い合わせだけです。接続設定やDBの情報は送りません。
- 接続設定はアプリとは別の場所に保存され、更新・アンインストールでは消えません。
  - Windows: `%APPDATA%\DB Workbench`
  - macOS: `~/Library/Application Support/DB Workbench`
- 保存したパスワードは、OSの保護機構（Windows DPAPI / macOS キーチェーン）で暗号化します。

## 旧名 TigerDB Workbench からの移行

初回起動時に、旧TigerDB Workbenchの接続設定とワークスペース設定を自動で引き継ぎます（旧フォルダーは残ります）。
macOSでは保存済みパスワードを読めないため、接続時に入力し直してください。

## 問い合わせ・ライセンス

使い方と制限の詳細は、ダウンロードしたファイルに同梱の `START-HERE.md` を参照してください。
ライセンスは同梱の `LICENSE` を参照してください。
