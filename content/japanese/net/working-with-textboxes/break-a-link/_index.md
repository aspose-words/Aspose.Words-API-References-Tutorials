---
title: Word 文書の転送リンクを解除する
linktitle: Word 文書の転送リンクを解除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の転送リンクを解除する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET は、Microsoft Word 文書をプログラムで処理するためのさまざまな機能を提供する強力なライブラリです。その便利な機能の 1 つは、Word 文書内の前方リンクを解除できることです。このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の前方リンクを解除する方法を示す C# のソース コードについて説明します。

## ステップ 1: C# ソース コードのプレビュー

提供されている C# ソース コードは、Aspose.Words for .NET の「リンクの解除」機能に重点を置いています。ドキュメント内の TextBox 図形のリンクを解除する方法を示します。コードでは、リンクを解除するためのさまざまなシナリオを示し、目的の結果を達成するための明確な手順を示します。

## ステップ2: ドキュメントの設定とテキストボックス図形の作成

まず、ドキュメントをセットアップしてTextBoxシェイプを作成する必要があります。次のコードは、`Document`クラスを作成し、テキスト ボックスの形状を作成します。

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## ステップ3: TextBoxの前方リンクを解除する

テキストボックス内の前方リンクを解除するには、`BreakForwardLink()`メソッド。このメソッドは、シーケンス内の次の図形へのリンクを解除します。次のコードは、前方リンクを解除する方法を示しています。

```csharp
textBox.BreakForwardLink();
```

## ステップ4: null値を設定して前方リンクを解除する

あるいは、TextBoxの`Next`財産に`null`これにより、次の図形への接続が効果的に削除されます。次のコードは、このアプローチを示しています。

```csharp
textBox. Next = null;
```

## ステップ5: TextBoxにつながるリンクを解除する

場合によっては、TextBoxシェイプにつながるリンクを解除する必要があります。これは、`BreakForwardLink()`方法`Previous`フォームは TextBox へのリンクを切断します。このようなリンクを切断する方法の例を次に示します。

```csharp
textBox.Previous?.BreakForwardLink();
```

### Aspose.Words for .NET でリンクを解除するためのサンプル ソース コード

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

//転送リンクを解除します。
textBox.BreakForwardLink();

// null 値を設定して前方リンクを解除します。
textBox. Next = null;

//このテキスト ボックスにつながるリンクを解除します。
textBox.Previous?.BreakForwardLink();
```

## 結論

おめでとうございます。これで、.NET 用の Aspose.Words ライブラリを使用して Word 文書内のリダイレクト リンクを解除する方法を学習しました。このガイドの手順に従うことで、文書を設定し、テキスト ボックスの図形を作成し、さまざまな方法を使用してリダイレクト リンクを解除することができました。

### Word 文書の転送リンクを解除するための FAQ

#### Q: Aspose.Words for .NET を使用して Word 文書内のリダイレクト リンクを解除するために使用されるライブラリは何ですか?

A: Aspose.Words for .NET を使用して Word 文書内のリダイレクト リンクを解除するには、Aspose.Words for .NET というライブラリを使用します。

#### Q: TextBox 内のリダイレクト リンクを解除するにはどうすればよいですか?

 A: TextBox内の前方リンクを解除するには、`BreakForwardLink()`メソッド。このメソッドは、シーケンス内の次の図形へのリンクを解除します。

#### Q: null 値を設定してリダイレクト リンクを解除するにはどうすればよいですか?

A: または、リダイレクトリンクを切断するには、`Next` TextBoxのプロパティを`null`これにより、次の図形への接続が効果的に削除されます。

#### Q: TextBox につながるリンクを解除するにはどうすればよいですか?

 A: 場合によっては、TextBoxへのリンクを解除する必要があります。これは、`BreakForwardLink()`方法`Previous`フォームでは、TextBox へのリンクが切断されます。

#### Q: テキストボックス以外の要素でリダイレクト リンクを解除できますか?

A: はい、Aspose.Words for .NET を使用すると、段落、表、画像などのさまざまな要素のリダイレクト リンクを解除できます。プロセスは、リンクを解除する特定の項目によって異なる場合があります。