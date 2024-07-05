---
title: フォームフィールドを名前で取得
linktitle: フォームフィールドを名前で取得
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のフォーム フィールドを名前で取得および変更する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-formfields/form-fields-get-by-name/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET を使用して Word 文書から名前でフォーム フィールドを取得する方法について説明します。提供されている C# ソース コードについて説明し、独自のプロジェクトに実装する方法を示します。

始めるには、開発環境にAspose.Words for .NETがインストールされ、設定されていることを確認してください。まだインストールされていない場合は、次の場所からライブラリをダウンロードしてインストールしてください。[Aspose.Releases]https://releases.aspose.com/words/net/.

## ステップ1: ドキュメントオブジェクトの初期化

まず、`Document`フォーム フィールドを含むソース ドキュメントへのパスを指定してオブジェクトを作成します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## ステップ2: フォームフィールドの取得

次に、`FormFields`の財産`Range`ドキュメント内のすべてのフォーム フィールドを取得するには、次のオブジェクトを使用します。

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

フォーム フィールドは、インデックスまたは名前で取得できます。この例では、両方の方法を使用してフォーム フィールドを取得します。

```csharp
FormField formField1 = documentFormFields[3]; //インデックスによる取得
FormField formField2 = documentFormFields["Text2"]; //名前で検索
```

## ステップ3: フォームフィールドのプロパティを変更する

フォームフィールドを取得したら、必要に応じてプロパティを変更できます。この例では、`formField1` 20とフォントの色`formField2`赤に:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## ステップ4: ドキュメントを保存する

最後に、変更したドキュメントを保存します。

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内のフォーム フィールドを名前で取得し、そのプロパティを変更することができました。

### Aspose.Words for .NET を使用して名前でフォーム フィールドを取得するためのサンプル ソース コード

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

 A: Aspose.Wordsでフォームフィールドを名前で取得するには、`Document.Range.FormFields[name]`メソッド。このメソッドは、指定された名前に対応するフォーム フィールドを返します。

#### Q: 指定された名前のフォーム フィールドがドキュメント内に存在しない場合はどうなりますか?

 A: 指定された名前のフォームフィールドが文書内に存在しない場合、`Document.Range.FormFields[name]`メソッドは戻ります`null`この結果をチェックすることで、フォーム フィールドが見つからないケースを処理できます。

#### Q: 見つかったフォーム フィールドのプロパティを変更するにはどうすればよいですか?

A: フォーム フィールドを名前で取得すると、その個々のプロパティにアクセスして編集できます。たとえば、フィールドの値を変更したり、フィールドの表示を有効または無効にしたり、必要に応じて他のプロパティを変更したりできます。

#### Q: ドキュメント内に同じ名前のフォーム フィールドを複数取得できますか?

 A: はい、文書内に同じ名前のフォームフィールドを複数持つことは可能です。この場合、`Document.Range.FormFields[name]`メソッドは、指定された名前で見つかった最初のフォーム フィールドを返します。同じ名前のフォーム フィールドが複数ある場合は、フィールドを操作するときにこれを考慮する必要があります。

#### Q: ドキュメント内のすべてのフォーム フィールドを反復処理するにはどうすればよいですか?

 A: 文書内のすべてのフォームフィールドを反復処理するには、`foreach`ループオン`Document.Range.FormFields`コレクション。これにより、各フォーム フィールドに個別にアクセスし、それぞれに対して操作を実行できるようになります。