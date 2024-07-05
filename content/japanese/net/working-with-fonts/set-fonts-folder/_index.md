---
title: フォントフォルダの設定
linktitle: フォントフォルダの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でフォント ディレクトリを設定し、ドキュメントで使用されるフォントが使用可能であることを確認する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folder/
---
このチュートリアルでは、Aspose.Words for .NET でフォント ディレクトリを設定する方法を説明します。Word 文書で使用されるフォントを含むディレクトリを指定する方法を学習します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ1: ドキュメントディレクトリを定義する
まず、Word文書の場所にディレクトリパスを設定します。`"YOUR DOCUMENT DIRECTORY"`コード内に適切なパスを追加します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: フォントディレクトリを設定する
インスタンスを作成する`FontSettings`クラスと使用`SetFontsFolder`フォントを含むディレクトリを指定する方法。`"Fonts"`実際のフォント ディレクトリの名前を使用します。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## ステップ3: フォント設定でドキュメントを読み込む
使用`LoadOptions`フォント設定を指定するクラス`FontSettings`オプションを選択します。`Document`これらのオプションを使用してドキュメントをロードするクラス。

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Aspose.Words for .NET を使用してフォント フォルダーを設定するサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 結論
おめでとうございます。これで、Aspose.Words for .NET でフォント ディレクトリを設定する方法がわかりました。この機能を使用すると、ドキュメントで使用されるフォントの可用性を確保し、フォントの表示の一貫性を確保できます。

### よくある質問

#### Q: Aspose.Words でカスタム フォント フォルダーを設定するにはどうすればよいですか?

 A: Aspose.Wordsでカスタムフォントフォルダーを設定するには、`FontsFolder`クラスと`SetFontsFolders`フォントを含むフォルダーへのパスを指定する方法。

#### Q: Aspose.Words で複数のフォント フォルダーを設定できますか?

 A: はい、Aspose.Wordsで複数のフォントフォルダを設定するには、`SetFontsFolders`使用したいさまざまなフォント フォルダーのパスを指定して、このメソッドを複数回実行します。

#### Q: ドキュメントで使用されているフォントが定義されたフォント フォルダーに存在しない場合はどうなりますか?

A: ドキュメントで使用されているフォントが Aspose.Words で定義されているフォント フォルダーに存在しない場合は、代わりに代替フォントが使用されます。これにより、元のフォントが使用できない場合でも、ドキュメント内のテキストが常に正しく表示されるようになります。

#### Q: Aspose.Words で定義されたフォント フォルダーは、システムにインストールされているフォントよりも優先されますか?

A: はい、Aspose.Words で定義されたフォント フォルダーは、システムにインストールされているフォントよりも優先されます。つまり、定義されたフォント フォルダーとシステム フォントの両方に同じ名前のフォントが存在する場合、Word ドキュメントの処理時にはフォント フォルダーのバージョンが使用されます。