---
title: フィールドレベルでロケールを指定する
linktitle: フィールドレベルでロケールを指定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントでフィールド レベルのローカリゼーションを指定する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fields/specify-locale-at-field-level/
---

ここでは、Aspose.Words for .NET 機能を使用してフィールド レベルでローカリゼーションを指定できる次の C# ソース コードを説明するステップバイステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ 1: ドキュメント ディレクトリ パスを設定する

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

編集したドキュメントが保存されるドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ 2: ドキュメント ジェネレーターを作成する

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

ここでは、`DocumentBuilder`このクラスを使用すると、ドキュメントにフィールドを追加できるようになります。

## ステップ 3: 特定の場所を含む日付フィールドを挿入する

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

ドキュメント ジェネレーターを使用して、次のタイプのフィールドを挿入します。`FieldType.FieldDate`文書に。を設定することで、`LocaleId`財産を`1049`では、このフィールドにロシア語のローカライズを指定します。

## ステップ 4: 変更したドキュメントを保存する

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

最後に、変更したドキュメントを指定した場所に指定したファイルに保存します。

### Aspose.Words for .NET でフィールド レベルのローカリゼーションを指定するためのサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

これは、Aspose.Words for .NET を使用してドキュメントのフィールド レベルでローカリゼーションを指定するソース コードの例でした。このコードを使用すると、Word 文書内の特定の場所に日付フィールドを挿入できます。

### よくある質問

#### Q: Aspose.Words for .NET でフィールド レベルのロケールを指定するにはどうすればよいですか?

 A: Aspose.Words for .NET のフィールド レベルでロケールを指定するには、`FieldOptions`クラスとその`FieldLocale`プロパティを使用して、必要なロケールを設定します。たとえば、次のように使用できます`FieldOptions.FieldLocale = new CultureInfo("fr-FR")`フランス語 (フランス) ロケールを指定します。

#### Q: Aspose.Words for .NET のフィールドごとに異なるロケールを指定することはできますか?

 A: はい、Aspose.Words for .NET のフィールドごとに異なるロケールを指定できます。使用できます`FieldOptions.FieldLocale`特定のフィールドを作成または更新する前にプロパティを使用して、別のロケールを割り当てます。

#### Q: Aspose.Words for .NET のフィールドで現在使用されているロケールを取得するにはどうすればよいですか?

 A: Aspose.Words for .NET のフィールドで現在使用されているロケールを取得するには、フィールドの`Field.LocaleId`財産。これにより、フィールドに関連付けられたロケール識別子を取得できるようになります。