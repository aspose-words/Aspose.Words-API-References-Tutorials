---
title: Word ファイルからアクティブな XControl プロパティを読み取る
linktitle: Word ファイルからアクティブな XControl プロパティを読み取る
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word ファイル内の ActiveX コントロールのプロパティを読み取ります。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word ファイル内の ActiveX コントロールのプロパティを読み取る方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントの初期化

最初のステップは、`Document` ActiveX コントロールを含む Word 文書をロードしてオブジェクトを取得します。必ず交換してください`MyDir`ドキュメントを含むディレクトリへの実際のパスを使用します。

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## ステップ 2: ActiveX コントロールを回復する

このステップでは、それぞれを繰り返し実行します。`Shape`ドキュメントの ActiveX コントロールを取得し、そのプロパティを読み取ります。

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Aspose.Words for .NET を使用した Read Active XControl Properties のソース コード例

Aspose.Words for .NET を使用して ActiveX コントロールのプロパティを読み取るための完全なソース コードを次に示します。

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## 結論

このガイドでは、Aspose.Words for .NET を使用して Word ファイル内の ActiveX コントロールのプロパティを読み取る方法を説明しました。説明されている手順に従うことで、ドキュメントを初期化し、ActiveX コントロールを取得し、そのプロパティを読み取ることができます。提供されているサンプル コードを開始点として使用し、特定のニーズに合わせてカスタマイズします。

ActiveX コントロールのプロパティを読み取ると、これらのコントロールを含む Word ファイルから重要な情報を抽出できます。 Aspose.Words for .NET は、ActiveX コントロールを使用した文書処理とドキュメント処理の自動化のための強力な機能を提供します。

### よくある質問

#### Q: Word ファイル内の ActiveX コントロールのプロパティを読み取る最初の手順は何ですか?

 A: 最初のステップは、`Document` ActiveX コントロールを含む Word 文書をロードしてオブジェクトを取得します。必ず交換してください`MyDir`ドキュメントを含むディレクトリへの実際のパスを使用します。

#### Q: ActiveX コントロールをドキュメントに取り込むにはどうすればよいですか?

 A: ActiveX コントロールを取得するには、それぞれを反復処理する必要があります。`Shape`ドキュメントの内容を確認し、それが ActiveX コントロールであるかどうかを確認します。使用`OleFormat`の財産`Shape`にアクセスするには`OleControl`オブジェクトを取得し、必要なプロパティを取得します。

#### Q: ActiveX コントロールのどのプロパティを読み取ることができますか?

A: キャプション、値、有効または無効の状態、タイプ、コントロールに関連付けられた childNodes など、ActiveX コントロールのさまざまなプロパティを読み取ることができます。

#### Q: ドキュメント内の ActiveX コントロールの総数を取得するにはどうすればよいですか?

 A: ドキュメント内の ActiveX コントロールの総数を取得するには、`GetChildNodes`の方法`Document`を指定するオブジェクト`NodeType.Shape`タイプと子ノードを含みます。