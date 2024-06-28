---
title: チャートの軸の範囲
linktitle: チャートの軸の範囲
second_title: Aspose.Words ドキュメント処理 API
description: 軸に表示される値の範囲を制御する Aspose.Words for .NET を使用して、グラフの軸の境界を設定する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/bounds-of-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の境界を設定する方法について説明します。グラフを挿入し、系列データを追加し、軸のスケーリングを構成することで、軸の最小値と最大値を定義できます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 新しいドキュメントと DocumentBuilder を作成する
の新しいインスタンスを作成します。`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: グラフの挿入と構成
を使用してドキュメントにグラフを挿入します。`InsertChart`の方法`DocumentBuilder`物体。必要なグラフの種類と寸法を設定します。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 4: シリーズ データを追加する
グラフ内の既存の系列をクリアし、新しい系列データを追加します。この例では、「Item 1」から「Item 5」というラベルと対応する値を持つシリーズを追加します。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## ステップ 5: 軸の境界を設定する
を使用して最小値と最大値を設定して、Y 軸のスケーリングを構成します。`Scaling.Minimum`そして`Scaling.Maximum`軸のプロパティ。

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## ステップ 6: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.BoundsOfAxis.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Aspose.Words for .NET を使用した軸境界のソース コード例 

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

それでおしまい！ Aspose.Words for .NET を使用してグラフの軸の境界を正常に設定しました。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の境界を設定する方法を学習しました。ステップバイステップのガイドに従うことで、グラフの挿入と構成、系列データの追加、軸のスケーリングの最小値と最大値の定義を行うことができます。 Aspose.Words for .NET は、Word ドキュメントを使用したワード処理用の強力で柔軟な API を提供し、動的で視覚的に魅力的なグラフを簡単に作成できます。


### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が Word ドキュメントをプログラムで操作できるようにするライブラリです。 Word 文書を作成、操作、保存するための幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio で NuGet パッケージ マネージャーを使用できます。 NuGet パッケージ マネージャーで「Apose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を他のプログラミング言語で使用できますか?
いいえ、Aspose.Words for .NET は .NET アプリケーション専用に設計されています。 C#やVB.NETなどのプログラミング言語で動作します。

#### Q4. Aspose.Words for .NET を使用するためのその他の前提条件はありますか?
Aspose.Words for .NET ライブラリをインストールすることに加えて、C# プログラミングと Word ドキュメントを使用したワード処理の基本的な知識が必要です。 .NET Framework に精通していることも役に立ちます。
