---
title: フローティングテーブルの位置を取得する
linktitle: フローティングテーブルの位置を取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のフローティング テーブルの位置を取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/get-floating-table-position/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のフローティング テーブルの位置を取得する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内のフローティング テーブルの位置プロパティをプログラムで取得できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントを読み込み、テーブルにアクセスする
表を使用して Words Processing を開始するには、表を含むドキュメントを読み込んでアクセスする必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込む
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

「YOUR DOCUMENTS DIRECTORY」を実際のドキュメント ディレクトリへのパスに置き換えてください。また、ドキュメントにフローティング テーブルが含まれていることを確認してください。

## ステップ3: フローティングテーブルの位置プロパティを取得する
次に、ドキュメント内のすべてのテーブルをループして、フローティング テーブルの配置プロパティを取得します。次のコードを使用します。

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
//配列が浮動小数点型の場合は、その配置プロパティを出力します。
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

ここでは、`foreach` loop を使ってドキュメント内のすべての配列をループします。配列が float 型かどうかは、`TextWrapping`プロパティ。そうであれば、水平アンカー、垂直アンカー、絶対水平距離と垂直距離、重なり許可、絶対水平距離、垂直配置相対など、テーブルの配置プロパティを出力します。
 
### Aspose.Words for .NET を使用してフローティング テーブルの位置を取得するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		//テーブルがフローティング タイプの場合は、その配置プロパティを出力します。
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のフローティング テーブルの位置を取得する方法を学習しました。このステップ バイ ステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書内のフローティング テーブルの位置プロパティをプログラムで取得できます。この機能を使用すると、特定のニーズに応じてフローティング テーブルを分析および操作できます。