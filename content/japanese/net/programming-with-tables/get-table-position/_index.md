---
title: テーブルの位置を取得
linktitle: テーブルの位置を取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の表の位置を取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/get-table-position/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の位置を取得する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内の表の位置プロパティをプログラムで取得できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントを読み込み、テーブルにアクセスする
表を使用して Words Processing を開始するには、表を含むドキュメントを読み込んでアクセスする必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込む
Document doc = new Document(dataDir + "Tables.docx");

//アレイへのアクセス
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

「YOUR DOCUMENTS DIRECTORY」を実際のドキュメント ディレクトリへのパスに置き換えてください。また、位置を取得したいテーブルがドキュメントに含まれていることを確認してください。

## ステップ3: 配列の配置プロパティを取得する
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

ここでは、配列がfloat型であるかどうかを確認する条件を使用します。そうであれば、`RelativeHorizontalAlignment`そして`RelativeVerticalAlignment`プロパティを使用して、テーブルの相対的な水平および垂直配置を取得します。それ以外の場合は、`Alignment`配列の配置を取得するためのプロパティ。

### Aspose.Words for .NET を使用してテーブルの位置を取得するためのサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表の位置を取得する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書内の表の位置プロパティをプログラムで取得できます。この機能を使用すると、配列を特定の位置に従って分析および操作できます。