---
title: 利用可能なフォントのリストを取得する
linktitle: 利用可能なフォントのリストを取得する
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET で使用できるフォントのリストを取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/get-list-of-available-fonts/
---
このチュートリアルでは、Aspose.Words for .NET で使用できるフォントのリストを取得する方法を説明します。使用可能なフォントのリストにより、ドキュメントで使用できるフォントがわかります。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

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

## ステップ 2: フォント ソースを構成する
次に、インスタンスを作成します。`FontSettings`を使用して既存のフォント ソースを取得します。`GetFontsSources()`方法。また、フォントが含まれているフォルダーを指定して、新しいフォント ソースを追加します。

```csharp
//フォントソースを設定する
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

//新しいフォントソースを追加する
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## ステップ 3: 利用可能なフォントのリストを取得する
次に、使用可能なフォントを参照します。`GetAvailableFonts()`最初に更新されたフォント ソースのメソッド。

```csharp
//使用可能なフォントのリストを取得する
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Aspose.Words for .NET を使用して利用可能なフォントのリストを取得するためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
//新しいフォルダー ソースを追加して、次のフォルダーでフォントを検索するように Aspose.Words に指示します。
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
//フォントを含むカスタム フォルダーを既存のフォント ソースのリストに追加します。
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## 結論
このチュートリアルでは、Aspose.Words for .NET で利用可能なフォントのリストを取得する方法を説明しました。これにより、ドキュメントで使用できるフォントがわかります。この機能を自由に使用して、ニーズに合わせて適切なフォントを選択してください。

### よくある質問

#### Q: Aspose.Words で利用可能なフォントのリストを取得するにはどうすればよいですか?

 A: Aspose.Words で利用可能なフォントのリストを取得するには、`FontsProvider`クラスと`GetAvailableFonts`方法。このメソッドは、システムにインストールされているすべてのフォントのリストを返します。

#### Q: Aspose.Words で特定の条件で使用可能なフォントのリストをフィルタリングできますか?

A: はい、特定の条件を使用して、Aspose.Words で使用可能なフォントのリストをフィルタリングできます。たとえば、ファミリー、スタイル、言語ごとにフォントをフィルタリングできます。

#### Q: Word 文書で使用可能なフォントのリストを使用するにはどうすればよいですか?

 A: Word 文書で使用できるフォントのリストを使用するには、リストを参照し、`FontSettings` Aspose.Words のクラス。