---
title: フォントフォルダーを優先的に設定する
linktitle: フォントフォルダーを優先的に設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに優先的にフォント フォルダーを設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-with-priority/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにフォント フォルダーを優先的に設定するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後では、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、カスタム検索優先順位で複数のフォント フォルダーを指定する方法がわかります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2：フォントフォルダーを優先的に設定する
次に、を使用してフォントフォルダーを優先的に設定できます。`FontSettings`クラスと`SetFontsSources()`方法。のインスタンスを使用して複数のフォント ソースを指定できます。`SystemFontSource`そして`FolderFontSource`。この例では、デフォルトのシステム フォント ソースと優先度 1 のカスタム フォント フォルダーという 2 つのフォント ソースを定義しました。

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## ステップ 3: レンダリングするドキュメントをロードする
これで、ドキュメントをロードしてレンダリングできるようになります。`Document`クラス。必ず正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 4: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Aspose.Words for .NET を使用してフォント フォルダーを優先的に設定するためのサンプル ソース コード 
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
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、フォント フォルダーを優先的に設定する方法を学びました。このステップバイステップのガイドに従うことで、ドキュメントをレンダリングするときにカスタム検索優先順位を使用して複数のフォント フォルダーを簡単に指定できます。 Aspose.Words は、ドキュメント内のフォントを使用したワード処理用の強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてドキュメントをレンダリングするときに使用されるフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words でフォント フォルダーを優先的に設定するにはどうすればよいですか?

 A: Aspose.Words でフォント フォルダーを優先的に設定するには、`SetFontsFoldersWithPriority`の方法`Fonts`フォント フォルダーの場所とその優先順位を指定して、クラスを指定します。

#### Q: フォントが優先度の異なる複数のフォルダーに存在する場合はどうなりますか?

A: 優先順位の異なる複数のフォルダーにフォントが存在する場合、Aspose.Words はドキュメントを処理するときに、最も優先順位の高いフォルダーのバージョンを使用します。

#### Q: Aspose.Words で同じ優先順位を持つ複数のフォント フォルダーを指定できますか?

A: はい、Aspose.Words では同じ優先順位を持つ複数のフォント フォルダーを指定できます。 Aspose.Words は、ドキュメント内のフォントを検索するときに、それらをすべて同じ優先順位で考慮します。

#### Q: Aspose.Words で優先的に定義されているフォント フォルダーを確認するにはどうすればよいですか?

 A: Aspose.Words で優先的に定義されているフォント フォルダーを確認するには、`GetFolders`の方法`Fonts`クラスを使用して、設定されたフォント フォルダーの優先順位を含むリストを取得します。

#### Q: Aspose.Words でフォント フォルダーを優先的に設定すると、どのような意味になりますか?

A: Aspose.Words でフォント フォルダーに優先順位を設定すると、Word 文書内のフォントの検索順序を制御できます。これにより、必要なフォントが確実に使用され、不要なフォント置換の問題を回避できます。