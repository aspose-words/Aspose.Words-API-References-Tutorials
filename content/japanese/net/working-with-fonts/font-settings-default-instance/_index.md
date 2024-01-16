---
title: フォント設定のデフォルトインスタンス
linktitle: フォント設定のデフォルトインスタンス
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のデフォルトのフォント設定を構成する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/font-settings-default-instance/
---

このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して Word 文書のデフォルトのフォント設定を構成する方法を説明します。デフォルトのフォント設定を使用すると、ドキュメントのロードおよびレンダリング時に使用するフォント ソースを指定できます。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: デフォルトのフォント設定を構成する
次に、インスタンスを作成します。`FontSettings`使用して`FontSettings.DefaultInstance`次に、ドキュメントの読み込みとレンダリング時に使用されるフォント ソースを指定します。この例では、システム フォント ソースとフォルダー フォント ソースを使用しています。

```csharp
//デフォルトのフォント設定を構成する
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## ステップ 3: フォント設定を使用してドキュメントをアップロードする
次に、次を使用してドキュメントをロードします`LoadOptions`使用するフォント設定を指定します。

```csharp
//フォント設定を使用してドキュメントをロードします
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Aspose.Words for .NET を使用したフォント設定のデフォルト インスタンスのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のデフォルトのフォント設定を構成する方法を説明しました。ドキュメントのロードおよびレンダリング時に使用するフォント ソースを指定することにより、ドキュメント内のフォントの外観を制御できます。この機能を自由に使用して、プロジェクトのフォント設定をカスタマイズしてください。

### よくある質問

#### Q: Aspose.Words でデフォルトのフォントを設定するにはどうすればよいですか?

 A: Aspose.Words でデフォルトのフォントを設定するには、`FontSettings`クラスと`DefaultFontName`プロパティで目的のフォントの名前を指定します。

#### Q: Aspose.Words でデフォルトのフォント サイズを指定できますか?

 A: はい、Aspose.Words でデフォルトのフォント サイズを指定できます。`DefaultFontSize`の財産`FontSettings`クラス。希望のポイントサイズを設定できます。

#### Q: Aspose.Words でデフォルトのフォントの色を設定することはできますか?

 A: はい、Aspose.Words でデフォルトのフォントの色を設定するには、`DefaultColor`の財産`FontSettings`クラス。 RGB 値または事前定義された名前を使用して色を指定できます。

#### Q: デフォルトのフォント設定はすべてのドキュメントに適用されますか?

A: はい、デフォルトのフォント設定は、個々の文書に特定の設定が設定されていない限り、Aspose.Words で作成または編集されたすべての文書に適用されます。