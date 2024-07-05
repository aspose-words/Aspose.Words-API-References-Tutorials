---
title: PDF ドキュメントで 3D DML 3DEffects をレンダリングする
linktitle: PDF ドキュメントで 3D DML 3DEffects をレンダリングする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にする手順を説明します。これにより、生成された PDF ドキュメントに 3D 効果が保持されます。以下の手順に従ってください。

## ステップ1: ドキュメントの読み込み

まず、PDF に変換したいドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

ドキュメントへの正しいパスを必ず指定してください。

## ステップ2: PDF保存オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、3D DML 効果の高度なレンダリングを有効にします。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

このオプションは、生成された PDF ドキュメントに 3D 効果を保持します。

## ステップ3: ドキュメントをPDFに変換する

使用`Save`保存オプションを指定してドキュメントを PDF に変換する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

変換した PDF を保存するには、正しいパスを指定してください。

### Aspose.Words for .NET を使用した Dml 3DEffects レンダリングのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

これらの手順に従うと、Aspose.Words for .NET を使用して PDF に変換するときに、3D DML 効果のレンダリングを簡単に有効にすることができます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にする方法について説明しました。説明されている手順に従うことで、生成された PDF ドキュメントで 3D 効果を簡単に維持できます。この機能を使用して、元のドキュメントの重要な視覚効果を維持します。


### よくある質問

#### Q: PDF ドキュメントで 3D DML 効果をレンダリングするとはどういうことですか?
A: PDF ドキュメントで 3D DML 効果をレンダリングするということは、ドキュメントを PDF 形式に変換するときに 3D 効果を保持する機能のことです。これにより、視覚効果が保持され、生成された PDF ドキュメントが元のドキュメントと同じように見えるようになります。

#### Q: Aspose.Words for .NET を使用して PDF に変換するときに、3D DML 効果のレンダリングを有効にするにはどうすればよいでしょうか?
A: Aspose.Words for .NET を使用して PDF に変換するときに 3D DML 効果のレンダリングを有効にするには、次の手順に従います。

インスタンスを作成する`Document` Word 文書へのパスを指定するクラス。

インスタンスを作成する`PdfSaveOptions`クラスを設定し、`Dml3DEffectsRenderingMode`財産に`Dml3DEffectsRenderingMode.Advanced` 3D DML 効果の高度なレンダリングを有効にします。

使用`Save`方法の`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: 生成された PDF ドキュメントで 3D DML 効果がレンダリングされているかどうかを確認するにはどうすればよいですか?
A: 生成された PDF ドキュメントで 3D DML 効果がレンダリングされているかどうかを確認するには、Adobe Acrobat Reader などの互換性のある PDF ビューアで PDF ファイルを開き、ドキュメントを調べます。元のドキュメントに表示される 3D 効果を確認できるはずです。



