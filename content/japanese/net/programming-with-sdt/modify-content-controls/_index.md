---
title: コンテンツコントロールの変更
linktitle: コンテンツコントロールの変更
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書のコンテンツ コントロール内のテキスト、ドロップダウン リスト、画像を変更する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-sdt/modify-content-controls/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のさまざまな種類のコンテンツ コントロールを変更する方法について説明します。テキスト、ドロップダウン リストの選択した値を更新したり、コンテンツ コントロール内の画像を置き換えたりできます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが置かれているディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードし、コンテンツ コントロールを反復処理する
を使用して Word 文書をロードします。`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。を使用して、ドキュメント内のすべての構造化ドキュメント タグを反復処理します。`foreach`ループ。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    //コンテンツ コントロールのタイプに基づいてアクションを実行します
}
```

## ステップ 3: プレーン テキスト コンテンツ コントロールを変更する
タイプのコンテンツ コントロールの場合`SdtType.PlainText`、既存の子をすべて削除し、新しい段落を作成し、目的のテキストを含むランを追加します。

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

## ステップ 4: ドロップダウン リスト コンテンツ コントロールを変更する
タイプのコンテンツ コントロールの場合`SdtType.DropDownList`、選択した値を特定の値に設定して更新します。`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## ステップ 5: 画像コンテンツ コントロールを変更する
タイプのコンテンツ コントロールの場合`SdtType.Picture`、コンテンツ コントロール内の図形を取得し、その画像を新しい画像に置き換えます。

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

## ステップ 6: 変更したドキュメントを保存する
を使用して、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithSdt.ModifyContentControls.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Aspose.Words for .NET を使用したコンテンツ コントロールの変更のソース コード例 

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

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内のさまざまな種類のコンテンツ コントロールを正常に変更できました。