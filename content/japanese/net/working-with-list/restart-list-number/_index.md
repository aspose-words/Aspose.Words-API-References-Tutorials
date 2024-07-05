---
title: 再開リスト番号
linktitle: 再開リスト番号
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のリストの番号をリセットする方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-list/restart-list-number/
---
このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のリストの番号をリセットする方法を説明します。提供されている C# ソース コードについて説明し、独自のプロジェクトに実装する方法を示します。

始めるには、開発環境にAspose.Words for .NETがインストールされ、構成されていることを確認してください。まだインストールしていない場合は、次の場所からライブラリをダウンロードしてインストールしてください。[Aspose.Releases]https://releases.aspose.com/words/net/.

## ステップ1: ドキュメントとドキュメントジェネレーターの作成

まず、新しいドキュメントと関連するドキュメント ジェネレーターを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: 最初のリストの作成とカスタマイズ

次に、既存のテンプレートに基づいてリストを作成し、そのレベルをカスタマイズします。

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## ステップ3: 最初のリストにアイテムを追加する

ドキュメント ビルダーを使用して、最初のリストに項目を追加し、リスト番号を削除します。

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## ステップ4: 2番目のリストの作成とカスタマイズ

番号をリセットして最初のリストを再利用するには、元のリスト レイアウトのコピーを作成します。

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

必要に応じて、2 番目のリストに追加の変更を加えることもできます。

## ステップ5: 2番目のリストにアイテムを追加する

ドキュメント ビルダーを再度使用して、2 番目のリストに項目を追加し、リスト番号を削除します。

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## ステップ6: 変更したドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

これで、Aspose.Words for .NET を使用して Word 文書内のリストの番号を正常にリセットできました。

### リスト番号リセットのサンプルソースコード

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

//最初のリストを再利用するには、元のリストの書式のコピーを作成して番号付けを再開する必要があります。
List list2 = doc.Lists.AddCopy(list1);

//新しい開始番号の設定を含め、新しいリストを任意の方法で変更できます。
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

 A: Aspose.Wordsでリストの番号付けを再開するには、`ListRestartAtNumber`方法の`List`クラス。このメソッドを使用すると、リストを再開する新しいダイヤル値を設定できます。たとえば、次のように使用できます。`list.ListRestartAtNumber(1)`番号を 1 からやり直します。

#### Q: Aspose.Words で再開されたリスト番号のプレフィックスとサフィックスをカスタマイズすることは可能ですか?

 A: はい、Aspose.Wordsでは、リスト番号の先頭と末尾をカスタマイズできます。`ListLevel`クラスは次のような特性を提供する`ListLevel.NumberPrefix`そして`ListLevel.NumberSuffix`リスト内の各レベルのプレフィックスとサフィックスを指定できます。これらのプロパティを使用して、必要に応じてプレフィックスとサフィックスをカスタマイズできます。

#### Q: リストを再開する特定の番号値を指定するにはどうすればよいですか?

 A: リストを再開する特定の数値を指定するには、`ListRestartAtNumber`メソッドは、希望する値を引数として渡します。例えば、5から番号を振り直すには、次のようにします。`list.ListRestartAtNumber(5)`.

#### Q: Aspose.Words で複数レベルのリストの番号付けを再開することは可能ですか?

 A: はい、Aspose.Wordsは複数のリストレベルの番号付けの再開をサポートしています。`ListRestartAtNumber`メソッドを使用して、リストの各レベルで個別に番号付けを再開できます。たとえば、`list.Levels[0].ListRestartAtNumber(1)`最初のリストレベルを1から再開し、`list.Levels[1].ListRestartAtNumber(1)` 2 番目のレベルのリストを 1 から再開します。



