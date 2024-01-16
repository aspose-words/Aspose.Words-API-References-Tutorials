---
title: サフィックスなしで置換を取得
linktitle: サフィックスなしで置換を取得
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書でサフィックスのないオーバーライドを取得する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/get-substitution-without-suffixes/
---

このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して、Word 文書内の接尾辞なしでオーバーライドを取得する方法を説明します。接尾辞のない置換は、ドキュメントを表示または印刷する際のフォント置換の問題を解決するために使用されます。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

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

## ステップ 2: ドキュメントをロードし、サフィックスなしで置換を構成する
次に、次のコマンドを使用してドキュメントをロードします。`Document`クラスを作成し、`DocumentSubstitutionWarnings`クラス。フォントが含まれるフォルダーを指定して、フォント ソースも追加します。

```csharp
//ドキュメントをロードし、接尾辞なしで置換を構成します
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## ステップ 3: ドキュメントを保存する
最後に、サフィックスなしのオーバーライドを適用してドキュメントを保存します。

```csharp
//文書を保存する
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Aspose.Words for .NET を使用したサフィックスなしの置換の取得のサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の接尾辞なしでオーバーライドを取得する方法を説明しました。接尾辞のない置換は、フォント置換の問題を解決するのに役立ちます。ドキュメントの表示と印刷を改善するために、この機能を自由に使用してください。

### よくある質問

#### Q: Aspose.Words がフォント置換にサフィックスを追加するのはなぜですか?

A: Aspose.Words は、元のフォントと置換されたフォントの間の競合を避けるために、フォント置換にサフィックスを追加します。これにより、ドキュメントの変換および操作時に最大限の互換性が保証されます。

#### Q: Aspose.Words でサフィックスのないフォント置換を取得するにはどうすればよいですか?

 A: Aspose.Words でサフィックスのないフォント置換を取得するには、`FontSubstitutionSettings`クラスと`RemoveSuffixes`財産。このプロパティを次のように設定する`true`接尾辞を追加せずにフォント置換を取得します。

#### Q: Aspose.Words のフォント置換へのサフィックスの追加を無効にすることはできますか?

A: いいえ、Aspose.Words のフォント置換へのサフィックスの追加を無効にすることはできません。ドキュメントの互換性と一貫性を確保するために、デフォルトでサフィックスが追加されます。

#### Q: Aspose.Words のフォント置換で不要な接尾辞を除外するにはどうすればよいですか?

 A: Aspose.Words のフォント置換で不要なサフィックスをフィルタリングして除外するには、次のような文字列処理テクニックを使用できます。`Replace`または`Substring`含めたくない特定のサフィックスを削除するメソッド。