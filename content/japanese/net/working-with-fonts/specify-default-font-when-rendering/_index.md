---
title: レンダリング時にデフォルトのフォントを指定する
linktitle: レンダリング時にデフォルトのフォントを指定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに既定のフォントを指定する手順ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/specify-default-font-when-rendering/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに既定のフォントを指定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する既定のフォントを指定する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: レンダリングするドキュメントを読み込む
次に、レンダリングするドキュメントをロードする必要があります。`Document`クラス。正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ3: デフォルトのフォントを設定する
レンダリング時に使用するデフォルトのフォントを指定するには、`FontSettings`クラスと設定`DefaultFontName`の財産`DefaultFontSubstitution`に反対する`DefaultFontSubstitution`物体`SubstitutionSettings`の`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## ステップ4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Aspose.Words for .NET を使用してレンダリング時に既定のフォントを指定するサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//ここで定義されたデフォルトのフォントがレンダリング中に見つからない場合は、
//代わりに、マシン上で最も近いフォントが使用されます。
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに既定のフォントを指定する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、ドキュメントをレンダリングするときに使用する既定のフォントを簡単に設定できます。Aspose.Words は、ドキュメント内のフォントを使用した Words Processing 用の強力で柔軟な API を提供します。この知識があれば、ドキュメントのレンダリングを特定のニーズに合わせて制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words で PDF に変換するときにデフォルトのフォントを指定するにはどうすればよいですか?

 A: Aspose.WordsでPDFに変換するときにデフォルトのフォントを指定するには、`PdfOptions`クラスを設定し、`DefaultFontName`プロパティを目的のフォントの名前に変更します。

#### Q: PDF に変換するときにデフォルトのフォントが使用できない場合はどうなりますか?

A: PDF に変換するときに指定された既定のフォントが使用できない場合、Aspose.Words は変換されたドキュメント内のテキストを表示するために代替フォントを使用します。これにより、元のフォントとは外観が若干異なる場合があります。

#### Q: DOCX や HTML などの他の出力形式のデフォルトのフォントを指定できますか?

A: はい、適切な変換オプションを使用し、各形式に対応するプロパティを設定することで、DOCX や HTML などの他の出力形式のデフォルト フォントを指定できます。

#### Q: Aspose.Words で指定されているデフォルトのフォントを確認するにはどうすればよいですか?

 A: Aspose.Wordsで指定されているデフォルトのフォントを確認するには、`DefaultFontName`の財産`PdfOptions`クラスを作成し、設定されたフォントの名前を取得します。

#### Q: ドキュメントの各セクションに異なるデフォルトフォントを指定することは可能ですか?

A: はい、各セクションに固有の書式設定オプションを使用して、ドキュメントの各セクションに異なる既定のフォントを指定することができます。ただし、これには Aspose.Words 機能を使用したドキュメントのより高度な操作が必要になります。