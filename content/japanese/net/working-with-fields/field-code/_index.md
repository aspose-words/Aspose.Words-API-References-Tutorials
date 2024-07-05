---
title: フィールドコード
linktitle: フィールドコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のフィールド コードとフィールド結果を取得するためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-fields/field-code/
---

ここでは、Aspose.Words for .NET の「フィールド コードの取得」機能を使用する以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。目的の結果を得るには、各手順を慎重に実行してください。

## ステップ1: ドキュメントディレクトリの設定

提供されたコードでは、ドキュメントのディレクトリを指定する必要があります。値「YOUR DOCUMENT DIRECTORY」をドキュメント ディレクトリへの適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントの読み込み

最初のステップは、フィールド コードを取得するドキュメントをアップロードすることです。

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

必ず「Hyperlinks.docx」を自分のファイル名に置き換えてください。

## ステップ3: ドキュメントフィールドを参照する

私たちは`foreach`loop を実行して、ドキュメント内に存在するすべてのフィールドをループします。

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

ループの各反復で、フィールドコードを取得します。`GetFieldCode()`メソッド。フィールドの結果も変数に格納します。

### Aspose.Words for .NET でフィールド コードを取得するためのソース コード例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込みます。
Document doc = new Document(dataDir + "Hyperlinks.docx");

//ドキュメント フィールドをループします。
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     //フィールドのコードと結果を使用して何かを実行します。
}
```

この例では、ドキュメントをロードし、ドキュメント内に存在するすべてのフィールドを循環処理しました。各反復処理で、フィールドのコードと結果を取得しました。必要に応じて、コードと結果フィールドを処理する独自のロジックを追加できます。

これで、Aspose.Words for .NET の「フィールド コードの取得」機能の使用に関するガイドは終了です。

### よくある質問

#### Q: Aspose.Words for .NET を使用して Word 文書にフィールドを挿入するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してWord文書にフィールドを挿入するには、`DocumentBuilder.InsertField`適切なフィールドコードを指定する方法。たとえば、`builder.InsertField("MERGEFIELD CustomerName")`文書に差し込みフィールドを挿入します。

#### Q: Aspose.Words for .NET を使用してドキュメント内のフィールドを更新するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してドキュメントフィールドを更新するには、`Document.UpdateFields`メソッド。これにより、マージ フィールド、日付フィールドなど、ドキュメント内に存在するすべてのフィールドが更新されます。

#### Q: Aspose.Words for .NET で特定のフィールドの値を取得するにはどうすればよいですか?

 A: Aspose.Words for .NETの特定のフィールドの値を取得するには、`Field.GetResult`フィールドのインデックスを指定することで`Document.Range.Fields`コレクション。例えば、`string value = document.Range.Fields[0].GetResult()`ドキュメントの最初のフィールドの値を取得します。

#### Q: Aspose.Words for .NET を使用してドキュメントからフィールドを削除するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してドキュメントからフィールドを削除するには、`Field.Remove`指定方法`Field`削除するオブジェクトを選択します。これにより、ドキュメントからフィールドが削除されます。