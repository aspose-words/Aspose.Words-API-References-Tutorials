---
title: Word ファイルから Active XControl プロパティを読み取る
linktitle: Word ファイルから Active XControl プロパティを読み取る
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word ファイル内の ActiveX コントロールのプロパティを読み取ります。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word ファイル内の ActiveX コントロールのプロパティを読み取る方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を説明します。

## ステップ1: ドキュメントの初期化

最初のステップは、`Document` ActiveXコントロールを含むWord文書をロードしてオブジェクトを作成します。`MyDir`ドキュメントを含むディレクトリへの実際のパスを指定します。

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## ステップ2: ActiveXコントロールを回復する

このステップでは、それぞれを反復処理します`Shape`ドキュメントの ActiveX コントロールを取得し、そのプロパティを読み取ります。

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

### Aspose.Words for .NET を使用して Active XControl プロパティを読み取るためのサンプル ソース コード

以下は、Aspose.Words for .NET を使用して ActiveX コントロールのプロパティを読み取るための完全なソース コードです。

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

このガイドでは、Aspose.Words for .NET を使用して Word ファイル内の ActiveX コントロールのプロパティを読み取る方法について説明しました。説明されている手順に従うことで、ドキュメントを初期化し、ActiveX コントロールを取得してそのプロパティを読み取ることができます。提供されているサンプル コードを開始点として使用し、特定のニーズに合わせてカスタマイズしてください。

ActiveX コントロールのプロパティを読み取ることで、これらのコントロールを含む Word ファイルから重要な情報を抽出できます。Aspose.Words for .NET は、ActiveX コントロールを使用した Words 処理とドキュメント処理の自動化のための強力な機能を提供します。

### よくある質問

#### Q: Word ファイル内の ActiveX コントロールのプロパティを読み取るための最初の手順は何ですか?

 A: 最初のステップは、`Document` ActiveXコントロールを含むWord文書をロードしてオブジェクトを作成します。`MyDir`ドキュメントを含むディレクトリへの実際のパスを指定します。

#### Q: ActiveX コントロールをドキュメントに組み込むにはどうすればよいですか?

 A: ActiveXコントロールを取得するには、各コントロールを反復処理する必要があります。`Shape`ドキュメントのActiveXコントロールであるかどうかを確認します。`OleFormat`の所有物`Shape`アクセスするには`OleControl`オブジェクトを作成して必要なプロパティを取得します。

#### Q: ActiveX コントロールのどのプロパティを読み取ることができますか?

A: ActiveX コントロールのキャプション、値、有効または無効の状態、タイプ、コントロールに関連付けられた childNodes など、さまざまなプロパティを読み取ることができます。

#### Q: ドキュメント内の ActiveX コントロールの合計数を取得するにはどうすればよいですか?

 A: ドキュメント内のActiveXコントロールの総数を取得するには、`GetChildNodes`方法の`Document`指定するオブジェクト`NodeType.Shape`タイプと子ノードを含みます。