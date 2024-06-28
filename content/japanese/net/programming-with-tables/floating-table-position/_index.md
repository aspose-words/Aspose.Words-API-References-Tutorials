---
title: フローティングテーブルの位置
linktitle: フローティングテーブルの位置
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内にテーブルをフローティング位置に配置する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/floating-table-position/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のフローティング位置にテーブルを配置する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内のフローティング テーブルの位置と配置をプログラムで制御できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントのロードとテーブルへのアクセス
表を使用して Word Processing を開始するには、その表を含む文書をロードしてアクセスする必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードする
Document doc = new Document(dataDir + "Table wrapped by text.docx");

//アレイへのアクセス
Table table = doc.FirstSection.Body.Tables[0];
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。また、ドキュメントにフローティング位置に配置される表が含まれていることを確認してください。

## ステップ 3: フローティング ボードの位置決め
次に、Aspose.Words for .NET によって提供されるプロパティを使用して、テーブルを浮動位置に配置します。次のコードを使用します。

```csharp
//フローティングテーブルの位置決め
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

ここで使用するのは、`AbsoluteHorizontalDistance`プロパティを使用して、ページの左端から表までの絶対水平距離を設定します。また、`RelativeVerticalAlignment`プロパティを使用して、周囲のコンテンツに対するテーブルの相対的な垂直方向の配置を設定します。

## ステップ 4: 変更したドキュメントを保存する
最後に、テーブルをフローティング位置に配置して、変更したドキュメントを保存する必要があります。次のコードを使用します。

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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内でテーブルをフローティング位置に配置する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内のフローティング テーブルの位置と配置をプログラムで制御できます。