---
title: フォントフォルダシステムとカスタムフォルダを設定する
linktitle: フォントフォルダシステムとカスタムフォルダを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、システム フォント フォルダーとカスタム フォント フォルダーを設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、システム フォント フォルダーとカスタム フォルダーを設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する、システム フォルダーとカスタム フォルダーを含む複数のフォント フォルダーを指定する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集したレンダリングされたドキュメントを保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: レンダリングするドキュメントを読み込む
次に、レンダリングするドキュメントをロードします。`Document`クラス。正しいドキュメント パスを指定してください。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ3: システムフォントフォルダとカスタムフォントフォルダを設定する
システムフォントフォルダとカスタムフォルダを、`FontSettings`クラスと`SetFontsSources()`メソッド。まず、環境依存フォントソースのリストを取得するには、`GetFontsSources()`リストに保存します。その後、新しいインスタンスを作成できます。`FolderFontSource`フォントを含むカスタムフォルダへのパスを指定します。このインスタンスを既存のフォントソースのリストに追加します。最後に、`SetFontsSources()`新しいリストでフォント ソースを更新します。

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## ステップ4: フォント設定を適用する
次に、フォント設定を文書に適用する必要があります。`FontSettings`の財産`Document`クラス。

```csharp
doc.FontSettings = fontSettings;
```

## ステップ5: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存することができます。

  使用して`Save()`方法の`Document`クラス。正しいパスとファイル名を必ず指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Aspose.Words for .NET を使用してフォント フォルダー システムとカスタム フォルダーを設定するためのサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//デフォルトで検索される環境依存のフォント ソースの配列を取得します。
//たとえば、Windows マシンでは「Windows\Fonts\」ソースが含まれます。
//フォント エントリの追加や削除がはるかに簡単になるように、この配列を新しいリストに追加します。
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
//Aspose.Words に次のフォルダーでフォントを検索するように指示する新しいフォルダー ソースを追加します。
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
//フォントを含むカスタム フォルダーを既存のフォント ソースのリストに追加します。
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、システム フォント フォルダーとカスタム フォルダーを設定する方法を学習しました。このステップ バイ ステップ ガイドに従うことで、ドキュメントをレンダリングするときに使用する、システム フォルダーやカスタム フォルダーなどの複数のフォント フォルダーを簡単に指定できます。Aspose.Words は、ドキュメント内のフォントを使用して Words を処理するための強力で柔軟な API を提供します。この知識があれば、ドキュメントを特定のニーズに合わせてレンダリングするときに使用するフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words でシステム フォント フォルダーを設定するにはどうすればよいでしょうか?

A: Aspose.Words でシステム フォント フォルダーを設定するには、何もする必要はありません。Aspose.Words は、オペレーティング システムにインストールされているシステム フォントを自動的に使用します。

#### Q: Aspose.Words でカスタム フォント フォルダーを設定するにはどうすればよいでしょうか?

 A: Aspose.Wordsでカスタムフォントフォルダーを設定するには、`SetFontsFolders`方法の`Fonts`カスタム フォント フォルダーの場所を指定するクラス。

#### Q: Aspose.Words で複数のカスタム フォント フォルダーを指定できますか?

 A: はい、Aspose.Wordsでは複数のカスタムフォントフォルダを指定することができます。`SetFontsFolders`方法の`Fonts`フォルダーの場所のリストを持つクラス。

#### Q: Aspose.Words で定義されているフォント フォルダーを確認するにはどうすればよいですか?

 Aspose.Wordsで定義されているフォントフォルダーを確認するには、`GetFolders`方法の`Fonts`構成されたフォント フォルダーのリストを取得するクラス。

#### Q: Aspose.Words では、カスタム フォルダー フォントがシステム フォントよりも優先されますか?

A: はい、Aspose.Words ではカスタム フォルダー フォントがシステム フォントよりも優先されます。カスタム フォルダーとシステム フォントの両方にフォントが存在する場合、Aspose.Words はカスタム フォルダーのバージョンを使用します。