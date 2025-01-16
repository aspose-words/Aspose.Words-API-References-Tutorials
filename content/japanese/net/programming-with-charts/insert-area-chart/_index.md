---
title: Word 文書に面グラフを挿入する
linktitle: Word 文書に面グラフを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、面グラフをドキュメントに挿入する方法を学びます。系列データを追加し、グラフを含むドキュメントを保存します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-area-chart/
---
## 導入

Aspose.Words for .NET を使用して Word 文書に面グラフを挿入する方法について、ステップ バイ ステップで説明するガイドへようこそ。熟練した開発者でも、初心者でも、このチュートリアルでは、Word 文書に魅力的で情報豊富な面グラフを作成するために必要なすべての手順を説明します。前提条件を説明し、必要な名前空間をインポートする方法を示し、明確でわかりやすい手順でプロセスの各ステップをガイドします。

## 前提条件

始める前に、始めるのに必要なものがすべて揃っていることを確認しましょう。

1.  Aspose.Words for .NET: Aspose.Words for .NETがインストールされていることを確認してください。ダウンロードできます。[ここ](https://releases.aspose.com/words/net/).
2. .NET Framework: マシンに .NET Framework がインストールされていることを確認します。
3. IDE: コードを記述して実行するための Visual Studio のような統合開発環境 (IDE)。
4. 基本的な C# の知識: C# プログラミングの基本的な理解が役立ちます。

これらの前提条件が満たされると、Word 文書で美しい面グラフを作成する準備が整います。

## 名前空間のインポート

まず最初に、必要な名前空間をインポートしましょう。これらの名前空間は、Aspose.Words for .NET で Word 文書やグラフを操作するために必要なクラスとメソッドを提供します。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

重要な名前空間をインポートしたので、ドキュメントの作成と面グラフの挿入を段階的に進めていきましょう。

## ステップ1: 新しいWord文書を作成する

まず、新しい Word 文書を作成します。これが面グラフを挿入するベースになります。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

このステップでは、新しい`Document`Word 文書を表すオブジェクト。

## ステップ 2: DocumentBuilder を使用してグラフを挿入する

次に、`DocumentBuilder`ドキュメントに面グラフを挿入するクラスです。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

ここでは、`DocumentBuilder`オブジェクトを作成し、それを使用して特定の寸法 (432x252) の面グラフをドキュメントに挿入します。

## ステップ3: チャートオブジェクトにアクセスする

チャートを挿入した後、`Chart`面グラフをカスタマイズするためのオブジェクト。

```csharp
Chart chart = shape.Chart;
```

このコード行は、`Chart`先ほど挿入した図形からオブジェクトを作成します。

## ステップ4: チャートに系列データを追加する

ここで、チャートにデータを追加します。日付と対応する値を含むシリーズを追加します。

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

この手順では、日付と対応する値のセットを含む「Aspose Series 1」という名前のシリーズを追加します。

## ステップ5: ドキュメントを保存する

最後に、面グラフを挿入したドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

このコード行は、指定されたファイル名で指定されたディレクトリにドキュメントを保存します。

## 結論

おめでとうございます! Aspose.Words for .NET を使用して、Word 文書に面グラフを挿入できました。このガイドでは、環境の設定から最終文書の保存まで、各手順を順を追って説明しました。Aspose.Words for .NET を使用すると、Word 文書にさまざまなグラフやその他の複雑な要素を作成できるため、レポートやプレゼンテーションをより動的で情報豊かなものにすることができます。

## よくある質問

### Aspose.Words for .NET を他の .NET 言語で使用できますか?
はい、Aspose.Words for .NET は VB.NET などの他の .NET 言語もサポートしています。

### チャートの外観をカスタマイズすることは可能ですか?
もちろんです! Aspose.Words for .NET には、グラフの外観をカスタマイズするための幅広いオプションが用意されています。

### 1 つの Word 文書に複数のグラフを追加できますか?
はい、1 つの Word 文書に必要な数のグラフを挿入できます。

### Aspose.Words for .NET は他の種類のグラフをサポートしていますか?
はい、Aspose.Words for .NET は、棒グラフ、折れ線グラフ、円グラフなど、さまざまな種類のグラフをサポートしています。

### Aspose.Words for .NET の一時ライセンスはどこで入手できますか?
一時ライセンスは以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/).