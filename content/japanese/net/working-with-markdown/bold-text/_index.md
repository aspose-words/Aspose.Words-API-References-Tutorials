---
title: 太字
linktitle: 太字
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドを使用してテキストを太字にする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/bold-text/
---

この例では、Aspose.Words for .NET を使用してテキストを太字にする方法を説明します。テキストを太字にすると、より目立つようになり、より目立つようになります。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: 太字のテキスト

ドキュメントビルダーの設定によりテキストを太字にすることができます。`Font.Bold`財産を`true`.

```csharp
builder.Font.Bold = true;
```

## ステップ 3: ドキュメントにコンテンツを追加する

これで、次のようなドキュメント ビルダー メソッドを使用してドキュメントにコンテンツを追加できるようになります。`Writeln`、テキスト行を追加します。

```csharp
builder.Writeln("This text will be bold");
```

## Aspose.Words for .NET を使用した太字のソース コードの例


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//テキストを太字にします。
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

おめでとうございます！ Aspose.Words for .NET を使用してテキストを太字にする方法を学習しました。


### よくある質問

#### Q: Aspose.Words でテキストを太字にするにはどうすればよいですか?

 A: Aspose.Words でテキストを太字にするには、`Font.Bold`の財産`Run`物体。このプロパティを次のように設定できます`true`特定のテキストを太字にします。たとえば、次のように使用できます`run.Font.Bold=true`内のテキストを太字にするには`Run`物体。

#### Q: 同じ段落内の複数のテキストを太字にすることはできますか?

 A: はい、複数の文字列を使用して、1 つの段落内の複数のテキストを太字にすることができます。`Run`オブジェクト。複数作成できます`Run`オブジェクトを設定し、`Font.Bold`財産を`true`オブジェクトごとに、テキストの必要な部分を太字にします。次に、を使用してそれらを段落に追加できます。`Paragraph.AppendChild(run)`方法。

#### Q: Aspose.Words のテーブルまたはセル内のテキストを太字にすることはできますか?

 A: はい、Aspose.Words のテーブルまたはセル内のテキストを太字にすることができます。適切な方法を使用して目的のセルまたは段落に移動し、`Font.Bold`の財産`Run`または`Paragraph`物体。