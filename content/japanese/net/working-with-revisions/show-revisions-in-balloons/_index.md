---
title: バルーンで変更履歴を表示
linktitle: バルーンで変更履歴を表示
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、バルーン内にリビジョンを表示します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/show-revisions-in-balloons/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書のバルーンにリビジョンを表示する方法を説明します。完全なソース コードを提供し、マークダウン出力の書式設定方法を説明します。

## ステップ1: ドキュメントの読み込み

最初のステップは、修正を含むドキュメントをアップロードすることです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ2: レビュー表示オプションを設定する

バルーン内にリビジョンが表示されるように表示オプションを設定します。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## ステップ3: ドキュメントをPDF形式で保存する

最後に、バルーン内に表示された変更内容とともにドキュメントを PDF として保存します。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown出力形式

読みやすさを向上させるために、出力をマークダウン形式でフォーマットすることができます。例:

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Aspose.Words for .NET を使用してバルーンでリビジョンを表示するサンプル ソース コード

Aspose.Words for .NET を使用してドキュメント内のバルーンに変更履歴を表示するための完全なソース コードは次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

//リビジョンの挿入をインラインでレンダリングし、リビジョンの削除とフォーマットをバルーンで表示します。
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
//ページの右側にリビジョン バーを表示します。
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のバルーンにリビジョンを表示する方法を学習しました。適切な表示オプションを使用することで、右側にリビジョン バーがあるバブルにリビジョンを表示できるようになりました。Aspose.Words for .NET には、リビジョン管理など、Word 文書を操作するための強力な機能が多数用意されています。この知識を活用して、Aspose.Words for .NET を使用して独自の Word 文書のバルーンにリビジョンを表示できます。


### よくある質問

#### Q: Aspose.Words for .NET でドキュメントをアップロードするにはどうすればよいですか?

 A:`Document`ファイルからドキュメントを読み込むための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET を使用してバルーンにリビジョンを表示するにはどうすればよいですか?

 A:`ShowInBalloons`の財産`RevisionOptions`オブジェクトを使用して、バルーン内のリビジョンの表示を設定します。このプロパティは`ShowInBalloons.FormatAndDelete`削除や書式設定の変更をバルーンで表示します。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Q: Aspose.Words for .NET を使用してドキュメントを PDF 形式で保存するにはどうすればよいですか?

 A:`Save`方法の`Document`オブジェクトを使用して、ドキュメントを PDF 形式で保存します。「.pdf」拡張子付きの完全な保存先パスを指定する必要があります。

```csharp
doc.Save("path/to/destination/document.pdf");
```