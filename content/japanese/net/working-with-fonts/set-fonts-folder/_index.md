---
title: フォントフォルダーの設定
linktitle: フォントフォルダーの設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でフォント ディレクトリを設定し、ドキュメントで使用されるフォントを確実に使用できるようにする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folder/
---
このチュートリアルでは、Aspose.Words for .NET でフォント ディレクトリを設定する方法を説明します。 Word 文書で使用されるフォントが含まれるディレクトリを指定する方法を学習します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: フォント ディレクトリを設定する
のインスタンスを作成します。`FontSettings`クラスを作成して使用します`SetFontsFolder`フォントを含むディレクトリを指定するメソッドです。交換する`"Fonts"`実際のフォントディレクトリの名前に置き換えます。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## ステップ 3: フォント設定を使用してドキュメントをロードする
使用`LoadOptions`のフォント設定を指定するクラス`FontSettings`オプション。次に、`Document`クラスを使用して、これらのオプションを使用してドキュメントをロードします。

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Aspose.Words for .NET を使用した Set Fonts Folder のサンプル ソース コード 

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
おめでとうございます！ Aspose.Words for .NET でフォント ディレクトリを設定する方法がわかりました。この機能を使用すると、ドキュメントで使用されるフォントが利用可能かどうかを確認し、フォントの表示の一貫性を確保できます。

### よくある質問

#### Q: Aspose.Words でカスタム フォント フォルダーを設定するにはどうすればよいですか?

 A: Aspose.Words でカスタム フォント フォルダーを設定するには、`FontsFolder`クラスと`SetFontsFolders`フォントを含むフォルダーへのパスを指定するメソッド。

#### Q: Aspose.Words で複数のフォント フォルダーを設定できますか?

 A: はい、Aspose.Words で複数のフォント フォルダーを設定するには、`SetFontsFolders`使用するさまざまなフォント フォルダーのパスを指定してメソッドを複数回実行します。

#### Q: ドキュメントで使用されているフォントが、定義されたフォント フォルダーに存在しない場合はどうなりますか?

A: ドキュメントで使用されているフォントが Aspose.Words で定義されたフォント フォルダーに存在しない場合は、代わりのフォントが使用されます。これにより、元のフォントが使用できない場合でも、ドキュメント内のテキストが常に正しく表示されます。

#### Q: Aspose.Words で定義されたフォント フォルダーは、システムにインストールされているフォントよりも優先されますか?

A: はい、Aspose.Words で定義されたフォント フォルダーは、システムにインストールされているフォントよりも優先されます。これは、同じ名前のフォントが定義されたフォント フォルダーとシステム フォントの両方に存在する場合、Word 文書を処理するときにフォント フォルダー内のバージョンが使用されることを意味します。