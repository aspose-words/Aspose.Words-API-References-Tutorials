---
title: フォントフォルダを優先的に設定
linktitle: フォントフォルダを優先的に設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときにフォント フォルダーを優先して設定するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-with-priority/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにフォント フォルダーを優先して設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、カスタム検索優先順位で複数のフォント フォルダーを指定する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: フォントフォルダを優先して設定する
次に、フォントフォルダの優先順位を設定するには、`FontSettings`クラスと`SetFontsSources()`メソッド。インスタンスを使用して複数のフォントソースを指定できます。`SystemFontSource`そして`FolderFontSource`この例では、デフォルトのシステム フォント ソースと、優先度 1 のカスタム フォント フォルダーの 2 つのフォント ソースを定義しています。

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## ステップ3: レンダリングするドキュメントを読み込む
これで、レンダリングするドキュメントをロードできます。`Document`クラス。正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Aspose.Words for .NET を使用してフォント フォルダーを優先順位付きで設定するためのサンプル ソース コード 
```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、フォント フォルダーを優先順位付きで設定する方法を学びました。このステップ バイ ステップ ガイドに従うことで、ドキュメントをレンダリングするときに、カスタム検索優先順位を使用して複数のフォント フォルダーを簡単に指定できます。Aspose.Words は、ドキュメント内のフォントを使用して Words を処理するための強力で柔軟な API を提供します。この知識があれば、ドキュメントを特定のニーズに合わせてレンダリングするときに使用するフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words でフォント フォルダーの優先順位を設定するにはどうすればよいでしょうか?

 A: Aspose.Wordsでフォントフォルダーの優先順位を設定するには、`SetFontsFoldersWithPriority`方法の`Fonts`フォント フォルダーの場所と優先順位を指定してクラスを作成します。

#### Q: フォントが優先順位の異なる複数のフォルダーに存在する場合はどうなりますか?

A: フォントが複数のフォルダーに異なる優先順位で存在する場合、Aspose.Words はドキュメントを処理するときに、最も優先順位の高いフォルダーのバージョンを使用します。

#### Q: Aspose.Words で同じ優先順位を持つ複数のフォント フォルダーを指定できますか?

A: はい、Aspose.Words では、同じ優先順位で複数のフォント フォルダーを指定できます。Aspose.Words は、ドキュメント内のフォントを検索するときに、それらすべてを同じ優先順位で考慮します。

#### Q: Aspose.Words で優先度が定義されたフォント フォルダーを確認するにはどうすればよいでしょうか?

 A: Aspose.Wordsで優先度が定義されたフォントフォルダーを確認するには、`GetFolders`方法の`Fonts`優先順位を含む設定されたフォント フォルダーのリストを取得するクラス。

#### Q: Aspose.Words でフォント フォルダーを優先して設定すると何に役立ちますか?

A: Aspose.Words でフォント フォルダーの優先順位を設定すると、Word 文書内のフォントの検索順序を制御できます。これにより、必要なフォントが確実に使用され、不要なフォント置換の問題を回避できます。