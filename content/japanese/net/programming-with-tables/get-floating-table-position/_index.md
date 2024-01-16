---
title: フローティングテーブルの位置を取得する
linktitle: フローティングテーブルの位置を取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のフローティング テーブルの位置を取得する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/get-floating-table-position/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のフローティング テーブルの位置を取得する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内のフローティング テーブルの位置プロパティをプログラムで取得できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントのロードとテーブルへのアクセス
表を使用して Word Processing を開始するには、表を含む文書をロードしてアクセスする必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。また、ドキュメントにフローティング テーブルが含まれていることを確認してください。

## ステップ 3: フローティング テーブルの配置プロパティを取得する
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

ここでは、`foreach`ドキュメント内のすべての配列をループします。配列が float 型であるかどうかをチェックすることで確認します。`TextWrapping`財産。その場合、水平アンカー、垂直アンカー、絶対的な水平距離と垂直距離、オーバーラップ許可、絶対的な水平距離、および相対的な垂直位置合わせなど、テーブルの位置決めプロパティを出力します。
 
### Aspose.Words for .NET を使用したフローティング テーブルの位置の取得のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		//テーブルがフローティング タイプの場合は、その位置決めプロパティを出力します。
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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のフローティング テーブルの位置を取得する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内のフローティング テーブルの位置プロパティをプログラムで取得できます。この機能を使用すると、特定のニーズに応じてフローティング テーブルを分析および操作できます。