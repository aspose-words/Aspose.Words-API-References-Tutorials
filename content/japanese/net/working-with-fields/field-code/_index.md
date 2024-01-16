---
title: フィールドコード
linktitle: フィールドコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のフィールド コードとフィールド結果を取得するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fields/field-code/
---

ここでは、Aspose.Words for .NET の「フィールド コードの取得」機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。望ましい結果を得るために、各ステップを慎重に実行してください。

## ステップ 1: ドキュメント ディレクトリのセットアップ

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。 「YOUR DOCUMENT DIRECTORY」という値を、ドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントをロードする

最初のステップは、フィールド コードを取得するドキュメントをアップロードすることです。

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

必ず「Hyperlinks.docx」を独自のファイル名に置き換えてください。

## ステップ 3: ドキュメントフィールドを参照する

私たちは、`foreach`ドキュメント内に存在するすべてのフィールドをループします。

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

ループの各反復で、次を使用してフィールド コードを取得します。`GetFieldCode()`方法。フィールドの結果も変数に保存します。

### Aspose.Words for .NET を使用してフィールド コードを取得するソース コードの例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします。
Document doc = new Document(dataDir + "Hyperlinks.docx");

//ドキュメントフィールドをループします。
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     //フィールドのコードと結果を使用して何らかの処理を行います。
}
```

この例では、ドキュメントをロードし、ドキュメント内に存在するすべてのフィールドを循環的に処理しました。各反復で、フィールドのコードと結果を取得しました。必要に応じて、コードと結果フィールドを処理する独自のロジックを追加できます。

これで、Aspose.Words for .NET での「フィールド コードの取得」機能の使用に関するガイドは終わりです。

### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書にフィールドを挿入するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して Word 文書にフィールドを挿入するには、`DocumentBuilder.InsertField`メソッドで適切なフィールド コードを指定します。たとえば、次のように使用できます`builder.InsertField("MERGEFIELD CustomerName")`文書に差し込みフィールドを挿入します。

#### Q: Aspose.Words for .NET を使用してドキュメント内のフィールドを更新するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してドキュメント フィールドを更新するには、`Document.UpdateFields`方法。これにより、差し込みフィールドや日付フィールドなど、ドキュメント内に存在するすべてのフィールドが更新されます。

#### Q: Aspose.Words for .NET の特定のフィールドの値を取得するにはどうすればよいですか?

 A: Aspose.Words for .NET の特定のフィールドの値を取得するには、`Field.GetResult`フィールドのインデックスを指定してメソッドを実行します。`Document.Range.Fields`コレクション。たとえば、次のように使用できます`string value = document.Range.Fields[0].GetResult()`ドキュメントの最初のフィールドの値を取得します。

#### Q: Aspose.Words for .NET を使用してドキュメントからフィールドを削除するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してドキュメントからフィールドを削除するには、`Field.Remove`を指定するメソッド`Field`削除したいオブジェクト。これにより、ドキュメントからフィールドが削除されます。