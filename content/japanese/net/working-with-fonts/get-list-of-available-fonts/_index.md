---
title: 利用可能なフォントのリストを取得する
linktitle: 利用可能なフォントのリストを取得する
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET で使用可能なフォントのリストを取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/get-list-of-available-fonts/
---
このチュートリアルでは、Aspose.Words for .NET で使用できるフォントのリストを取得する方法について説明します。使用可能なフォントのリストにより、ドキュメントで使用できるフォントがわかります。.NET プロジェクトでコードを理解して実装できるように、手順を追って説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ

## ステップ1: ドキュメントディレクトリを定義する
まず、Word文書の場所にディレクトリパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`コード内に適切なパスを追加します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: フォントソースを構成する
次に、インスタンスを作成します`FontSettings`既存のフォントソースを取得するには、`GetFontsSources()`メソッド。フォントを含むフォルダーを指定して、新しいフォント ソースも追加します。

```csharp
//フォントソースを構成する
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

//新しいフォントソースを追加する
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## ステップ3: 利用可能なフォントのリストを取得する
次に、利用可能なフォントを参照します。`GetAvailableFonts()`最初に更新されたフォント ソースのメソッド。

```csharp
//利用可能なフォントのリストを取得する
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
//Aspose.Words に次のフォルダーでフォントを検索するように指示する新しいフォルダー ソースを追加します。
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
このチュートリアルでは、Aspose.Words for .NET で使用できるフォントのリストを取得する方法について説明しました。これにより、ドキュメントで使用できるフォントがわかります。この機能を使用して、ニーズに合った適切なフォントを自由に選択してください。

### よくある質問

#### Q: Aspose.Words で使用できるフォントのリストを取得するにはどうすればよいですか?

 A: Aspose.Wordsで利用可能なフォントのリストを取得するには、`FontsProvider`クラスと`GetAvailableFonts`メソッド。このメソッドは、システムにインストールされているすべてのフォントのリストを返します。

#### Q: Aspose.Words で、特定の条件で使用可能なフォントのリストをフィルターできますか?

A: はい、特定の条件を使用して、Aspose.Words で使用可能なフォントのリストをフィルターできます。たとえば、フォントをファミリ、スタイル、言語でフィルターできます。

#### Q: Word 文書で使用可能なフォントのリストを使用するにはどうすればよいですか?

 A: Word文書で使用可能なフォントのリストを使用するには、リストを参照し、メソッドとプロパティを使用して適切なフォントを選択します。`FontSettings` Aspose.Words のクラス。