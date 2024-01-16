---
title: 圧縮レベルの設定
linktitle: 圧縮レベルの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを保存するときに圧縮レベルを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存する際の圧縮レベルを設定するために、提供されている C# ソース コードを調べます。この機能を使用すると、生成されるドキュメントの圧縮レベルを制御できます。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用して開発環境がセットアップされていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ 2: ドキュメントをロードする

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

このステップでは、`Document`メソッドを実行し、ロードする DOCX ファイルへのパスを渡します。

## ステップ 3: OOXML バックアップ オプションの構成

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

このステップでは、OOXML 保存オプションを使用して設定します。`OoxmlSaveOptions`クラス。圧縮レベルを次のように設定します。`SuperFast`より高速な圧縮を実現します。

## ステップ 4: 指定した圧縮レベルでドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを渡します。`.docx`拡張子と、指定された保存オプションを追加します。

これで、ソース コードを実行して、ドキュメントを保存するときに圧縮レベルを設定できるようになりました。結果のファイルは、「WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx」という名前で指定されたディレクトリに保存されます。

### Aspose.Words for .NET を使用した圧縮レベルの設定のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに圧縮レベルを設定する機能を検討しました。適切な圧縮レベルを指定することで、ドキュメントのサイズと生成速度を最適化できます。

の`OoxmlSaveOptions`このクラスは、`CompressionLevel`プロパティを適切な値に変更します。`SuperFast`。これにより、特定のニーズに基づいてファイル サイズとバックアップ速度の適切なバランスを取ることができます。

圧縮を使用すると、生成されるファイルのサイズを削減する必要がある場合、特に大きなドキュメントの場合に有益です。これにより、ドキュメントの保存、共有、送信が容易になります。

Aspose.Words for .NET は、ドキュメント操作のための強力なオプションと機能を幅広く提供します。適切なバックアップ オプションを使用すると、ドキュメント生成プロセスをカスタマイズし、アプリケーションのパフォーマンスを最適化できます。

Aspose.Words for .NET のその他の機能を自由に探索して、ドキュメント生成ワークフローを強化してください。
