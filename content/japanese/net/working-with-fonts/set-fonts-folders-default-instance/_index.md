---
title: フォントフォルダのデフォルトインスタンスを設定する
linktitle: フォントフォルダのデフォルトインスタンスを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに既定のフォント フォルダーを設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-default-instance/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、既定のフォント フォルダーを設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する既定のフォント フォルダーを設定する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: デフォルトのフォントフォルダを設定する
次に、デフォルトのフォントフォルダを設定します。`FontSettings.DefaultInstance`クラスと`SetFontsFolder()`方法。デフォルト フォルダーとして使用するフォント フォルダーへのパスを指定します。

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## ステップ3: レンダリングするドキュメントを読み込む
これで、レンダリングするドキュメントをロードできます。`Document`クラス。正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Aspose.Words for .NET を使用してフォント フォルダーの既定のインスタンスを設定するサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、既定のフォント フォルダーを設定する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、ドキュメントをレンダリングするときに既定のフォルダーとして使用するフォントのフォルダーを簡単に指定できます。Aspose.Words は、ドキュメント内のフォントを使用して Words を処理するための強力で柔軟な API を提供します。この知識があれば、ドキュメントを特定のニーズに合わせてレンダリングするときに使用するフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words でデフォルトのフォント フォルダーを設定するにはどうすればよいですか?

 A: Aspose.Wordsでデフォルトのフォントフォルダを設定するには、`Fonts`クラスと`SetFontsFolders`カスタムフォントフォルダの場所を指定する方法。

#### Q: 既定のフォント フォルダーを設定すると、Aspose.Words で処理されるすべての Word 文書に影響しますか?

A: はい、既定のフォント フォルダーを設定すると、Aspose.Words で処理されるすべての Word ドキュメントに影響します。既定のフォント フォルダーを設定すると、Aspose.Words はこれらの場所を使用してすべてのドキュメント内のフォントを検索します。

#### Q: Aspose.Words で複数のデフォルト フォント フォルダーを設定できますか?

 A: はい、Aspose.Wordsでは複数のデフォルトフォントフォルダを設定できます。`SetFontsFolders`方法の`Fonts`クラス。

#### Q: Aspose.Words に現在設定されているデフォルトのフォント フォルダーを確認するにはどうすればよいですか?

 A: Aspose.Wordsで現在定義されているデフォルトのフォントフォルダーを確認するには、`GetFolders`方法の`Fonts`構成されたフォント フォルダーの場所を取得するクラス。

#### Q: デフォルトのフォント フォルダーを設定すると、Word 文書でカスタム フォントを使用できるようになりますか?

A: はい、デフォルトのフォント フォルダーを設定することで、Word 文書でカスタム フォントを使用できます。指定したフォルダーにフォントを配置するだけで、Aspose.Words はドキュメントの生成や操作時にそのフォントを使用します。