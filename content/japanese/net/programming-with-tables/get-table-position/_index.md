---
title: テーブル位置の取得
linktitle: テーブル位置の取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の表の位置を取得する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/get-table-position/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の位置を取得する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内の表の配置プロパティをプログラムで取得できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントのロードとテーブルへのアクセス
表を使用して Word Processing を開始するには、その表を含む文書をロードしてアクセスする必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードする
Document doc = new Document(dataDir + "Tables.docx");

//アレイへのアクセス
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。また、位置を取得したい表がドキュメントに含まれていることを確認してください。

## ステップ 3: 配列の配置プロパティを取得する
次に、配列の配置タイプを確認し、適切な配置プロパティを取得します。次のコードを使用します。

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

ここでは条件を使用して、配列が float 型であるかどうかを確認します。その場合は、`RelativeHorizontalAlignment`そして`RelativeVerticalAlignment`プロパティを使用して、テーブルの相対的な水平方向および垂直方向の配置を取得します。それ以外の場合は、`Alignment`プロパティを使用して配列の位置合わせを取得します。

### Aspose.Words for .NET を使用したテーブル位置の取得のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の位置を取得する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内のテーブルの配置プロパティをプログラムで取得できます。この機能を使用すると、特定の位置に従って配列を分析および操作できます。