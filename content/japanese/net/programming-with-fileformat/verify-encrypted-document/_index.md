---
title: 暗号化されたWord文書を検証する
linktitle: 暗号化されたWord文書を検証する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書が暗号化されているかどうかを確認する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-fileformat/verify-encrypted-document/
---

この記事では、Aspose.Words for .NET で暗号化された Word ドキュメント検証機能を使用する方法について、ステップ バイ ステップ ガイドを提供します。コードの各部分を詳しく説明します。このチュートリアルの最後には、ドキュメントが暗号化されているかどうかを確認する方法が理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ファイル形式を検出する

次に、`DetectFileFormat`方法の`FileFormatUtil`クラスを使用してファイル形式情報を検出します。この例では、暗号化されたドキュメントの名前が「Encrypted.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## ステップ3: 文書が暗号化されているかどうかを確認する

私たちは`IsEncrypted`の財産`FileFormatInfo`文書が暗号化されているかどうかを確認するオブジェクト。このプロパティは`true`文書が暗号化されている場合は、そうでない場合は`false`コンソールに結果を表示します。

```csharp
Console.WriteLine(info.IsEncrypted);
```

以上です。Aspose.Words for .NET を使用してドキュメントが暗号化されているかどうかを正常に確認できました。

### Aspose.Words for .NET を使用して暗号化されたドキュメントを検証するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## よくある質問

### Q: 暗号化された Word 文書を検証する手順は何ですか?

暗号化された Word 文書を検証する手順は次のとおりです。

ドキュメントディレクトリを定義します。

ファイル形式を検出します。

ドキュメントが暗号化されているかどうかを確認します。

### Q: ドキュメントディレクトリを設定するにはどうすればよいですか?
ドキュメントディレクトリを設定するには、`"YOUR DOCUMENT DIRECTORY"`次のコードに、ドキュメント ディレクトリの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Q: ファイル形式を検出するにはどうすればいいですか?
あなたは`DetectFileFormat`方法の`FileFormatUtil`クラスを使用してファイル形式情報を検出します。次の例では、暗号化されたドキュメントの名前が「Encrypted.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Q: 文書が暗号化されているかどうかを確認するにはどうすればよいですか?
あなたは`IsEncrypted`の財産`FileFormatInfo`文書が暗号化されているかどうかを確認するオブジェクト。このプロパティは`true`文書が暗号化されている場合は、そうでない場合は`false`結果はコンソールに表示されます:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Q: Aspose.Words for .NET を使用してドキュメントが暗号化されているかどうかを確認するにはどうすればよいですか?
このチュートリアルに記載されている手順に従い、提供されているソース コードを実行すると、Aspose.Words for .NET を使用してドキュメントが暗号化されているかどうかを確認できます。
