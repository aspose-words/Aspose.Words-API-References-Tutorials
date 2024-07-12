---
title: 差し込みフィールドの名前を変更する
linktitle: 差し込みフィールドの名前を変更する
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント内の結合フィールドの名前を変更する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/rename-merge-fields/
---

ここでは、Aspose.Words for .NET の結合フィールドの名前変更機能を使用する C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各ステップを慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを作成し、差し込みフィールドを挿入する

まず、新しいドキュメントを作成し、`DocumentBuilder`差し込みフィールドを挿入します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## ステップ3: マージフィールドの名前を変更する

ドキュメント範囲内の各フィールドをループし、マージフィールドの場合は「_「名前を変更しました」サフィックス。

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## ステップ4: ドキュメントを保存する

最後に、`Save()`変更されたドキュメントを保存する方法。

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Aspose.Words for .NET を使用してマージ フィールドの名前を変更するためのソース コード例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、差し込みフィールドを挿入します。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

//マージフィールドの名前を変更します。
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

//ドキュメントを保存します。
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Aspose.Words for .NET を使用してドキュメント内の結合フィールドの名前を変更するには、次の手順に従います。

### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書内の結合フィールドの名前を変更するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してWord文書内の結合フィールドの名前を変更するには、`FieldMergingArgs`クラスと使用`FieldMergingArgs.FieldName`フィールドの名前を変更するメソッド。

#### Q: Aspose.Words for .NET を使用して、Word 文書内の特定の結合フィールドの名前のみを変更することは可能ですか?

A: はい、Aspose.Words for .NETではWord文書内の特定の結合フィールドのみの名前を変更することができます。フィールド名やその他の関連プロパティなどの特定の条件を使用して、名前を変更するフィールドをフィルタリングできます。次に、`FieldMergingArgs.FieldName`方法。

#### Q: Aspose.Words for .NET を使用して Word 文書内の結合フィールドの名前が正常に変更されたかどうかを確認するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してWord文書内の結合フィールドの名前が正常に変更されたかどうかを確認するには、`FieldMergedArgs`クラスにアクセスして`FieldMergedArgs.IsMerged`フィールドがヒットで名前変更されたかどうかを判断するプロパティ。

#### Q: Aspose.Words for .NET を使用して Word 文書内の結合フィールドの名前を変更すると、どのような結果になりますか?

A: Aspose.Words for .NET を使用して Word 文書内の結合フィールドの名前を変更すると、文書内のフィールド名が変更され、フィールド名に依存する他の機能やプロセスに影響する可能性があります。結合フィールドの名前を変更する前に、これらの潜在的な結果を必ず考慮してください。

#### Q: Aspose.Words for .NET で名前を変更した後、結合フィールドの元の名前を復元することは可能ですか?

A: はい、Aspose.Words for .NET で名前を変更した後、結合されたフィールドの元の名前を復元することは可能です。フィールドの元の名前を変数またはリストに保存し、必要に応じてその情報を使用して元の名前を復元できます。