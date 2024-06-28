---
title: 取り消し線
linktitle: 取り消し線
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドで取り消し線テキスト スタイルを適用する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/strikethrough/
---


この例では、Aspose.Words for .NET を使用して取り消し線のテキスト スタイルを適用する方法を説明します。取り消し線のテキストは、テキストが削除されたか、無効になったことを示すために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: 取り消し線のテキスト スタイルを適用する

を設定することで取り消し線のテキスト スタイルを有効にします。`StrikeThrough`の財産`Font`に反対する`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## ステップ 3: 取り消し線テキストを追加する

ドキュメントジェネレーターを使用して取り消し線テキストを追加できるようになりました。`Writeln`方法。

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Aspose.Words for .NET を使用した取り消し線テキストのソース コードの例

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//テキストに取り消し線を付けます。
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

おめでとうございます！ Aspose.Words for .NET を使用して取り消し線のテキスト スタイルを適用する方法を学習しました。

### よくある質問

#### Q: Aspose.Words に取り消し線テキストを追加するにはどうすればよいですか?

 A: Aspose.Words に取り消し線テキストを追加するには、`Font.StrikeThrough`の財産`Run`物体。このプロパティを次のように設定できます`true`特定のテキストに取り消し線のテキストを追加します。たとえば、次のように使用できます`run.Font.StrikeThrough=true`に取り消し線のテキストを追加するには、`Run`物体。

#### Q: 同じ段落内の複数のテキストに取り消し線を追加することはできますか?

 A: はい、複数を使用することで、単一段落内のテキストの複数の部分に取り消し線テキストを追加できます。`Run`オブジェクト。複数作成できます`Run`オブジェクトを設定し、`Font.StrikeThrough`財産を`true`オブジェクトごとに、必要なテキスト部分に取り消し線のテキストを追加します。次に、を使用してそれらを段落に追加できます。`Paragraph.AppendChild(run)`方法。

#### Q: Aspose.Words のテーブルまたはセル内のテキストに取り消し線のテキストを追加できますか?

 A: はい、Aspose.Words のテーブルまたはセル内のテキストに取り消し線のテキストを追加できます。適切な方法を使用して目的のセルまたは段落にジャンプし、次に、取り消し線のテキスト書式設定を適用できます。`Font.StrikeThrough`の財産`Run`または`Paragraph`物体。