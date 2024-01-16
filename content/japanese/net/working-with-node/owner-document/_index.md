---
title: 所有者文書
linktitle: 所有者文書
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でオーナー ドキュメントを使用する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-node/owner-document/
---

ここでは、Aspose.Words for .NET で独自のドキュメント機能を使用する方法を示す、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。

## ステップ 1: 必要な参照をインポートする
始める前に、Aspose.Words for .NET を使用するために必要な参照をプロジェクトにインポートしていることを確認してください。これには、Aspose.Words ライブラリのインポートと、ソース ファイルへの必要な名前空間の追加が含まれます。

```csharp
using Aspose.Words;
using Aspose.Words.Nodes;
using Aspose.Words.Paragraphs;
```

## ステップ 2: 新しいドキュメントを作成する
このステップでは、`Document`クラス。

```csharp
Document doc = new Document();
```

## ステップ 3: 所有者ドキュメントを使用してノードを作成する
任意のタイプの新しいノードを作成するときは、ドキュメントをコンストラクターに渡す必要があります。この例では、ドキュメントを使用して新しい段落ノードを作成しています。`doc`.

```csharp
Paragraph para = new Paragraph(doc);
```

## ステップ 4: 親ノードと所有者ドキュメントを確認する
段落ノードを作成したので、そのノードに親ノードがあるかどうか、および所有ドキュメントが同じであるかどうかを確認できます。`doc`.

```csharp
Console.WriteLine("The paragraph has no parent node: " + (para.ParentNode == null));
Console.WriteLine("The documents of the two nodes are identical: " + (para.Document == doc));
```

## ステップ 5: ドキュメント データを使用してノード プロパティを変更する
ノードとドキュメント間の関係により、スタイルやリストなどのドキュメント固有のデータを参照するプロパティへのアクセスと変更が可能になります。この例では、段落スタイル名を「見出し 1」に設定しています。

```csharp
para.ParagraphFormat.StyleName = "Heading 1";
```

## ステップ 6: 文書に段落を追加する
これで、文書のメインセクションに段落ノードを追加できるようになりました。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## ステップ 7: 追加後の親ノードを確認する
文書に段落を追加した後、その段落に親ノードがあるかどうかを再度確認します。

```csharp
Console.WriteLine("The paragraph has a parent node: " + (para.ParentNode != null));
```

### Aspose.Words for .NET を使用したオーナー ドキュメントのサンプル ソース コード

```csharp
Document doc = new Document();

//任意のタイプの新しいノードを作成するには、コンストラクターにドキュメントを渡す必要があります。
Paragraph para = new Paragraph(doc);

//新しい段落ノードにはまだ親がありません。
Console.WriteLine("Paragraph has no parent node: " + (para.ParentNode == null));

//しかし、段落ノードはそのドキュメントを知っています。
Console.WriteLine("Both nodes' documents are the same: " + (para.Document == doc));

//ノードは常にドキュメントに属しているため、アクセスして変更することができます。
//スタイルやリストなど、ドキュメント全体のデータを参照するプロパティ。
para.ParagraphFormat.StyleName = "Heading 1";

//次に、最初のセクションの本文に段落を追加します。
doc.FirstSection.Body.AppendChild(para);

//段落ノードは本文ノードの子になりました。
Console.WriteLine("Paragraph has a parent node: " + (para.ParentNode != null));
```

### よくある質問

#### Q: Node.js の独自ドキュメントとは何ですか?

A: Node.js のオーナー ドキュメントは、特定のノードが属する XML ドキュメントです。これは、ノードを含む XML ドキュメントのインスタンスを表します。

#### Q: ノードの所有者ドキュメントを取得するにはどうすればよいですか?

 A: Node.js でノードの所有者ドキュメントを取得するには、`ownerDocument`ノードのプロパティ。このプロパティは、ノードを所有する XML ドキュメントを返します。

#### Q: 専有文書は何に使用されますか?

A: オーナー ドキュメントは、XML ドキュメント内のノードのグローバル コンテキストを表すために使用されます。これにより、ドキュメント内の他のノードへのアクセスが提供され、それらのノード上で操作を実行できるようになります。

#### Q: ノードの所有者ドキュメントを変更できますか?

A: ほとんどの場合、ノードのドキュメント所有者はノードの作成時に決定され、直接変更することはできません。所有者ドキュメントは読み取り専用のプロパティです。

#### Q: オーナードキュメントのノードにアクセスするにはどうすればよいですか?

 A: 独自のドキュメント内のノードにアクセスするには、Node.js 環境で使用される XML API によって提供されるメソッドとプロパティを使用できます。たとえば、次のようなメソッドを使用できます。`getElementsByTagName`または`querySelector`ドキュメント内の特定のノードを選択します。