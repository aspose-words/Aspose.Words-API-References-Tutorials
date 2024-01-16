---
title: フォントの設定 フォルダー 複数のフォルダー
linktitle: フォントの設定 フォルダー 複数のフォルダー
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに複数のフォント フォルダーを設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに複数のフォント フォルダーを設定するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルを終えると、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する複数のフォント フォルダーを指定する方法がわかるようになります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: レンダリングするドキュメントをロードする
次に、レンダリングするドキュメントを次のコマンドを使用してロードできます。`Document`クラス。必ず正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 3: フォント フォルダーを設定する
を使用して複数のフォント フォルダーを設定できるようになりました。`FontSettings`クラスと`SetFontsFolders()`方法。使用するフォント フォルダーへのパスを配列で指定できます。この例では、2 つのフォント フォルダー「C:\MyFonts」を指定しています。\" および "D:\Misc\Fonts\」。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## ステップ 4: フォント設定を適用する
次に、フォント設定をドキュメントに適用する必要があります。`FontSettings`の財産`Document`クラス。

```csharp
doc.FontSettings = fontSettings;
```

## ステップ 5: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存するには、`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Aspose.Words for .NET を使用したフォント フォルダーの複数のフォルダーの設定のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//この設定は、デフォルトで検索されるデフォルトのフォント ソースをオーバーライドすることに注意してください。これで、これらのフォルダーのみが検索されるようになります
//フォントのレンダリングまたは埋め込み時のフォント。システム フォント ソースを維持しながら追加のフォント ソースを追加するには、FontSettings.GetFontSources と
//代わりに FontSettings.SetFontSources を使用してください。
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに複数のフォント フォルダーを設定する方法を学びました。このステップバイステップのガイドに従うことで、ドキュメントをレンダリングするときに使用する複数のフォント フォルダーを簡単に指定できます。 Aspose.Words は、ドキュメント内のフォントを使用したワード処理用の強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてドキュメントをレンダリングするときに使用されるフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words で複数のフォント フォルダーを設定するにはどうすればよいですか?

 A: Aspose.Words で複数のフォント フォルダーを設定するには、`SetFontsFolders`の方法`Fonts`カスタム フォント フォルダーの場所のリストを提供するクラス。

#### Q: 複数のフォント フォルダーを設定すると、Aspose.Words で処理されるすべてのドキュメントに影響しますか?

A: はい、複数のフォント フォルダーを設定すると、Aspose.Words で処理されるすべてのドキュメントに影響します。フォント フォルダーを定義すると、Aspose.Words はこれらの場所を使用してすべてのドキュメント内のフォントを検索します。

#### Q: Aspose.Words ではフォント フォルダーをいくつ定義できますか?

A: Aspose.Words では、フォント フォルダーを必要な数だけ定義できます。定義できるフォント フォルダーの数に特に制限はありません。

#### Q: Aspose.Words で定義されているフォント フォルダーを確認するにはどうすればよいですか?

 A: Aspose.Words で定義されているフォント フォルダーを確認するには、`GetFolders`の方法`Fonts`クラスを使用して、構成されたフォントフォルダーの場所を取得します。

#### Q: フォント フォルダーには特定のフォントを含める必要がありますか?

A: はい、フォント フォルダーには、Word 文書で使用するフォントが含まれている必要があります。 Aspose.Words は、ドキュメントを処理するときに、指定されたフォルダーでフォントを検索します。