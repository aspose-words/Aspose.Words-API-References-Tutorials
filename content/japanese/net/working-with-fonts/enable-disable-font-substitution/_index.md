---
title: フォント置換を有効/無効にする
linktitle: フォント置換を有効/無効にする
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書でフォントの置換を有効または無効にする方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/enable-disable-font-substitution/
---
このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して Word 文書をレンダリングするときに、フォントの置換を有効または無効にする方法を説明します。フォントの置換を有効または無効にすることで、不足しているフォントを既定のフォントに自動的に置き換えるかどうかを制御できます。.NET プロジェクトでコードを理解して実装できるように、手順を追って説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- フォント置換の有無にかかわらずレンダリングする Word 文書

## ステップ1: ドキュメントディレクトリを定義する
まず、Word文書の場所にディレクトリパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`コード内に適切なパスを追加します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントをアップロードし、フォント設定を構成する
次に、レンダリングしたいWord文書を読み込み、`FontSettings`フォント設定を扱うクラスです。フォント名を指定してデフォルトのフォントオーバーライドを設定します。`DefaultFontName`フォント情報の上書きを無効にする`Enabled`に設定`false`.

```csharp
//ドキュメントを読み込む
Document doc = new Document(dataDir + "Rendering.docx");

//フォント設定を構成する
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

//フォント設定を文書に適用する
doc.FontSettings = fontSettings;
```

## ステップ3: レンダリングされたドキュメントを保存する
最後に、定義されたフォントオーバーライド設定を尊重したレンダリングされたドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Aspose.Words for .NET を使用してフォント置換を有効/無効にするサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## 結論
このチュートリアルでは、Aspose.Words for .NET で Word 文書をレンダリングするときに、フォントの置換を有効または無効にする方法を説明しました。フォントの置換を制御することで、レンダリングされた文書で見つからないフォントの処理方法に影響を与えることができます。この機能を使用して、Word 文書のフォントの管理をカスタマイズしてください。

### よくある質問

#### Q: Aspose.Words を使用して Word 文書でフォントの置換を有効にするにはどうすればよいでしょうか?

A: Aspose.Words を使用して Word 文書でフォントの置換を有効にするには、必要なフォントが利用できない場合に使用する代替フォントを指定する API を使用します。これにより、元のフォントがなくても一貫したテキストの視覚化が保証されます。

#### Q: Aspose.Words を使用して Word 文書内のフォント置換を無効にすることは可能ですか?

A: はい、Aspose.Words を使用すると、Word 文書内のフォントの置換を無効にすることができます。API を使用すると、Word が必要なフォントを他のフォントに置き換えるのを防ぐことができ、テキストの元の外観が維持されます。

#### Q: Word 文書で置換時に必要なフォントが見つからない場合はどうなりますか?

A: Word 文書で必要なフォントを置換するときに見つからない場合、Aspose.Words はこの問題を検出し、修正オプションを提供します。見つからないフォントを代替フォントで置き換えるか、見つからないフォントを文書に含めるかを選択して、正しく表示されるようにすることができます。

#### Q: Aspose.Words を使用して Word 文書でフォントを置換するときに、不足しているフォントをどのように処理すればよいですか?

A: Aspose.Words を使用して Word 文書でフォントを置換するときに不足しているフォントを処理するには、不足しているフォントを検出し、解決オプションを提供する API を使用します。必要に応じて、不足しているフォントを代替フォントで置き換えるか、不足しているフォントを文書に含めるかを選択できます。

#### Q: Word 文書でフォントの置換を制御することは重要ですか?

A: はい、テキストの視覚的な整合性を維持するために、Word 文書のフォントの置換を制御することが重要です。Aspose.Words を使用してフォントの置換を有効または無効にすることで、必要なフォントが確実に使用され、フォントの欠落や置換による問題を回避できます。