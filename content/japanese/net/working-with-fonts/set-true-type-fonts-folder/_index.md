---
title: True Type フォント フォルダーの設定
linktitle: True Type フォント フォルダーの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに True Type フォント フォルダーを設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-true-type-fonts-folder/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに True Type フォント フォルダーを設定する手順を段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後では、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する True Type フォントを含むカスタム フォルダーを指定する方法がわかります。

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

## ステップ 3: True Type フォント フォルダーを設定する
のインスタンスを作成することで、レンダリング時に使用する True Type フォントのフォルダーを指定できるようになりました。`FontSettings`クラスとそれを使用する`SetFontsFolder()`フォントフォルダーを設定するメソッドです。 True Type フォントを含むカスタム フォルダーを指定できます。 2 番目のパラメータは、`SetFontsFolder()`指定したフォルダーのサブフォルダーも検索するかどうかを示します。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## ステップ 4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Aspose.Words for .NET を使用した True Type フォント フォルダーの設定のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//この設定は、デフォルトで検索されるデフォルトのフォント ソースをオーバーライドすることに注意してください。これで、これらのフォルダーのみが検索されるようになります
//フォントのレンダリングまたは埋め込み時のフォント。システム フォント ソースを維持しながら追加のフォント ソースを追加するには、FontSettings.GetFontSources と
//代わりに FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
//フォント設定を行う
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに True Type フォント フォルダーを設定する方法を学習しました。このステップバイステップ ガイドに従うことで、ドキュメントのレンダリング時に使用する True Type フォントを含むカスタム フォルダーを簡単に指定できます。 Aspose.Words は、ドキュメント内のフォントを使用したワード処理用の強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてドキュメントをレンダリングするときに使用するフォントを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words で TrueType フォント フォルダーを構成するにはどうすればよいですか?

 A: Aspose.Words で TrueType フォント フォルダーを構成するには、`SetTrueTypeFontsFolder`の方法`Fonts` TrueType フォントを含むフォルダーの場所を指定するクラス。

#### Q: どのような種類のフォントが TrueType フォントとみなされますか?

A: TrueType フォントは一般的なフォント形式です。これらは Word 文書でよく使用され、ファイル拡張子は .ttf または .ttc です。

#### Q: Aspose.Words で複数の TrueType フォント フォルダーを指定できますか?

A: はい、Aspose.Words で複数の TrueType フォント フォルダを指定できます。`SetTrueTypeFontsFolder`の方法`Fonts`フォルダーの場所のリストを含むクラス。

#### Q: Aspose.Words で構成されている TrueType フォント フォルダーを確認するにはどうすればよいですか?

 A: Aspose.Words で構成された TrueType フォント フォルダーを確認するには、`GetTrueTypeFontsFolder`の方法`Fonts`クラスを使用して、構成された TrueType フォント フォルダーの場所を取得します。

#### Q: Aspose.Words で TrueType フォント フォルダーを構成することが重要なのはなぜですか?

A: Aspose.Words で TrueType フォント フォルダーを設定することは、Aspose.Words が Word 文書を処理するときに必要なフォントを見つけるのに役立つため、重要です。これにより、異なるシステム間でも文書の書式設定と外観の一貫性が確保されます。