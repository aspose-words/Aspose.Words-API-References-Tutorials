---
title: Word 文書の比較の粒度
linktitle: Word 文書の比較の粒度
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の Word ドキュメントの粒度を比較する機能について学習します。この機能を使用すると、ドキュメントを 1 文字ずつ比較し、加えられた変更をレポートできます。
type: docs
weight: 10
url: /ja/net/compare-documents/comparison-granularity/
---
ここでは、Aspose.Words for .NET の Word ドキュメントの粒度の比較機能を使用する、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。

## ステップ 1: はじめに

Aspose.Words for .NET の粒度の比較機能を使用すると、文字レベルでドキュメントを比較できます。これは、各文字が比較され、それに応じて変更が報告されることを意味します。

## ステップ 2: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用できるように開発環境をセットアップする必要があります。 Aspose.Words ライブラリがインストールされていること、およびコードを埋め込むための適切な C# プロジェクトがあることを確認してください。

## ステップ 3: 必要なアセンブリを追加する

Aspose.Words for .NET の粒度の比較機能を使用するには、必要なアセンブリをプロジェクトに追加する必要があります。プロジェクト内に Aspose.Words への適切な参照があることを確認してください。

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## ステップ 4: ドキュメントの作成

このステップでは、DocumentBuilder クラスを使用して 2 つのドキュメントを作成します。これらの文書は比較に使用されます。

```csharp
//文書Aを作成します。
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

//文書Bを作成します。
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## ステップ 5: 比較オプションの構成

このステップでは、比較の粒度を指定するために比較オプションを構成します。ここではキャラクターレベルの粒度を使用します。

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## ステップ 6: 文書の比較

次に、Document クラスの Compare メソッドを使用してドキュメントを比較してみましょう。変更はドキュメント A に保存されます。

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

の`Compare`このメソッドは、ドキュメント A とドキュメント B を比較し、変更をドキュメント A に保存します。参照用に作成者の名前と比較の日付を指定できます。

## 結論

この記事では、Aspose.Words for .NET の粒度の比較機能について説明しました。この機能を使用すると、文字レベルでドキュメントを比較し、変更をレポートできます。この知識を使用して、プロジェクト内で詳細なドキュメントの比較を実行できます。

### Aspose.Words for .NET を使用した比較粒度のサンプル ソース コード

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET の比較粒度機能を検討しました。この機能を使用すると、ドキュメントを比較する際の詳細レベルを指定できます。さまざまな粒度レベルを選択することで、特定の要件に応じて文字、単語、またはブロック レベルで詳細な比較を実行できます。 Aspose.Words for .NET は、柔軟かつ強力なドキュメント比較機能を提供し、さまざまなレベルの粒度でドキュメントの相違点を簡単に識別できるようにします。

### よくある質問

#### Q: Aspose.Words for .NET で比較粒度を使用する目的は何ですか?

A: Aspose.Words for .NET の比較粒度を使用すると、ドキュメントを比較する際の詳細レベルを指定できます。この機能を使用すると、文字レベル、単語レベル、さらにはブロック レベルなど、さまざまなレベルでドキュメントを比較できます。各粒度レベルにより、比較結果の詳細レベルが異なります。

#### Q: Aspose.Words for .NET で比較粒度を使用するにはどうすればよいですか?

A: Aspose.Words for .NET で比較粒度を使用するには、次の手順に従います。
1. Aspose.Words ライブラリを使用して開発環境をセットアップします。
2. Aspose.Words を参照して、必要なアセンブリをプロジェクトに追加します。
3. を使用して、比較するドキュメントを作成します。`DocumentBuilder`クラス。
4. を作成して比較オプションを構成します。`CompareOptions`オブジェクトと設定`Granularity`プロパティを希望のレベルに設定します (例:`Granularity.CharLevel`キャラクターレベルの比較用）。
5. 使用`Compare`一方のドキュメントのメソッドを、もう一方のドキュメントと`CompareOptions`オブジェクトをパラメータとして指定します。このメソッドは、指定された粒度に基づいてドキュメントを比較し、最初のドキュメントの変更を保存します。

#### Q: Aspose.Words for .NET で利用可能な比較粒度のレベルは何ですか?

A: Aspose.Words for .NET は、次の 3 レベルの比較粒度を提供します。
- `Granularity.CharLevel`: 文書を文字レベルで比較します。
- `Granularity.WordLevel`: 文書を単語レベルで比較します。
- `Granularity.BlockLevel`: ドキュメントをブロックレベルで比較します。

#### Q: 文字レベルの粒度で比較結果を解釈するにはどうすればよいですか?

A: 文字レベルの粒度で、比較されるドキュメント内の各文字の違いが分析されます。比較結果には、追加、削除、変更など、個々のキャラクター レベルでの変更が表示されます。