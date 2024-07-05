---
title: WMF フォントをメタファイル サイズにスケールして PDF サイズを縮小する
linktitle: WMF フォントをメタファイル サイズにスケールして PDF サイズを縮小する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに、wmf フォントをメタファイル サイズに合わせて PDF サイズを縮小する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

この記事では、Aspose.Words for .NET の WMF フォントをメタファイル サイズにスケーリングする機能を使用して PDF サイズを縮小する方法について、ステップ バイ ステップで説明します。コードの各部分を詳しく説明します。このチュートリアルの最後には、PDF に変換するときに WMF フォントのスケーリングを有効または無効にする方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントをアップロードする

次に、処理するドキュメントを読み込む必要があります。この例では、ドキュメントの名前が「WMF with text.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## ステップ3: メタファイルのレンダリングオプションを構成する

WMFフォントをメタファイルサイズに合わせて拡大縮小する機能を有効または無効にするには、`MetafileRenderingOptions`オブジェクト。この例では、フォントのスケーリングを無効にし、`ScaleWmfFontsToMetafileSize`財産に`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## ステップ4: メタファイルレンダリングオプションを使用してPDFとして保存オプションを構成する

最後に、先ほど設定したメタファイル レンダリング オプションを使用して、PDF に保存するオプションを設定できます。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## ステップ5: メタファイルレンダリングオプションを使用してドキュメントをPDFとして保存する

以前に設定した保存オプションを使用して、ドキュメントを PDF 形式で保存します。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

以上です。変換時にWMFフォントをメタファイルサイズに合わせてスケーリングする設定を有効または無効にできました。

Aspose.Words for .NET を使用して PDF ドキュメントを作成します。

### Aspose.Words for .NET を使用して WMF フォントをメタファイル サイズにスケーリングするサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Aspose.Wordsがメタファイルレコードの一部をベクターグラフィックに正しくレンダリングできない場合
	//次に、Aspose.Words はこのメタファイルをビットマップにレンダリングします。
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、PDF ドキュメント内の WMF フォントをメタファイル サイズにサイズ変更する機能を有効または無効にする方法を説明しました。説明されている手順に従うことで、PDF ドキュメントに変換するときに、WMF フォントをメタファイル サイズに合わせてサイズ変更するかどうかを簡単に制御できます。これにより、生成される PDF ファイルのサイズが削減され、レンダリング パフォーマンスが向上します。ドキュメントへの正しいパスを指定し、必要に応じてメタファイル レンダリング オプションを構成するようにしてください。

### よくある質問

#### Q: PDF ドキュメント内の WMF フォントをメタファイル サイズに変更するとはどういうことですか?
A: PDF ドキュメント内の WMF フォントをメタファイル サイズにサイズ変更する機能は、PDF ドキュメントに変換するときに WMF フォントをメタファイル サイズに合わせて拡大縮小するかどうかを制御する機能です。この機能を有効にすると、WMF フォントはメタファイルのサイズに合わせて拡大縮小され、生成される PDF ドキュメントのサイズが小さくなる可能性があります。

#### Q: Aspose.Words for .NET を使用して、PDF ドキュメント内の WMF フォントをメタファイル サイズに合わせてサイズ変更する機能を有効または無効にするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメント内の WMF フォントをメタファイル サイズにサイズ変更する機能を有効または無効にするには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

処理したい文書をロードします。`Document`クラスを作成し、指定されたドキュメント ディレクトリ内の Word ドキュメントへのパスを指定します。

メタファイルのレンダリングオプションを設定するには、`MetafileRenderingOptions`クラスと設定`ScaleWmfFontsToMetafileSize`財産に`true` WMFフォントをメタファイルサイズに拡大縮小できるようにする、または`false`この機能を無効にします。

 PDFとして保存オプションを設定するには、`PdfSaveOptions`クラスと、以前に構成したメタファイル レンダリング オプションを使用します。

ドキュメントをPDF形式で保存するには、`Save`方法の`Document`パスと保存オプションを指定するクラス。

#### Q: PDF ドキュメントで WMF フォントをメタファイル サイズに変更する利点は何ですか?
A: PDF ドキュメントで WMF フォントをメタファイル サイズに変更する利点は次のとおりです。

PDF ファイル サイズの縮小: WMF フォントをメタファイル サイズに合わせてサイズ変更すると、フォント サイズがメタファイルのニーズに合わせて調整され、生成される PDF ドキュメントのサイズが縮小されます。

パフォーマンスの向上: WMF フォントのサイズをメタファイルの寸法に合わせて調整することで、PDF ドキュメントのレンダリングがより高速かつ効率的になります。