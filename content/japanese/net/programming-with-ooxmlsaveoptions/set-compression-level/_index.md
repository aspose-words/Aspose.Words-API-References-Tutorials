---
title: 圧縮レベルの設定
linktitle: 圧縮レベルの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを保存するときに圧縮レベルを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに圧縮レベルを設定するために提供されている C# ソース コードについて説明します。この機能を使用すると、生成されたドキュメントの圧縮レベルを制御できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: ドキュメントの読み込み

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

このステップでは、`Document`メソッドを呼び出して、読み込む DOCX ファイルへのパスを渡します。

## ステップ3: OOXMLバックアップオプションの設定

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

このステップでは、OOXML保存オプションを設定します。`OoxmlSaveOptions`クラス。圧縮レベルを`SuperFast`より高速な圧縮を実現します。

## ステップ4: 指定した圧縮レベルでドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを`.docx`拡張子と指定された保存オプションを指定します。

これで、ソース コードを実行して、ドキュメントを保存するときに圧縮レベルを設定できます。結果のファイルは、指定されたディレクトリに「WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx」という名前で保存されます。

### Aspose.Words for .NET を使用して圧縮レベルを設定するサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに圧縮レベルを設定する機能について説明しました。適切な圧縮レベルを指定することで、ドキュメントのサイズと生成速度を最適化できます。

の`OoxmlSaveOptions`クラスは、設定によって圧縮レベルを柔軟に制御できます。`CompressionLevel`プロパティを適切な値に設定します。`SuperFast`これにより、特定のニーズに基づいて、ファイル サイズとバックアップ速度の適切なバランスを実現できます。

圧縮を使用すると、特に大きなドキュメントの場合、生成されるファイルのサイズを縮小する必要がある場合に役立ちます。これにより、ドキュメントの保存、共有、および転送が容易になります。

Aspose.Words for .NET は、ドキュメント操作のための強力なオプションと機能を幅広く提供します。適切なバックアップ オプションを使用することで、ドキュメント生成プロセスをカスタマイズし、アプリケーションのパフォーマンスを最適化できます。

ドキュメント生成ワークフローを強化するために、Aspose.Words for .NET のその他の機能を自由に探索してください。
