---
title: PDF ドキュメントで 3D DML 3DEffect をレンダリングする
linktitle: PDF ドキュメントで 3D DML 3DEffect をレンダリングする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にする手順を説明します。これにより、生成された PDF ドキュメント内の 3D 効果が維持されます。以下の手順に従います。

## ステップ 1: ドキュメントをロードする

まず、PDF に変換するドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

必ずドキュメントへの正しいパスを指定してください。

## ステップ 2: PDF 保存オプションを構成する

PdfSaveOptions クラスのインスタンスを作成し、3D DML 効果の高度なレンダリングを有効にします。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

このオプションでは、生成された PDF ドキュメントに 3D 効果が保持されます。

## ステップ 3: ドキュメントを PDF に変換する

使用`Save`保存オプションを指定してドキュメントを PDF に変換するメソッド:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

変換された PDF を保存するための正しいパスを指定してください。

### Aspose.Words for .NET を使用した Dml 3DEffects レンダリングのソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

これらの手順に従うことで、Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを簡単に有効にすることができます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にする方法について説明しました。説明されている手順に従うことで、生成された PDF ドキュメントに 3D 効果を簡単に維持できます。この機能を使用して、元のドキュメントの重要な視覚効果を保存します。


### よくある質問

#### Q: PDF ドキュメントでの 3D DML 効果のレンダリングとは何ですか?
A: PDF ドキュメントでの 3D DML 効果のレンダリングとは、ドキュメントを PDF 形式に変換するときに 3D 効果を保持できる機能を指します。これにより、視覚効果が維持され、生成された PDF ドキュメントが元のドキュメントと同じように見えるようになります。

#### Q: Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にするには、次の手順に従います。

のインスタンスを作成します。`Document` Word ドキュメントへのパスを指定するクラス。

のインスタンスを作成します。`PdfSaveOptions`クラスを設定して、`Dml3DEffectsRenderingMode`財産を`Dml3DEffectsRenderingMode.Advanced` 3D DML 効果の高度なレンダリングを有効にします。

使用`Save`の方法`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: 生成された PDF ドキュメントに 3D DML 効果がレンダリングされているかどうかを確認するにはどうすればよいですか?
A: 生成された PDF ドキュメントで 3D DML 効果がレンダリングされているかどうかを確認するには、Adobe Acrobat Reader などの互換性のある PDF ビューアで PDF ファイルを開いてドキュメントを調べます。元のドキュメントに表示されているのと同じように 3D 効果が表示されるはずです。



