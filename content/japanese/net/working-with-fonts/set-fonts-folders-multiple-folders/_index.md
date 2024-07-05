---
title: フォントフォルダの設定 複数のフォルダ
linktitle: フォントフォルダの設定 複数のフォルダ
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに複数のフォント フォルダーを設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに複数のフォント フォルダーを設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する複数のフォント フォルダーを指定する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: レンダリングするドキュメントを読み込む
次に、レンダリングするドキュメントをロードします。`Document`クラス。正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ3: フォントフォルダを設定する
複数のフォントフォルダを設定できるようになりました。`FontSettings`クラスと`SetFontsFolders()`方法。使用するフォントフォルダへのパスを配列で指定できます。この例では、2つのフォントフォルダを指定しています: "C:\MyFonts\" および "D:\Misc\Fonts\「」。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## ステップ4: フォント設定を適用する
次に、フォント設定を文書に適用する必要があります。`FontSettings`の財産`Document`クラス。

```csharp
doc.FontSettings = fontSettings;
```

## ステップ5: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Aspose.Words for .NET を使用して複数のフォルダーにフォント フォルダーを設定するサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//この設定は、デフォルトで検索されるデフォルトのフォントソースを上書きすることに注意してください。これで、これらのフォルダのみが検索されます。
//フォントをレンダリングまたは埋め込むときにフォントを使用します。システムフォントソースを保持したまま追加のフォントソースを追加するには、FontSettings.GetFontSourcesと
//代わりに FontSettings.SetFontSources を使用してください。
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに複数のフォント フォルダーを設定する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、ドキュメントをレンダリングするときに使用する複数のフォント フォルダーを簡単に指定できます。Aspose.Words は、ドキュメント内のフォントを使用して Words を処理するための強力で柔軟な API を提供します。この知識があれば、ドキュメントを特定のニーズに合わせてレンダリングするときに使用するフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words で複数のフォント フォルダーを設定するにはどうすればよいですか?

 A: Aspose.Wordsで複数のフォントフォルダを設定するには、`SetFontsFolders`方法の`Fonts`カスタム フォント フォルダーの場所のリストを提供するクラス。

#### Q: 複数のフォント フォルダーを設定すると、Aspose.Words で処理されるすべてのドキュメントに影響しますか?

A: はい、複数のフォント フォルダーを設定すると、Aspose.Words で処理されるすべてのドキュメントに影響します。フォント フォルダーを定義すると、Aspose.Words はこれらの場所を使用してすべてのドキュメント内のフォントを検索します。

#### Q: Aspose.Words で定義できるフォント フォルダーの数はいくつですか?

A: Aspose.Words では、必要な数のフォント フォルダーを定義できます。定義できるフォント フォルダーの数に特に制限はありません。

#### Q: Aspose.Words で定義されているフォント フォルダーを確認するにはどうすればよいですか?

 A: Aspose.Wordsで定義されているフォントフォルダーを確認するには、`GetFolders`方法の`Fonts`構成されたフォント フォルダーの場所を取得するクラス。

#### Q: フォント フォルダーには特定のフォントが含まれている必要がありますか?

A: はい、フォント フォルダーには Word 文書で使用するフォントが含まれている必要があります。Aspose.Words は、文書を処理するときに指定されたフォルダー内のフォントを検索します。