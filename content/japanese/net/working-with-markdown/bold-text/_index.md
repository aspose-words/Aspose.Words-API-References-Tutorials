---
title: 太字
linktitle: 太字
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してテキストを太字にする方法をステップバイステップで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/bold-text/
---

この例では、Aspose.Words for .NET を使用してテキストを太字にする方法を説明します。テキストを太字にすると、テキストがより目立つようになり、目立つようになります。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: 太字テキスト

ドキュメントビルダーの`Font.Bold`財産に`true`.

```csharp
builder.Font.Bold = true;
```

## ステップ3: ドキュメントにコンテンツを追加する

ドキュメントビルダーメソッドを使用して、ドキュメントにコンテンツを追加できるようになりました。`Writeln`、テキスト行を追加します。

```csharp
builder.Writeln("This text will be bold");
```

## Aspose.Words for .NET を使用した太字テキストのサンプル ソース コード


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//テキストを太字にします。
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

おめでとうございます！Aspose.Words for .NET を使用してテキストを太字にする方法を学習しました。


### よくある質問

#### Q: Aspose.Words でテキストを太字にするにはどうすればいいですか?

 A: Aspose.Wordsでテキストを太字にするには、`Font.Bold`の財産`Run`オブジェクト。このプロパティは次のように設定できます。`true`特定のテキストを太字にするには、例えば`run.Font.Bold=true`内のテキストを太字にする`Run`物体。

#### Q: 同じ段落内の複数のテキストを太字にすることはできますか?

 A: はい、複数のテキストを1つの段落内で太字にすることができます。`Run`オブジェクトを複数作成できます`Run`オブジェクトを設定し、`Font.Bold`財産に`true`各オブジェクトでテキストの必要な部分を太字にすることができます。その後、`Paragraph.AppendChild(run)`方法。

#### Q: Aspose.Words の表またはセル内のテキストを太字にできますか?

 A: はい、Aspose.Wordsでは表やセル内のテキストを太字にすることができます。適切な方法で目的のセルまたは段落に移動し、`Font.Bold`の財産`Run`または`Paragraph`物体。