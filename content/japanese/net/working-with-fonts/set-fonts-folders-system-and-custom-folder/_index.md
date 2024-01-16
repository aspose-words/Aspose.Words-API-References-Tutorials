---
title: フォントフォルダーシステムとカスタムフォルダーを設定する
linktitle: フォントフォルダーシステムとカスタムフォルダーを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをレンダリングするときに、システム フォント フォルダーとカスタム フォント フォルダーを設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにシステム フォント フォルダーとカスタム フォルダーを設定する手順を段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルを終えると、Aspose.Words for .NET を使用してドキュメントをレンダリングするときに使用する、システム フォルダーやカスタム フォルダーを含む複数のフォント フォルダーを指定する方法がわかるようになります。

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

## ステップ 3: システム フォント フォルダーとカスタム フォント フォルダーを設定する
これで、システム フォント フォルダーとカスタム フォルダーを設定できるようになりました。`FontSettings`クラスと`SetFontsSources()`方法。まず、環境依存のフォント ソースのリストを取得する必要があります。`GetFontsSources()`そしてそれをリストに保存します。その後、新しいインスタンスを作成できます`FolderFontSource`フォントを含むカスタム フォルダーへのパスを指定します。このインスタンスを既存のフォント ソースのリストに追加します。最後に、使用します`SetFontsSources()`をクリックして、新しいリストでフォント ソースを更新します。

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## ステップ 4: フォント設定を適用する
次に、フォント設定をドキュメントに適用する必要があります。`FontSettings`の財産`Document`クラス。

```csharp
doc.FontSettings = fontSettings;
```

## ステップ 5: レンダリングされたドキュメントを保存する
最後に、レンダリングされたドキュメントをファイルに保存できます。

  を使用して`Save()`の方法`Document`クラス。必ず正しいパスとファイル名を指定してください。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Aspose.Words for .NET を使用したフォント フォルダー システムとカスタム フォルダーの設定のサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//デフォルトで検索される環境依存のフォント ソースの配列を取得します。
//たとえば、これには Windows マシン上の「Windows\Fonts\」ソースが含まれます。
//この配列を新しいリストに追加して、フォント エントリの追加または削除をより簡単にします。
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
//新しいフォルダー ソースを追加して、次のフォルダーでフォントを検索するように Aspose.Words に指示します。
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
//フォントを含むカスタム フォルダーを既存のフォント ソースのリストに追加します。
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントをレンダリングするときにシステム フォント フォルダーとカスタム フォルダーを設定する方法を学習しました。このステップバイステップのガイドに従うことで、ドキュメントのレンダリング時に使用するシステム フォルダーやカスタム フォルダーを含む複数のフォント フォルダーを簡単に指定できます。 Aspose.Words は、ドキュメント内のフォントを使用したワード処理用の強力で柔軟な API を提供します。この知識があれば、特定のニーズに合わせてドキュメントをレンダリングするときに使用されるフォント ソースを制御およびカスタマイズできます。

### よくある質問

#### Q: Aspose.Words でシステム フォント フォルダーを設定するにはどうすればよいですか?

A: Aspose.Words でシステム フォント フォルダーを設定するには、何もする必要はありません。 Aspose.Words は、オペレーティング システムにインストールされているシステム フォントを自動的に使用します。

#### Q: Aspose.Words でカスタム フォント フォルダーを設定するにはどうすればよいですか?

 A: Aspose.Words でカスタム フォント フォルダーを設定するには、`SetFontsFolders`の方法`Fonts`カスタム フォント フォルダーの場所を指定するクラス。

#### Q: Aspose.Words で複数のカスタム フォント フォルダーを指定できますか?

 A: はい、Aspose.Words で複数のカスタム フォント フォルダーを指定できます。`SetFontsFolders`の方法`Fonts`フォルダーの場所のリストを含むクラス。

#### Q: Aspose.Words で定義されているフォント フォルダーを確認するにはどうすればよいですか?

 Aspose.Words で定義されたフォント フォルダーを確認するには、`GetFolders`の方法`Fonts`クラスを使用して、構成されたフォントフォルダーのリストを取得します。

#### Q: Aspose.Words では、カスタム フォルダー フォントがシステム フォントよりも優先されますか?

A: はい、Aspose.Words ではカスタム フォルダー フォントがシステム フォントよりも優先されます。フォントがカスタム フォルダーとシステム フォントの両方に存在する場合、Aspose.Words はカスタム フォルダーのバージョンを使用します。