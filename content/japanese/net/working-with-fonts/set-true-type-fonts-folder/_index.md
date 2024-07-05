---
title: TrueTypeフォントフォルダを設定する
linktitle: TrueTypeフォントフォルダを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに True Type フォント フォルダーを設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-true-type-fonts-folder/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに True Type フォント フォルダーを設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する True Type フォントを含むカスタム フォルダーを指定する方法がわかります。

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

## ステップ3: True Typeフォントフォルダを設定する
レンダリング時に使用するTrueTypeフォントのフォルダを指定するには、`FontSettings`クラスと使用`SetFontsFolder()`メソッドを使用してフォントフォルダを設定します。TrueTypeフォントを含むカスタムフォルダを指定できます。`SetFontsFolder()`指定したフォルダーのサブフォルダーも検索するかどうかを示します。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## ステップ4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Aspose.Words for .NET を使用して True Type フォント フォルダーを設定するためのサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//この設定は、デフォルトで検索されるデフォルトのフォントソースを上書きすることに注意してください。これで、これらのフォルダのみが検索されます。
//フォントをレンダリングまたは埋め込むときのフォント。システムフォントソースを維持しながら追加のフォントソースを追加するには、FontSettings.GetFontSourcesと
//代わりにFontSettings.SetFontSourcesを使用してください
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
//フォント設定を行う
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに True Type フォント フォルダーを設定する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、ドキュメントをレンダリングするときに使用する True Type フォントを含むカスタム フォルダーを簡単に指定できます。Aspose.Words は、ドキュメント内のフォントを使用して Words を処理するための強力で柔軟な API を提供します。この知識があれば、ドキュメントをレンダリングするときに使用するフォントを制御およびカスタマイズして、特定のニーズに対応できます。

### よくある質問

#### Q: Aspose.Words で TrueType フォント フォルダーを構成するにはどうすればよいですか?

 A: Aspose.WordsでTrueTypeフォントフォルダーを構成するには、`SetTrueTypeFontsFolder`方法の`Fonts` TrueType フォントを含むフォルダーの場所を指定するクラス。

#### Q: TrueType フォントと見なされるフォントの種類は何ですか?

A: TrueType フォントは一般的なフォント形式です。Word 文書でよく使用され、ファイル拡張子は .ttf または .ttc です。

#### Q: Aspose.Words で複数の TrueType フォント フォルダーを指定できますか?

A: はい、Aspose.Wordsでは複数のTrueTypeフォントフォルダを指定することができます。`SetTrueTypeFontsFolder`方法の`Fonts`フォルダーの場所のリストを持つクラス。

#### Q: Aspose.Words で設定されている TrueType フォント フォルダーを確認するにはどうすればよいですか?

 A: Aspose.Wordsで構成されたTrueTypeフォントフォルダーを確認するには、`GetTrueTypeFontsFolder`方法の`Fonts`構成された TrueType フォント フォルダーの場所を取得するクラス。

#### Q: Aspose.Words で TrueType フォント フォルダーを構成することが重要なのはなぜですか?

A: Aspose.Words で TrueType フォント フォルダーを設定することは重要です。これは、Aspose.Words が Word 文書を処理するときに必要なフォントを見つけるのに役立つためです。これにより、異なるシステム間でも文書の書式設定と外観の一貫性が確保されます。