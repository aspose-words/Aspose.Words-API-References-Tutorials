---
title: グラフの軸の境界
linktitle: グラフの軸の境界
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、軸に表示される値の範囲を制御しながら、グラフの軸の境界を設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/bounds-of-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の境界を設定する方法について説明します。グラフを挿入し、系列データを追加し、軸のスケーリングを構成することで、軸の最小値と最大値を定義できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: 新しいドキュメントとDocumentBuilderを作成する
新しいインスタンスを作成する`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: グラフを挿入して構成する
ドキュメントにグラフを挿入するには、`InsertChart`方法の`DocumentBuilder`オブジェクト。希望するグラフの種類と寸法を設定します。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ステップ4: シリーズデータを追加する
グラフ内の既存のシリーズをクリアし、新しいシリーズ データを追加します。この例では、「アイテム 1」から「アイテム 5」までのラベルと対応する値を持つシリーズを追加します。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## ステップ5: 軸の境界を設定する
Y軸のスケーリングを設定するには、`Scaling.Minimum`そして`Scaling.Maximum`軸のプロパティ。

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## ステップ6: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.BoundsOfAxis.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Aspose.Words for .NET を使用した Bounds Of Axis のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

これで完了です。Aspose.Words for .NET を使用して、グラフの軸の境界を正常に設定できました。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の境界を設定する方法を学習しました。ステップ バイ ステップ ガイドに従うことで、グラフを挿入して構成し、系列データを追加し、軸のスケーリングの最小値と最大値を定義できます。Aspose.Words for .NET は、Word ドキュメントの Words Processing 用の強力で柔軟な API を提供し、動的で視覚的に魅力的なグラフを簡単に作成できます。


### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が Word 文書をプログラムで操作できるようにするライブラリです。Word 文書を作成、操作、保存するための幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio の NuGet パッケージ マネージャーを使用できます。NuGet パッケージ マネージャーで「Aspose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を他のプログラミング言語で使用できますか?
いいえ、Aspose.Words for .NET は .NET アプリケーション専用に設計されています。C# や VB.NET などのプログラミング言語で動作します。

#### Q4. Aspose.Words for .NET を使用するためのその他の前提条件はありますか?
Aspose.Words for .NET ライブラリをインストールすることに加えて、C# プログラミングと Word 文書での Words Processing に関する基本的な知識も必要です。.NET フレームワークの知識も役立ちます。
