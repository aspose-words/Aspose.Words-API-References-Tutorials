---
title: リビジョンをバルーンで表示
linktitle: リビジョンをバルーンで表示
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してバルーン内にリビジョンを表示します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/show-revisions-in-balloons/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書のバルーンにリビジョンを表示する方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントをロードする

最初のステップは、リビジョンを含むドキュメントをアップロードすることです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## ステップ 2: レビュー表示オプションを構成する

リビジョンがバルーン内に表示されるように表示オプションを設定します。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## ステップ 3: ドキュメントを PDF 形式で保存する

最後に、バルーン内に表示されているリビジョンを含むドキュメントを PDF として保存します。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## マークダウン出力形式

読みやすさを向上させるために、出力をマークダウンでフォーマットすることができます。例えば ：

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Aspose.Words for .NET を使用したバルーン内のリビジョンの表示のソース コード例

Aspose.Words for .NET を使用してドキュメント内のバルーンにリビジョンを表示する完全なソース コードを次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

//リビジョンをインラインで挿入し、バルーン内のリビジョンを削除およびフォーマットしてレンダリングします。
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
//ページの右側にリビジョン バーをレンダリングします。
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書のバルーンにリビジョンを表示する方法を学習しました。適切な表示オプションを使用することで、右側にリビジョン バーを備えたバブル内にリビジョンを表示することができました。 Aspose.Words for .NET は、リビジョン管理など、Word ドキュメントを操作するための強力な機能を多数提供します。この知識を利用して、Aspose.Words for .NET を使用して独自の Word 文書のバルーンにリビジョンを表示できるようになりました。


### よくある質問

#### Q: Aspose.Words for .NET にドキュメントをアップロードするにはどうすればよいですか?

 A: を使用してください。`Document`ファイルからドキュメントをロードするための Aspose.Words for .NET のクラス。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET を使用してバルーン内にリビジョンを表示するにはどうすればよいですか?

 A: を使用してください。`ShowInBalloons`の財産`RevisionOptions`オブジェクトを使用して、バルーン内のリビジョンの表示を設定します。このプロパティを設定できるのは、`ShowInBalloons.FormatAndDelete`削除および書式設定のリビジョンをバルーン内に表示します。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Q: Aspose.Words for .NET を使用してドキュメントを PDF 形式で保存するにはどうすればよいですか?

 A: を使用してください。`Save`の方法`Document`オブジェクトを使用してドキュメントを PDF 形式で保存します。 「.pdf」拡張子を付けた完全な宛先パスを指定する必要があります。

```csharp
doc.Save("path/to/destination/document.pdf");
```