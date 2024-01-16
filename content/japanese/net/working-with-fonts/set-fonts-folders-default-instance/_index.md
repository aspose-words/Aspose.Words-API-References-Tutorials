---
title: フォントフォルダーのデフォルトインスタンスの設定
linktitle: フォントフォルダーのデフォルトインスタンスの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときにデフォルトのフォント フォルダーを設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-default-instance/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにデフォルトのフォント フォルダーを設定するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後では、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用するデフォルトのフォント フォルダーを設定する方法がわかります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: デフォルトのフォントフォルダーを設定する
次に、を使用してデフォルトのフォントフォルダーを設定できます。`FontSettings.DefaultInstance`クラスと`SetFontsFolder()`方法。デフォルトのフォルダーとして使用するフォント フォルダーへのパスを指定します。

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## ステップ 3: レンダリングするドキュメントをロードする
これで、ドキュメントをロードしてレンダリングできるようになります。`Document`クラス。必ず正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Aspose.Words for .NET を使用した Set Fonts Folders Default Instance のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにデフォルトのフォント フォルダーを設定する方法を学習しました。このステップバイステップのガイドに従うことで、ドキュメントをレンダリングするときにデフォルトのフォルダーとして使用するフォントのフォルダーを簡単に指定できます。 Aspose.Words は、ドキュメント内のフォントを使用したワード処理用の強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてドキュメントをレンダリングするときに使用されるフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words でデフォルトのフォント フォルダーを設定するにはどうすればよいですか?

 A: Aspose.Words でデフォルトのフォント フォルダーを設定するには、`Fonts`クラスと`SetFontsFolders`カスタム フォント フォルダーの場所を指定するメソッド。

#### Q: デフォルトのフォント フォルダーの設定は、Aspose.Words で処理されるすべての Word 文書に影響しますか?

A: はい、デフォルトのフォント フォルダーの設定は、Aspose.Words で処理されるすべての Word 文書に影響します。デフォルトのフォント フォルダーを設定すると、Aspose.Words はこれらの場所を使用してすべてのドキュメント内のフォントを検索します。

#### Q: Aspose.Words で複数のデフォルトのフォント フォルダーを設定できますか?

 A: はい、Aspose.Words で複数のデフォルト フォント フォルダーを設定できます。必要なのは、カスタム フォント フォルダーの場所を指定することだけです。`SetFontsFolders`の方法`Fonts`クラス。

#### Q: Aspose.Words に現在設定されているデフォルトのフォント フォルダーを確認するにはどうすればよいですか?

 A: Aspose.Words で現在定義されているデフォルトのフォント フォルダーを確認するには、`GetFolders`の方法`Fonts`クラスを使用して、構成されたフォントフォルダーの場所を取得します。

#### Q: デフォルトのフォント フォルダーを設定すると、Word 文書でカスタム フォントを使用できるようになりますか?

A: はい、デフォルトのフォント フォルダーを設定すると、Word 文書でカスタム フォントを使用できます。指定したフォルダーにフォントを配置するだけで、Aspose.Words はドキュメントの生成または操作時にフォントを使用します。