---
title: インラインコード
linktitle: インラインコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してコードをインライン化する方法を学ぶステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-markdown/inline-code/
---

この例では、Aspose.Words for .NET でインライン コード機能を使用する方法について説明します。インライン コードは、段落内のコード部分を視覚的に表現するために使用されます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: インラインコードにスタイルを追加する

インラインコードにカスタムスタイルを追加するには、`Styles.Add`方法の`Document`オブジェクト。この例では、デフォルトのバックティックを持つインライン コード用の「InlineCode」というスタイルを作成しています。

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## ステップ3: インラインコードを追加する

これで、「InlineCode」カスタム スタイルを使用してインライン コードを追加できます。この例では、バックティックの数が異なる 2 つのテキストを追加します。

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Aspose.Words for .NET を使用したインライン コードのサンプル ソース コード

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//バックティックの数が不足しています。デフォルトでは 1 つのバックティックが使用されます。
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

//バックティックは 3 つあります。
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

おめでとうございます。これで、Aspose.Words for .NET でインライン コード機能を使用する方法を学習しました。


### よくある質問

#### Q: Aspose.Words でインライン コードを使用するにはどうすればよいですか?

 A: Aspose.Wordsでインラインコードを使用するには、適切なタグを使用して、インラインコードとして書式設定するテキストを囲みます。たとえば、`<code>`または`<kbd>`インライン コードとしてフォーマットされるテキストを囲むタグ。

#### Q: Aspose.Words でインライン コードのフォントや色を指定することは可能ですか?

 A: はい、Aspose.Wordsではインラインコードのフォントや色を指定できます。`Font.Name`そして`Font.Color`の特性`Run`オブジェクトを使用してインラインコードのフォントと色を設定できます。たとえば、`run.Font.Name = "Courier New"`インラインコードのフォントを指定するには`run.Font.Color = Color.Blue`色を指定します。

#### Q: 他のテキスト要素を含む段落でインライン コードを使用できますか?

 A: はい、他のテキスト要素を含む段落内でインラインコードを使用できます。複数の`Run`オブジェクトを使用して段落のさまざまな部分を表すには、インラインコードタグを使用して特定の部分のみをインラインコードとしてフォーマットします。その後、`Paragraph.AppendChild(run)`方法。