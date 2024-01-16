---
title: Word文書の差し込みフィールドに移動
linktitle: Word文書の差し込みフィールドに移動
second_title: Aspose.Words ドキュメント処理 API
description: ステップバイステップのガイドを使用して、Aspose.Words for .NET の Word 文書に差し込みフィールドに移動機能を実装する方法を学びます。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/move-to-merge-field/
---
この例では、Aspose.Words for .NET の Word ドキュメントの差し込みフィールドに移動機能を調べます。 Aspose.Words は、開発者が Word ドキュメントをプログラムで作成、変更、変換できるようにする強力なドキュメント操作ライブラリです。差し込みフィールドに移動機能を使用すると、ドキュメント内の差し込みフィールドに移動し、フィールド上でさまざまな操作を実行できます。


## ソースコードをステップバイステップで解説

Aspose.Words for .NET を使用して差し込みフィールドに移動機能を使用する方法を理解するために、ソース コードを段階的に見てみましょう。

## ステップ 1: ドキュメントとドキュメント ビルダーの初期化

まず、Document オブジェクトと DocumentBuilder オブジェクトを初期化します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2 差し込みフィールドを挿入し、その後にテキストを追加する

DocumentBuilder クラスの InsertField メソッドを使用して差し込みフィールドを挿入し、その後にテキストを追加します。

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## ステップ 3: ビルダーのカーソルは現在ドキュメントの末尾にあります。

```csharp
Assert.Null(builder.CurrentNode);
```
## ステップ 4: ドキュメントビルダーのカーソルを差し込みフィールドに移動する

ドキュメント ビルダーのカーソルを差し込みフィールドに移動するには、DocumentBuilder クラスの MoveToField メソッドを使用します。

```csharp
builder.MoveToField(field, true);
```

## 差し込みフィールドの直後にテキストを追加する

ドキュメント ビルダーのカーソルが差し込みフィールド内にあると、Write メソッドを使用して直後にテキストを追加できます。

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Aspose.Words for .NET を使用した差し込みフィールドに移動のソース コードの例

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//DocumentBuilder を使用してフィールドを挿入し、その後に一連のテキストを追加します。
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

//ビルダーのカーソルは現在ドキュメントの末尾にあります。
Assert.Null(builder.CurrentNode);
//このようにビルダーをフィールドに移動し、フィールドの直後にカーソルを置きます。
builder.MoveToField(field, true);

//カーソルはフィールドの FieldEnd ノードを超えた場所にあることに注意してください。これは、実際にはフィールド内にいないことを意味します。
// DocumentBuilder をフィールド内に移動したい場合は、
// DocumentBuilder.MoveTo() メソッドを使用して、フィールドの FieldStart ノードまたは FieldSeparator ノードに移動する必要があります。
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## 結論

Aspose.Words for .NET の差し込みフィールドに移動機能を調べました。 DocumentBuilder クラスを使用してドキュメント内のフィールドを結合し、それらのフィールドに対して操作を実行するように移動する方法を学習しました。この機能は、マージを使用してプログラムでワード処理を行う場合に便利です。

### Word 文書の差し込みフィールドへの移動に関する FAQ

#### Q: Aspose.Words for .NET の差し込みフィールドに移動機能の目的は何ですか?

A: Aspose.Words for .NET の差し込みフィールドへの移動機能を使用すると、開発者は Word 文書内の差し込みフィールドに移動し、プログラムでさまざまな操作を実行できます。差し込みフィールドは、差し込み印刷操作のために Word 文書で使用される特別なプレースホルダーです。

#### Q: Aspose.Words for .NET を使用して Word 文書に差し込みフィールドを挿入するにはどうすればよいですか?

A: DocumentBuilder クラスの InsertField メソッドを使用して、差し込みフィールドを文書に挿入できます。差し込みフィールドを挿入した後、Write メソッドを使用してフィールドの前後にテキストなどのコンテンツを追加できます。

#### Q: ドキュメントビルダーのカーソルを特定の差し込みフィールドに移動するにはどうすればよいですか?

A: ドキュメント ビルダー カーソルを特定の差し込みフィールドに移動するには、DocumentBuilder クラスの MoveToField メソッドを使用し、フィールドをパラメータとして渡します。これにより、カーソルが差し込みフィールドの直後に配置されます。

#### Q: 差し込みフィールドに移動機能を使用して、差し込みフィールド内にテキストを追加できますか?

A: いいえ、差し込みフィールドへ移動機能では、ドキュメント ビルダー カーソルが差し込みフィールドの直後に配置されます。差し込みフィールド内にテキストを追加するには、DocumentBuilder.MoveTo メソッドを使用してカーソルを差し込みフィールドの FieldStart ノードまたは FieldSeparator ノードに移動します。

#### Q: Aspose.Words for .NET を使用して差し込み印刷操作を実行するにはどうすればよいですか?

A: Aspose.Words for .NET は、差し込み印刷操作の広範なサポートを提供します。 MailMerge クラスを使用すると、配列、データセット、カスタム データ ソースなどのさまざまなソースからのデータを使用して差し込み印刷を実行できます。