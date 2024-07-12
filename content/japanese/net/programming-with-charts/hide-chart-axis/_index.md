---
title: Word 文書でグラフの軸を非表示にする
linktitle: Word 文書でグラフの軸を非表示にする
second_title: Aspose.Words ドキュメント処理 API
description: 詳細なステップバイステップのチュートリアルで、Aspose.Words for .NET を使用して Word 文書内のグラフ軸を非表示にする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/hide-chart-axis/
---
## 導入

動的で視覚的に魅力的な Word 文書を作成するには、多くの場合、チャートやグラフを組み込む必要があります。そのようなシナリオの 1 つとして、よりすっきりとしたプレゼンテーションのためにチャートの軸を非表示にすることが考えられます。Aspose.Words for .NET は、そのようなタスクのための包括的で使いやすい API を提供します。このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書でチャートの軸を非表示にする手順を説明します。

## 前提条件

チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。

-  Aspose.Words for .NET: ダウンロードはこちらから[ここ](https://releases.aspose.com/words/net/).
- 開発環境: Visual Studio など、.NET 開発をサポートする任意の IDE。
- .NET Framework: マシンに .NET Framework がインストールされていることを確認します。
- C# の基礎知識: C# プログラミング言語に精通していると有利です。

## 名前空間のインポート

Aspose.Words for .NET の使用を開始するには、プロジェクトに必要な名前空間をインポートする必要があります。手順は次のとおりです。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

プロセスをシンプルでわかりやすいステップに分解してみましょう。

## ステップ 1: ドキュメントと DocumentBuilder を初期化する

最初のステップでは、新しい Word 文書を作成し、DocumentBuilder オブジェクトを初期化します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

このステップでは、ドキュメントを保存するパスを定義します。次に、新しい`Document`オブジェクトと`DocumentBuilder`ドキュメントの構築を開始するためのオブジェクト。

## ステップ2: グラフを挿入する

次に、`DocumentBuilder`物体。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

ここでは、指定されたディメンションの縦棒グラフを挿入します。`InsertChart`メソッドは`Shape`チャートを含むオブジェクト。

## ステップ3: 既存のシリーズをクリアする

グラフに新しいデータを追加する前に、既存のシリーズをすべてクリアする必要があります。

```csharp
chart.Series.Clear();
```

この手順により、グラフ内のデフォルト データがすべて削除され、次に追加する新しいデータのための場所が確保されます。

## ステップ4: シリーズデータを追加する

ここで、独自のデータ シリーズをグラフに追加してみましょう。

```csharp
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

この手順では、対応するカテゴリと値を持つ「Aspose Series 1」というタイトルのシリーズを追加します。

## ステップ5: Y軸を非表示にする

グラフのY軸を非表示にするには、`Hidden` Y軸のプロパティ`true`.

```csharp
chart.AxisY.Hidden = true;
```

このコード行は Y 軸を非表示にし、グラフ内で見えなくします。

## ステップ6: ドキュメントを保存する

最後に、ドキュメントを指定されたディレクトリに保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

このコマンドは、グラフを含む Word 文書を指定されたパスに保存します。

## 結論

おめでとうございます。Aspose.Words for .NET を使用して Word 文書内のグラフ軸を非表示にする方法を学習しました。この強力なライブラリを使用すると、Word 文書をプログラムで簡単に操作できます。これらの手順に従うことで、最小限の労力でカスタマイズされたプロフェッショナルな外観の文書を作成できます。

## よくある質問

### Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、.NET アプリケーション内で Word 文書を作成、編集、変換、操作するための強力な API です。

### グラフ内の X 軸と Y 軸の両方を非表示にすることはできますか?
はい、両方の軸を非表示にするには、`Hidden`両者の財産`AxisX`そして`AxisY`に`true`.

### Aspose.Words for .NET の無料試用版はありますか?
はい、無料トライアルをご利用いただけます[ここ](https://releases.aspose.com/).

### さらに詳しいドキュメントはどこで見つかりますか?
詳細なドキュメントはAspose.Words for .NETでご覧いただけます。[ここ](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET のサポートを受けるにはどうすればよいですか?
 Asposeコミュニティからサポートを受けることができます[ここ](https://forum.aspose.com/c/words/8).
