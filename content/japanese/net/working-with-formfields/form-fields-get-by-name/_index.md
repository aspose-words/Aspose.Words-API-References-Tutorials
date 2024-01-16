---
title: フォームフィールドを名前で取得
linktitle: フォームフィールドを名前で取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word ドキュメント内のフォーム フィールドを名前で取得および変更する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-formfields/form-fields-get-by-name/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書から名前でフォーム フィールドを取得する方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、Aspose.Words for .NET が開発環境にインストールされ、セットアップされていることを確認してください。まだ行っていない場合は、からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ドキュメント オブジェクトの初期化

まず、初期化します`Document`フォームフィールドを含むソースドキュメントへのパスを指定して、オブジェクトをオブジェクトに追加します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## ステップ 2: フォームフィールドの取得

次に、`FormFields`の財産`Range`ドキュメント内のオブジェクトを使用してすべてのフォームフィールドを取得します。

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

フォームフィールドはインデックスまたは名前で取得できます。この例では、両方のメソッドを使用してフォーム フィールドを取得します。

```csharp
FormField formField1 = documentFormFields[3]; //インデックスによる取得
FormField formField2 = documentFormFields["Text2"]; //名前で取得する
```

## ステップ 3: フォームフィールドのプロパティを変更する

フォームフィールドを取得したら、必要に応じてそのプロパティを変更できます。この例では、フォント サイズを変更します。`formField1`から 20 と文字の色`formField2`赤に:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## ステップ 4: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、フォーム フィールドを名前で取得し、Word 文書内のプロパティを変更することに成功しました。

### Aspose.Words for .NET を使用した名前によるフォーム フィールドの取得のソース コード例

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

このコードを独自のプロジェクトで自由に使用し、特定の要件に応じて変更してください。

### よくある質問

#### Q: Aspose.Words でフォーム フィールドを名前で取得するにはどうすればよいですか?

 A: Aspose.Words でフォーム フィールドを名前で取得するには、`Document.Range.FormFields[name]`方法。このメソッドは、指定された名前に対応するフォーム フィールドを返します。

#### Q: 指定された名前のフォーム フィールドがドキュメント内に存在しない場合はどうすればよいですか?

 A: 指定された名前のフォーム フィールドがドキュメント内に存在しない場合、`Document.Range.FormFields[name]`メソッドが戻ります`null`。この結果を確認して、フォーム フィールドが見つからない場合に対処できます。

#### Q: 見つかったフォームフィールドのプロパティを変更するにはどうすればよいですか?

A: フォーム フィールドを名前で取得したら、その個々のプロパティにアクセスして編集できます。たとえば、フィールドの値を変更したり、フィールドの表示を有効または無効にしたり、必要に応じて他のプロパティを変更したりできます。

#### Q: ドキュメント内で同じ名前の複数のフォーム フィールドを取得できますか?

 A: はい、ドキュメント内に同じ名前の複数のフォーム フィールドを含めることができます。この場合、`Document.Range.FormFields[name]`このメソッドは、指定された名前で最初に見つかったフォーム フィールドを返します。同じ名前のフォーム フィールドが複数ある場合は、フィールドを操作するときにこれを考慮する必要があります。

#### Q: ドキュメント内のすべてのフォームフィールドを反復処理するにはどうすればよいですか?

 A: ドキュメント内のすべてのフォーム フィールドを反復処理するには、`foreach`をループします`Document.Range.FormFields`コレクション。これにより、各フォームフィールドに個別にアクセスし、それぞれに対して操作を実行できるようになります。