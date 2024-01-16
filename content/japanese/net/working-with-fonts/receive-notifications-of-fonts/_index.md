---
title: フォントの通知を受け取る
linktitle: フォントの通知を受け取る
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用するときにフォントが見つからない、または代替されたという通知を受け取る方法について説明します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/receive-notifications-of-fonts/
---

このチュートリアルでは、Aspose.Words for .NET の使用中にフォント通知を受け取る方法を説明します。フォント通知を使用すると、ドキュメント内の欠落フォントまたは代替フォントを検出して管理できます。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

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

## ステップ 2: ドキュメントをロードし、フォント設定を構成する
次に、次のコマンドを使用してドキュメントをロードします。`Document`クラスを作成し、を使用してフォント設定を構成します。`FontSettings`クラス。フォントが見つからない場合に使用するデフォルトのフォントを設定します。

```csharp
//ドキュメントをロードしてフォント設定を構成します
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## ステップ 3: 通知ハンドラーを設定する
次に、次を実装して通知ハンドラーを定義します。`IWarningCallback`インターフェース。これにより、ドキュメントを保存するときにフォントの警告を収集できるようになります。

```csharp
//通知ハンドラーを定義する
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## ステップ 4: フォント設定を適用してドキュメントを保存する
最後に、フォント設定をドキュメントに適用して保存します。フォントの警告は、前に定義した通知ハンドラーによってキャプチャされます。

```csharp
//フォント設定を適用してドキュメントを保存します
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Aspose.Words for .NET を使用したフォントの通知の受信のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//フォントが見つからない場合に使用するデフォルトのフォントを選択できます。
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
//テストのために、存在しないフォルダー内でのみフォントを検索するように Aspose.Words を設定します。 Aspose.Words では機能しないため、
//指定されたディレクトリ内のフォントを検索すると、レンダリング中にドキュメント内のフォントがデフォルトのフォントに置き換えられます。
// FontSettings.DefaultFontName で指定されたフォント。コールバックを使用して、このサブスーツを取得できます。
fontSettings.SetFontsFolder(string.Empty, false);
//ドキュメントの保存中に生成された警告を収集する IWarningCallback を実装する新しいクラスを作成します。
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## 結論
このチュートリアルでは、Aspose.Words for .NET の使用中にフォント通知を受け取る方法について説明しました。フォント通知を使用すると、ドキュメント内の欠落フォントまたは代替フォントを検出して管理できます。この機能を使用して、文書内のフォントの一貫性を確保し、フォントが見つからない場合に適切な措置を講じます。

### よくある質問

#### Q: Aspose.Words で見つからないフォントの通知を受け取るにはどうすればよいですか?

 A: Aspose.Words で見つからないフォントの通知を受け取るには、`FontSettings`クラスと`FontSubstitutionCallback`イベント。ドキュメントの処理中にフォントが見つからない場合に通知を受けるようにコールバック メソッドを設定できます。

#### Q: Word 文書でフォントが見つからない場合はどうすればよいですか?

A: Word 文書内でフォントが見つからない場合は、さまざまな方法を使用できます。 Aspose.Words アプリケーションを実行するシステムに不足しているフォントをインストールするか、不足しているフォントを利用可能な代替フォントで置き換えることができます。

#### Q: Aspose.Words で代替フォントの通知を受け取ることはできますか?

 A: はい、Aspose.Words で代替フォントの通知を受け取ることができます。文書処理中にフォントが置き換えられると、`FontSubstitutionCallback`イベントを確認し、適切なアクションを実行してテキストの外観を調整します。

#### Q: Aspose.Words でフォントが置き換えられる場合、テキストの外観の一貫性を保つにはどうすればよいですか?

A: フォントを置き換えるときにテキストの外観の一貫性を維持するには、フォント サイズ、スタイル、色などのテキスト書式設定プロパティを調整できます。元のフォントと見た目が似ている代替フォントの使用を検討することもできます。