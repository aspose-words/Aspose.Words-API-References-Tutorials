---
title: Wmf フォントをメタファイル サイズに拡大縮小して PDF サイズを縮小する
linktitle: Wmf フォントをメタファイル サイズに拡大縮小して PDF サイズを縮小する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに、wmf フォントをメタファイル サイズにスケールして PDF サイズを縮小するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

この記事では、Aspose.Words for .NET の wmf フォントをメタファイル サイズに拡大縮小する機能を使用して PDF サイズを縮小する方法についてのステップバイステップ ガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルを終えると、PDF に変換するときに WMF フォントのスケーリングを有効または無効にする方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードする

次に、処理するドキュメントをロードする必要があります。この例では、ドキュメントが「WMF with text.docx」という名前で、指定されたドキュメント ディレクトリに配置されていると仮定します。

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## ステップ 3: メタファイルのレンダリング オプションを構成する

メタファイル サイズに合わせた WMF フォントのスケーリングを有効または無効にするには、`MetafileRenderingOptions`物体。この例では、フォントのスケーリングを無効にします。`ScaleWmfFontsToMetafileSize`財産を`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## ステップ 4: メタファイル レンダリング オプションを使用して PDF として保存オプションを構成する

最後に、前に設定したメタファイル レンダリング オプションを使用して、PDF に保存するオプションを設定できます。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## ステップ 5: メタファイル レンダリング オプションを使用してドキュメントを PDF として保存する

以前に構成した保存オプションを使用して、ドキュメントを PDF 形式で保存します。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

それだけです ！変換時に WMF フォントのメタファイル サイズへのスケーリングを有効または無効にできました。

Aspose.Words for .NET を使用した PDF ドキュメント。

### Aspose.Words for .NET を使用して WMF フォントをメタファイル サイズにスケーリングするためのソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Aspose.Words が一部のメタファイル レコードをベクター グラフィックスに正しくレンダリングできない場合
	//次に、Aspose.Words がこのメタファイルをビットマップにレンダリングします。
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメント内の WMF フォントのメタファイル サイズへのサイズ変更を有効または無効にする方法について説明しました。ここで説明する手順に従うことで、PDF ドキュメントに変換するときにメタファイルのサイズに合わせて WMF フォントのサイズを変更するかどうかを簡単に制御できます。これにより、生成される PDF ファイルのサイズが削減され、レンダリングのパフォーマンスが向上します。必ずドキュメントへの正しいパスを指定し、必要に応じてメタファイルのレンダリング オプションを構成してください。

### よくある質問

#### Q: PDF ドキュメント内の WMF フォントのサイズをメタファイル サイズに変更するとは何ですか?
A: PDF ドキュメント内の WMF フォントのメタファイル サイズへのサイズ変更は、PDF ドキュメントへの変換時に WMF フォントをメタファイル サイズに合わせて拡大縮小するかどうかを制御する機能です。この機能を有効にすると、WMF フォントがメタファイルのサイズに合わせて拡大縮小され、生成される PDF ドキュメントのサイズが小さくなる可能性があります。

#### Q: Aspose.Words for .NET を使用して、PDF ドキュメント内の WMF フォントのメタファイル サイズへのサイズ変更を有効または無効にするにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメント内の WMF フォントのメタファイル サイズへのサイズ変更を有効または無効にするには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

を使用して、処理するドキュメントをロードします。`Document`クラスを指定し、指定したドキュメント ディレクトリ内の Word ドキュメントへのパスを指定します。

のインスタンスを作成して、メタファイルのレンダリング オプションを構成します。`MetafileRenderingOptions`クラスと設定`ScaleWmfFontsToMetafileSize`財産を`true` WMF フォントをメタファイル サイズに合わせてスケーリングできるようにするか、`false`この機能を無効にするには、

のインスタンスを作成して、PDF として保存オプションを構成します。`PdfSaveOptions`クラスを使用し、前に構成したメタファイル レンダリング オプションを使用します。

ドキュメントを PDF 形式で保存するには、`Save`の方法`Document`パスと保存オプションを指定するクラス。

#### Q: PDF ドキュメント内の WMF フォントのサイズをメタファイル サイズに変更すると、どのような利点がありますか?
A: PDF ドキュメント内の WMF フォントのサイズをメタファイル サイズに変更する利点は次のとおりです。

PDF ファイル サイズの縮小: WMF フォントのサイズをメタファイル サイズに変更すると、フォント サイズをメタファイルのニーズに適合させることにより、生成される PDF ドキュメントのサイズを縮小できます。

パフォーマンスの向上: WMF フォントのサイズをメタファイルのサイズに調整することにより、PDF ドキュメントのレンダリングがより高速かつ効率的に行われます。