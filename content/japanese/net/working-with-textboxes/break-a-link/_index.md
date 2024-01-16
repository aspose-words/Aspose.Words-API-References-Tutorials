---
title: Word 文書内の転送リンクを解除する
linktitle: Word 文書内の転送リンクを解除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の前方リンクを解除する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET は、Microsoft Word ドキュメントをプログラム的にワード処理するためのさまざまな機能を提供する強力なライブラリです。その便利な機能の 1 つは、Word 文書内の前方リンクを解除する機能です。このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内で前方リンクを解除する方法を示す C# のソース コードを調べます。

## ステップ 1: C# ソース コードのプレビュー

提供されている C# ソース コードは、Aspose.Words for .NET の「リンクの解除」機能に重点を置いています。ドキュメント内の TextBox 図形内のリンクを解除する方法を示します。このコードは、リンクを切断するためのさまざまなシナリオを示し、望ましい結果を達成する方法について明確な指示を提供します。

## ステップ 2: ドキュメントを設定し、TextBox 図形を作成する

まず、ドキュメントを設定し、TextBox 図形を作成する必要があります。次のコードは、`Document`クラスを作成し、テキスト ボックスの形状を作成します。

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## ステップ 3: TextBox で転送リンクを解除する

TextBox 内のフォワードリンクを解除するには、`BreakForwardLink()`方法。このメソッドは、シーケンス内の次のシェイプへのリンクを切断します。次のコードは、前方リンクを解除する方法を示しています。

```csharp
textBox.BreakForwardLink();
```

## ステップ 4: null 値を設定して順方向リンクを切断する

あるいは、TextBox の設定によって前方リンクを解除することもできます。`Next`財産を`null`。これにより、次の形状への接続が効果的に削除されます。次のコードは、このアプローチを示しています。

```csharp
textBox. Next = null;
```

## ステップ 5: TextBox へのリンクを解除する

場合によっては、TextBox 図形につながるリンクを解除する必要があります。これを呼び出すことでこれを実現できます。`BreakForwardLink()`のメソッド`Previous`これにより、TextBox へのリンクが切断されます。このようなリンクを解除する方法の例を次に示します。

```csharp
textBox.Previous?.BreakForwardLink();
```

### Aspose.Words for .NET とのリンクを解除するためのサンプル ソース コード

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

//前方リンクを解除します。
textBox.BreakForwardLink();

// null 値を設定して、順方向リンクを切断します。
textBox. Next = null;

//このテキスト ボックスへのリンクを解除します。
textBox.Previous?.BreakForwardLink();
```

## 結論

おめでとうございます！これで、.NET 用の Aspose.Words ライブラリを使用して Word 文書内のリダイレクト リンクを解除する方法を学習しました。このガイドの手順に従うことで、さまざまな方法を使用してドキュメントを設定し、TextBox 図形を作成し、リダイレクト リンクを解除することができました。

### Word 文書内のブレークフォワードリンクに関する FAQ

#### Q: Aspose.Words for .NET を使用して Word 文書内のリダイレクト リンクを解除するために使用されるライブラリは何ですか?

A: Aspose.Words for .NET を使用して Word 文書内のリダイレクト リンクを解除するには、Aspose.Words for .NET のライブラリが使用されます。

#### Q: TextBox 内のリダイレクト リンクを解除するにはどうすればよいですか?

 A: TextBox 内のフォワードリンクを解除するには、`BreakForwardLink()`方法。このメソッドは、シーケンス内の次のシェイプへのリンクを切断します。

#### Q: null 値を設定してリダイレクト リンクを解除するにはどうすればよいですか?

A: または、次のように設定してリダイレクト リンクを解除することもできます。`Next` TextBox のプロパティを`null`。これにより、次の形状への接続が効果的に削除されます。

#### Q: TextBox へのリンクを解除するにはどうすればよいですか?

 A: 場合によっては、TextBox へのリンクを解除する必要があります。これを実現するには、`BreakForwardLink()`のメソッド`Previous`これにより、TextBox へのリンクが切断されます。

#### Q: TextBox 以外の要素のリダイレクト リンクを解除できますか?

A: はい、Aspose.Words for .NET を使用すると、段落、表、画像などのさまざまな要素のリダイレクト リンクを解除できます。プロセスは、リンクを解除する特定の項目によって異なる場合があります。