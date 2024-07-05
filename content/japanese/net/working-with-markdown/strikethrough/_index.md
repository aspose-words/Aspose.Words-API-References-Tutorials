---
title: 取り消し線
linktitle: 取り消し線
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して取り消し線テキスト スタイルを適用する方法をステップ バイ ステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/strikethrough/
---


この例では、Aspose.Words for .NET を使用して取り消し線テキスト スタイルを適用する方法について説明します。取り消し線テキストは、テキストが削除されたか、無効になったことを示すために使用されます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: 取り消し線テキストスタイルを適用する

取り消し線テキストスタイルを有効にするには、`StrikeThrough`の財産`Font`反対する`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## ステップ3: 取り消し線テキストを追加する

ドキュメントジェネレーターの`Writeln`方法。

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Aspose.Words for .NET を使用した取り消し線テキストのサンプル ソース コード

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//テキストに取り消し線を付けます。
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

おめでとうございます！これで、Aspose.Words for .NET を使用して取り消し線テキスト スタイルを適用する方法を学習しました。

### よくある質問

#### Q: Aspose.Words で取り消し線テキストを追加するにはどうすればよいですか?

 A: Aspose.Wordsで取り消し線テキストを追加するには、`Font.StrikeThrough`の財産`Run`オブジェクト。このプロパティは次のように設定できます。`true`特定のテキストに取り消し線を追加するには、例えば`run.Font.StrikeThrough=true`取り消し線テキストを追加するには`Run`物体。

#### Q: 同じ段落内の複数のテキストに取り消し線テキストを追加することは可能ですか?

 A: はい、複数のツールを使って、1つの段落内の複数のテキスト部分に取り消し線を追加できます。`Run`オブジェクトを複数作成できます`Run`オブジェクトを設定し、`Font.StrikeThrough`財産に`true`各オブジェクトに対して、取り消し線テキストを任意のテキスト部分に追加します。その後、`Paragraph.AppendChild(run)`方法。

#### Q: Aspose.Words の表またはセル内のテキストに取り消し線テキストを追加できますか?

 A: はい、Aspose.Wordsの表やセル内のテキストに取り消し線を追加できます。適切な方法を使用して目的のセルまたは段落にジャンプし、`Font.StrikeThrough`の財産`Run`または`Paragraph`物体。