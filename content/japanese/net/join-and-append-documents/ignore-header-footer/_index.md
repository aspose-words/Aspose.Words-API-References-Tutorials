---
title: ヘッダーフッターを無視
linktitle: ヘッダーフッターを無視
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ヘッダーとフッターのコンテンツを無視しながらドキュメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/join-and-append-documents/ignore-header-footer/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ヘッダーとフッターの内容を無視してドキュメントを追加する方法について説明します。提供されているソース コードは、追加プロセス中にヘッダーとフッターを除外するようにインポート形式オプションを設定する方法を示しています。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NETライブラリがインストールされています。ダウンロードはこちらから[Aspose.Releases]https://releases.aspose.com/words/net/ にアクセスするか、NuGet パッケージ マネージャーを使用してインストールします。
- ソース ドキュメントと宛先ドキュメントが配置されているドキュメント ディレクトリ パス。

## ステップ2: ソースドキュメントと宛先ドキュメントを開く

ソース文書と宛先文書を`Document`クラスコンストラクタ。置換`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## ステップ3: インポート形式オプションを設定する

インスタンスを作成する`ImportFormatOptions`クラスを設定し、`IgnoreHeaderFooter`財産に`false`これにより、追加プロセス中にヘッダーとフッターのコンテンツが確実に含まれるようになります。

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## ステップ4: ソース文書を宛先文書に追加する

使用`AppendDocument`宛先ドキュメントのメソッドを使用してソースドキュメントを追加します。`ImportFormatMode.KeepSourceFormatting` 番目のパラメータとして を指定し、3 番目のパラメータとしてインポート形式オプションを指定します。

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## ステップ5: 宛先ドキュメントを保存する

最後に、変更した宛先ドキュメントを`Save`方法の`Document`物体。

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

これで、Aspose.Words for .NET を使用して、ヘッダーとフッターのコンテンツを無視しながらドキュメントを追加する実装が完了します。

### Aspose.Words for .NET を使用したヘッダー フッターを無視するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```