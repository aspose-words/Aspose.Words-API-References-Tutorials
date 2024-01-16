---
title: リスタートリスト番号
linktitle: リスタートリスト番号
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のリストの番号をリセットする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-list/restart-list-number/
---
このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のリストの番号をリセットする方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、開発環境に Aspose.Words for .NET がインストールされ、構成されていることを確認してください。まだライブラリをダウンロードしてインストールしていない場合は、次からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ドキュメントとドキュメント ジェネレーターの作成

まず、新しいドキュメントと関連するドキュメント ジェネレーターを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 最初のリストの作成とカスタマイズ

次に、既存のテンプレートに基づいてリストを作成し、そのレベルをカスタマイズします。

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## ステップ 3: 最初のリストに項目を追加する

ドキュメント ビルダーを使用して、最初のリストに項目を追加し、リスト番号を削除します。

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## ステップ 4: 2 番目のリストの作成とカスタマイズ

番号をリセットして最初のリストを再利用するには、元のリスト レイアウトのコピーを作成します。

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

必要に応じて、2 番目のリストに追加の変更を加えることもできます。

## ステップ 5: 2 番目のリストに項目を追加する

ドキュメント ビルダーを再度使用して、2 番目のリストに項目を追加し、リスト番号を削除します。

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## ステップ 6: 変更したドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

それで ！ Aspose.Words for .NET を使用して Word 文書内のリストの番号を正常にリセットしました。

### リスト番号リセットのサンプル ソース コード

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//テンプレートに基づいてリストを作成します。
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

//最初のリストを再利用するには、元のリストの書式設定のコピーを作成して、番号付けをやり直す必要があります。
List list2 = doc.Lists.AddCopy(list1);

//新しい開始番号の設定など、任意の方法で新しいリストを変更できます。
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### よくある質問

#### Q: Aspose.Words でリストの番号付けを再開するにはどうすればよいですか?

 A: Aspose.Words でリストの番号付けを再開するには、`ListRestartAtNumber`の方法`List`クラス。このメソッドを使用すると、リストを再開する新しいダイヤル値を設定できます。たとえば、次のように使用できます`list.ListRestartAtNumber(1)`番号付けを 1 からやり直すには

#### Q: Aspose.Words で再開されたリストの番号付けのプレフィックスとサフィックスをカスタマイズすることはできますか?

 A: はい、Aspose.Words で再開されたリストの番号付けのプレフィックスとサフィックスをカスタマイズできます。の`ListLevel`クラスは次のようなプロパティを提供します`ListLevel.NumberPrefix`そして`ListLevel.NumberSuffix`これにより、リスト内の各レベルのプレフィックスとサフィックスを指定できます。これらのプロパティを使用して、必要に応じてプレフィックスとサフィックスをカスタマイズできます。

#### Q: リストを再開する特定の番号付け値を指定するにはどうすればよいですか?

A: リストを再開する特定の数値を指定するには、`ListRestartAtNumber`必要な値を引数として渡すメソッド。たとえば、番号付けを 5 から再開するには、次のようにします。`list.ListRestartAtNumber(5)`.

#### Q: Aspose.Words で複数レベルのリストの番号付けを再開することはできますか?

 A: はい、Aspose.Words は複数のリスト レベルの再起動番号付けをサポートしています。適用できるのは、`ListRestartAtNumber`各リストレベルで個別に番号付けを再開する方法。たとえば、次のように使用できます`list.Levels[0].ListRestartAtNumber(1)`最初のリストレベルを 1 から再開し、`list.Levels[1].ListRestartAtNumber(1)` 2 番目のレベルのリストを 1 から再開するなど。



