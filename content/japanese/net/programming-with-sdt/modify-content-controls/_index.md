---
title: コンテンツコントロールの変更
linktitle: コンテンツコントロールの変更
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のコンテンツ コントロール内のテキスト、ドロップダウン リスト、画像を変更する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/modify-content-controls/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のさまざまな種類のコンテンツ コントロールを変更する方法について説明します。コンテンツ コントロール内のテキスト、ドロップダウン リストの選択値を更新したり、画像を置き換えたりすることができます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されているディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントを読み込み、コンテンツ コントロールを反復処理する
Word文書を読み込むには、`Document`コンストラクタにドキュメントへのパスをパラメータとして渡します。ドキュメント内のすべての構造化ドキュメントタグを反復処理するには、`foreach`ループ。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    //コンテンツコントロールの種類に基づいてアクションを実行する
}
```

## ステップ3: プレーンテキストコンテンツコントロールを変更する
コンテンツコントロールの種類`SdtType.PlainText`既存の子要素をすべて削除し、新しい段落を作成して、目的のテキストを含む実行を追加します。

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## ステップ4: ドロップダウンリストのコンテンツコントロールを変更する
コンテンツコントロールの種類`SdtType.DropDownList`選択した値を特定の値に設定して更新します`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## ステップ5: 画像コンテンツコントロールを変更する
コンテンツコントロールの種類`SdtType.Picture`コンテンツ コントロール内の図形を取得し、その画像を新しい画像に置き換えます。

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## ステップ6: 変更したドキュメントを保存する
変更したドキュメントを指定されたディレクトリに保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.ModifyContentControls.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Aspose.Words for .NET を使用してコンテンツ コントロールを変更するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内のさまざまな種類のコンテンツ コントロールを正常に変更できました。