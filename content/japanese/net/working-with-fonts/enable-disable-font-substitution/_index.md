---
title: 有効 無効 フォント置換
linktitle: 有効 無効 フォント置換
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のフォント置換を有効または無効にする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/enable-disable-font-substitution/
---
このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して Word 文書をレンダリングするときに、その文書内のフォント置換を有効または無効にする方法について説明します。フォント置換を有効または無効にすると、不足しているフォントをデフォルトのフォントに自動的に置き換えるかどうかを制御できます。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- フォントの置換を使用して、または置換せずにレンダリングする Word 文書

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードし、フォント設定を構成する
次に、レンダリングしたい Word 文書をロードし、`FontSettings`フォント設定を処理するクラス。でフォント名を指定して、デフォルトのフォント オーバーライドを設定します。`DefaultFontName`そしてフォント情報の上書きを無効にします`Enabled`に設定`false`.

```csharp
//ドキュメントをロードする
Document doc = new Document(dataDir + "Rendering.docx");

//フォント設定を構成する
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

//フォント設定をドキュメントに適用する
doc.FontSettings = fontSettings;
```

## ステップ 3: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントを保存します。これにより、定義されたフォント オーバーライド設定が尊重されます。

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Aspose.Words for .NET を使用したフォント置換の無効化の有効化のサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書をレンダリングするときに、その文書内のフォント置換を有効または無効にする方法について説明しました。フォントの置換を制御することで、レンダリングされたドキュメント内で欠落しているフォントがどのように処理されるかに影響を与えることができます。 Word 文書内のフォントの管理をカスタマイズするには、この機能を遠慮なく使用してください。

### よくある質問

#### Q: Aspose.Words を使用して Word 文書内のフォント置換を有効にするにはどうすればよいですか?

A: Aspose.Words を使用して Word 文書内のフォント置換を有効にするには、API を使用して、必要なフォントが利用できない場合に使用する代替フォントを指定できます。これにより、元のフォントがなくても、一貫したテキストの視覚化が保証されます。

#### Q: Aspose.Words を使用して Word 文書内のフォント置換を無効にすることはできますか?

A: はい、Aspose.Words を使用すると、Word 文書内のフォント置換を無効にすることができます。 API を使用すると、Word が必要なフォントを他のフォントに置き換えることを防ぐことができ、テキストの元の外観が維持されます。

#### Q: Word 文書での置換中に必要なフォントが見つからない場合はどうなりますか?

A: Word 文書での置換中に必要なフォントが見つからない場合、Aspose.Words はこの問題を検出し、修正するためのオプションを提供します。不足しているフォントを代替フォントで置き換えたり、ドキュメントに不足しているフォントを含めたりして、正しく表示できるようにすることができます。

#### Q: Word 文書内で Aspose.Words を使用してフォントを置き換えるときに、見つからないフォントを処理するにはどうすればよいですか?

A: Word 文書内で Aspose.Words を使用して置換するときに欠落しているフォントを処理するには、API を使用して欠落しているフォントを検出し、解像度オプションを提供します。ニーズに応じて、不足しているフォントを代替フォントで置き換えたり、ドキュメントに不足しているフォントを含めたりすることを選択できます。

#### Q: Word 文書内のフォント置換を制御することは重要ですか?

A: はい、テキストの視覚的な整合性を維持するには、Word 文書内のフォント置換を制御することが重要です。 Aspose.Words を使用してフォントの置換を有効または無効にすると、必要なフォントが確実に使用され、フォントの欠落または置換による問題を回避できます。