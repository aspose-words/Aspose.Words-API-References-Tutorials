---
title: 数式
linktitle: 数式
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に数式を追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-officemath/math-equations/
---

Aspose.Words for .NET は、C# アプリケーションで Word 文書を作成、編集、操作するための強力なライブラリです。Aspose.Words が提供する機能の 1 つに、文書に数式を追加する機能があります。このガイドでは、Aspose.Words for .NET の C# ソース コードを使用して Word 文書に数式を追加する方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、Word 文書での Words 処理を簡単かつ効率的にする人気のライブラリです。数式のサポートなど、Word 文書の作成、編集、操作のための幅広い機能を提供します。

## Word文書の読み込み

最初のステップは、数式を追加する Word 文書を読み込むことです。Document クラスを使用して、ソース ファイルから文書を読み込みます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Office math.docx");
```

この例では、ドキュメント ディレクトリにある「Office math.docx」ドキュメントを読み込んでいます。

## 数式を追加する

ドキュメントが読み込まれると、ドキュメント内の OfficeMath 要素にアクセスできます。Document クラスの GetChild メソッドを使用して、指定されたインデックスから OfficeMath 項目を取得します。次に例を示します。

```csharp
OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);
```

この例では、ドキュメント内の最初の OfficeMath 項目を取得します。

## 数式のプロパティの設定

OfficeMath オブジェクトのプロパティを使用して、数式のさまざまなプロパティを構成できます。たとえば、DisplayType プロパティを使用して数式の表示タイプを設定できます。次に例を示します。

```csharp
officeMath.DisplayType = OfficeMathDisplayType.Display;
```

この例では、数式の表示タイプを「表示」に設定しています。これは、数式が独自の行に表示されることを意味します。

同様に、Justification プロパティを使用して数式の配置を設定できます。次に例を示します。

```csharp
officeMath.Justification = OfficeMathJustification.Left;
```

この例では、数式の配置を左に設定します。

## 数式を含む文書を保存する

数式のプロパティを設定したら、Document クラスの Save メソッドを使用して変更したドキュメントを保存できます。次に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithOfficeMath.MathEquations.docx

");
```

この例では、変更したドキュメントを「WorkingWithOfficeMath.MathEquations.docx」として保存します。

### Aspose.Words for .NET を使用した数式のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word文書を読み込む
Document doc = new Document(dataDir + "Office math.docx");

//OfficeMath要素を取得する
OfficeMath officeMath = (OfficeMath)doc.GetChild(NodeType.OfficeMath, 0, true);

//数式のプロパティを設定する
officeMath.DisplayType = OfficeMathDisplayType.Display;
officeMath.Justification = OfficeMathJustification.Left;

//数式を含む文書を保存する
doc.Save(dataDir + "WorkingWithOfficeMath.MathEquations.docx");
```

## 結論

このガイドでは、提供されている C# ソース コードを使用して、Aspose.Words for .NET で Word 文書に数式を追加する方法について説明しました。提供されている手順に従うと、C# アプリケーションで Word 文書に数式を簡単に追加できます。Aspose.Words は数式を使用した Words 処理に優れた柔軟性とパワーを提供し、プロフェッショナルで書式設定された文書を作成できます。
