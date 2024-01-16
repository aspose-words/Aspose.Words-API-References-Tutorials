---
title: レンダリング時にデフォルトのフォントを指定する
linktitle: レンダリング時にデフォルトのフォントを指定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときにデフォルトのフォントを指定するためのステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/specify-default-font-when-rendering/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにデフォルトのフォントを指定するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルを終えると、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用するデフォルト フォントを指定する方法がわかるようになります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: レンダリングするドキュメントをロードする
次に、レンダリングするドキュメントをロードする必要があります。`Document`クラス。必ず正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 3: デフォルトのフォントを設定する
のインスタンスを作成することで、レンダリング時に使用するデフォルトのフォントを指定できるようになりました。`FontSettings`クラスと設定`DefaultFontName`の財産`DefaultFontSubstitution`に反対する`DefaultFontSubstitution`物体`SubstitutionSettings`の`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## ステップ 4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Aspose.Words for .NET を使用したレンダリング時のデフォルト フォントの指定のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//ここで定義されたデフォルトのフォントがレンダリング中に見つからない場合は、
//マシン上で最も近いフォントが代わりに使用されます。
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにデフォルトのフォントを指定する方法を学習しました。このステップバイステップのガイドに従うことで、ドキュメントのレンダリング時に使用するデフォルトのフォントを簡単に設定できます。 Aspose.Words は、ドキュメント内のフォントを使用したワード処理用の強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてドキュメントのレンダリングを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words で PDF に変換するときにデフォルトのフォントを指定するにはどうすればよいですか?

 A: Aspose.Words で PDF に変換するときにデフォルトのフォントを指定するには、`PdfOptions`クラスを設定して、`DefaultFontName`プロパティを目的のフォントの名前に置き換えます。

#### Q: PDF に変換するときにデフォルトのフォントが使用できない場合はどうすればよいですか?

A: PDF への変換時に指定されたデフォルト フォントが使用できない場合、Aspose.Words は置換フォントを使用して、変換されたドキュメント内のテキストを表示します。これにより、元のフォントと多少見た目が異なる場合があります。

#### Q: DOCX や HTML などの他の出力形式のデフォルト フォントを指定できますか?

A: はい、適切な変換オプションを使用し、各形式に対応するプロパティを設定することで、DOCX や HTML などの他の出力形式のデフォルト フォントを指定できます。

#### Q: Aspose.Words で指定されているデフォルトのフォントを確認するにはどうすればよいですか?

 A: Aspose.Words で指定されているデフォルトのフォントを確認するには、`DefaultFontName`の財産`PdfOptions`クラスを取得し、設定されているフォントの名前を取得します。

#### Q: ドキュメントのセクションごとに異なるデフォルト フォントを指定することはできますか?

A: はい、各セクションに固有の書式設定オプションを使用して、ドキュメントのセクションごとに異なるデフォルト フォントを指定できます。ただし、これには、Aspose.Words 機能を使用したドキュメントのより高度な操作が必要になります。