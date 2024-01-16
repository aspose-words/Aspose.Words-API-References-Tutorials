---
title: 暗号化された Word 文書を検証する
linktitle: 暗号化された Word 文書を検証する
second_title: Aspose.Words ドキュメント処理 API
description: Word ドキュメントが Aspose.Words for .NET で暗号化されていることを確認するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-fileformat/verify-encrypted-document/
---

この記事では、Aspose.Words for .NET で暗号化された Word ドキュメント検証機能を使用する方法について段階的なガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルを終えると、ドキュメントが暗号化されているかどうかを確認する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ファイル形式を検出する

次に、`DetectFileFormat`の方法`FileFormatUtil`ファイル形式情報を検出するクラス。この例では、暗号化されたドキュメントが「Encrypted.docx」という名前で、指定されたドキュメント ディレクトリに存在すると仮定します。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## ステップ 3: ドキュメントが暗号化されているかどうかを確認する

私たちが使用するのは、`IsEncrypted`の財産`FileFormatInfo`オブジェクトを使用して、ドキュメントが暗号化されているかどうかを確認します。このプロパティは返します`true`ドキュメントが暗号化されている場合は、それ以外の場合は返されます。`false`。結果をコンソールに表示します。

```csharp
Console.WriteLine(info.IsEncrypted);
```

それだけです ！ Aspose.Words for .NET を使用してドキュメントが暗号化されているかどうかを正常に確認できました。

### Aspose.Words for .NET を使用して暗号化されたドキュメントを検証するためのソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## よくある質問

### Q: 暗号化された Word 文書を検証する手順は何ですか?

暗号化された Word 文書を検証する手順は次のとおりです。

ドキュメントディレクトリを定義します。

ファイル形式を検出します。

文書が暗号化されているかどうかを確認します。

### Q: ドキュメント ディレクトリを設定するにはどうすればよいですか?
ドキュメントディレクトリを設定するには、以下を置き換える必要があります`"YOUR DOCUMENT DIRECTORY"`次のコード内のドキュメント ディレクトリの実際のパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Q: ファイル形式を検出するにはどうすればよいですか?
使用できます`DetectFileFormat`の方法`FileFormatUtil`ファイル形式情報を検出するクラス。次の例では、暗号化されたドキュメントが「Encrypted.docx」という名前で、指定されたドキュメント ディレクトリに配置されていると想定しています。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Q: ドキュメントが暗号化されているかどうかを確認するにはどうすればよいですか?
使用できます`IsEncrypted`の財産`FileFormatInfo`オブジェクトを使用して、ドキュメントが暗号化されているかどうかを確認します。このプロパティは返します`true`ドキュメントが暗号化されている場合は、それ以外の場合は返されます。`false`。結果がコンソールに表示されます。

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Q: Aspose.Words for .NET を使用してドキュメントが暗号化されているかどうかを確認するにはどうすればよいですか?
このチュートリアルで説明されている手順に従い、提供されたソース コードを実行すると、Aspose.Words for .NET を使用してドキュメントが暗号化されているかどうかを確認できます。
