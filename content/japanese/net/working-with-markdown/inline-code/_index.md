---
title: インラインコード
linktitle: インラインコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドを使用してコードをインライン化する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/inline-code/
---

この例では、Aspose.Words for .NET でインライン コード機能を使用する方法を説明します。インライン コードは、段落内のコード部分を視覚的に表現するために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: インライン コードのスタイルを追加する

を使用してインライン コードのカスタム スタイルを追加します。`Styles.Add`の方法`Document`物体。この例では、デフォルトのバッククォートを使用してインライン コード用に「InlineCode」というスタイルを作成します。

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## ステップ 3: インラインコードを追加する

これで、「InlineCode」カスタム スタイルを使用してインライン コードを追加できるようになりました。この例では、バッククォートの数が異なる 2 つのテキストを追加します。

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Aspose.Words for .NET を使用したインライン コードのソース コード例

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//バッククォートの数が欠落しています。デフォルトでは 1 つのバッククォートが使用されます。
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

//バッククォートが 3 つになります。
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

おめでとうございます！これで、Aspose.Words for .NET でインライン コード機能を使用する方法を学習しました。


### よくある質問

#### Q: Aspose.Words でインライン コードを使用するにはどうすればよいですか?

 A: Aspose.Words でインライン コードを使用するには、適切なタグを使用して、インライン コードとして書式設定されるテキストを囲みます。たとえば、次のように使用できます。`<code>`または`<kbd>`タグを使用して、インライン コードとして書式設定されるテキストを囲みます。

#### Q: Aspose.Words でインライン コードのフォントや色を指定することはできますか?

 A: はい、Aspose.Words でインライン コードのフォントまたは色を指定できます。使用できます`Font.Name`そして`Font.Color`のプロパティ`Run`インラインコードのフォントと色を設定するオブジェクト。たとえば、次のように使用できます`run.Font.Name = "Courier New"`インラインコードのフォントを指定し、`run.Font.Color = Color.Blue`色を指定します。

#### Q: 他のテキスト要素を含む段落でインライン コードを使用できますか?

 A: はい、他のテキスト要素を含む段落でインライン コードを使用できます。複数作成できます`Run`オブジェクトを使用して段落のさまざまな部分を表現し、インライン コード タグを使用して特定の部分のみをインライン コードとして書式設定します。次に、を使用してそれらを段落に追加できます。`Paragraph.AppendChild(run)`方法。