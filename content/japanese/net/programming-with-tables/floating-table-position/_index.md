---
title: フローティングテーブルの位置
linktitle: フローティングテーブルの位置
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内でテーブルをフローティング位置に配置する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/floating-table-position/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のフローティング位置にテーブルを配置する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内のフローティング テーブルの位置と配置をプログラムで制御できるようになります。

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

//アレイへのアクセス
Table table = doc.FirstSection.Body.Tables[0];
```

「YOUR DOCUMENTS DIRECTORY」を実際のドキュメント ディレクトリへのパスに置き換えてください。また、ドキュメントにフローティング位置に配置されるテーブルが含まれていることを確認してください。

## ステップ3: フローティングボードの配置
次に、Aspose.Words for .NET が提供するプロパティを使用して、テーブルをフローティング位置に配置します。次のコードを使用します。

```csharp
//フローティングテーブルの配置
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

ここでは`AbsoluteHorizontalDistance`プロパティを使用して、ページの左端からの表の絶対的な水平距離を設定します。また、`RelativeVerticalAlignment`周囲のコンテンツに対するテーブルの相対的な垂直配置を設定するプロパティ。

## ステップ4: 変更したドキュメントを保存する
最後に、テーブルをフローティング位置に配置し、変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
//変更したドキュメントを保存する
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用したフローティング テーブル位置のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内のフローティング位置にテーブルを配置する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書内のフローティング テーブルの位置と配置をプログラムで制御できます。