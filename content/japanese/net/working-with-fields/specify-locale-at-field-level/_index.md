---
title: フィールドレベルでロケールを指定する
linktitle: フィールドレベルでロケールを指定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書でフィールド レベルのローカリゼーションを指定する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fields/specify-locale-at-field-level/
---

ここでは、Aspose.Words for .NET 機能を使用してフィールド レベルでローカリゼーションを指定できるようにする次の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。このコードを使用する前に、プロジェクトに Aspose.Words ライブラリが含まれていることを確認してください。

## ステップ1: ドキュメントディレクトリのパスを設定する

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

編集したドキュメントが保存されるドキュメント ディレクトリへの正しいパスを必ず指定してください。

## ステップ2: ドキュメントジェネレータを作成する

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

ここでは、`DocumentBuilder`ドキュメントにフィールドを追加できるクラスです。

## ステップ3: 特定の場所の日付フィールドを挿入する

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

ドキュメントジェネレータを使用して、次のタイプのフィールドを挿入します。`FieldType.FieldDate`文書に挿入します。`LocaleId`財産に`1049`、このフィールドにロシア語のローカライズを指定します。

## ステップ4: 変更したドキュメントを保存する

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

最後に、変更されたドキュメントを指定された場所に指定されたファイルに保存します。

### Aspose.Words for .NET でフィールド レベルのローカリゼーションを指定するためのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

これは、Aspose.Words for .NET を使用してドキュメント内のフィールド レベルでローカリゼーションを指定するためのサンプル ソース コードです。このコードを使用して、Word ドキュメントに特定の場所の日付フィールドを挿入できます。

### よくある質問

#### Q: Aspose.Words for .NET でフィールド レベルのロケールを指定するにはどうすればよいですか?

 A: Aspose.Words for .NETでフィールドレベルでロケールを指定するには、`FieldOptions`クラスとその`FieldLocale`プロパティを使用して、希望するロケールを設定します。たとえば、`FieldOptions.FieldLocale = new CultureInfo("fr-FR")`フランス語 (フランス) ロケールを指定します。

#### Q: Aspose.Words for .NET の各フィールドに異なるロケールを指定することは可能ですか?

 A: はい、Aspose.Words for .NETの各フィールドに異なるロケールを指定することができます。`FieldOptions.FieldLocale`特定のフィールドを作成または更新する前に、プロパティを変更して別のロケールを割り当てます。

#### Q: Aspose.Words for .NET のフィールドで現在使用されているロケールを取得するにはどうすればよいですか?

 A: Aspose.Words for .NETのフィールドで現在使用されているロケールを取得するには、フィールドの`Field.LocaleId`プロパティ。これにより、フィールドに関連付けられたロケール識別子を取得できます。