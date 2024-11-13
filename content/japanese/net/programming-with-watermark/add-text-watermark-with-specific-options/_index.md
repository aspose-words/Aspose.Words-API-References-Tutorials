---
title: 特定のオプションでテキスト透かしを追加する
linktitle: 特定のオプションでテキスト透かしを追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、特定のオプションで Word 文書にテキスト透かしを追加する方法を学びます。フォント、サイズ、色、レイアウトを簡単にカスタマイズします。
type: docs
weight: 10
url: /ja/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## 導入

透かしは、Word 文書にスタイリッシュかつ機能的な追加要素として使用できます。文書を機密としてマークしたり、パーソナライズされたタッチを追加したりすることができます。このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にテキスト透かしを追加する方法について説明します。フォント ファミリ、フォント サイズ、色、レイアウトなど、構成できる特定のオプションについて詳しく説明します。最後には、ニーズにぴったり合うように文書の透かしをカスタマイズできるようになります。では、コード エディターを手に取って、始めましょう。

## 前提条件

始める前に、以下のものを用意しておいてください。

1.  Aspose.Words for .NET ライブラリ: Aspose.Words ライブラリをインストールする必要があります。まだインストールしていない場合は、次の場所からダウンロードできます。[Aspose.Words ダウンロード リンク](https://releases.aspose.com/words/net/).
2. C# の基本的な理解: このチュートリアルでは、プログラミング言語として C# を使用します。C# 構文の基本的な理解が役立ちます。
3. .NET 開発環境: .NET アプリケーションを作成して実行できる開発環境 (Visual Studio など) が設定されていることを確認します。

## 名前空間のインポート

Aspose.Words を使用するには、プロジェクトに必要な名前空間を含める必要があります。インポートする必要があるものは次のとおりです。

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## ステップ1: ドキュメントを設定する

まず、作業したい文書を読み込む必要があります。このチュートリアルでは、サンプル文書を使用します。`Document.docx`このドキュメントが指定したディレクトリに存在することを確認してください。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

このステップでは、ドキュメントが配置されているディレクトリを定義し、それを`Document`クラス。

## ステップ2: 透かしオプションを設定する

次に、テキスト透かしのオプションを設定します。フォント ファミリ、フォント サイズ、色、レイアウトなど、さまざまな側面をカスタマイズできます。これらのオプションを設定しましょう。

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

各オプションの機能は次のとおりです。
- `FontFamily`: 透かしテキストのフォントを指定します。
- `FontSize`: 透かしテキストのサイズを設定します。
- `Color`: 透かしテキストの色を定義します。
- `Layout`透かしの方向 (水平または斜め) を決定します。
- `IsSemitrasparent`: 透かしを半透明にするかどうかを設定します。

## ステップ3: 透かしテキストを追加する

次に、以前に設定したオプションを使用して、ドキュメントに透かしを適用します。この手順では、透かしのテキストを「テスト」に設定し、定義したオプションを適用します。

```csharp
doc.Watermark.SetText("Test", options);
```

このコード行は、指定されたオプションを適用して、ドキュメントに「Test」というテキストの透かしを追加します。

## ステップ4: ドキュメントを保存する

最後に、新しい透かしを適用したドキュメントを保存します。元のドキュメントが上書きされないように、新しい名前で保存することもできます。

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

このコード スニペットは、変更されたドキュメントを新しいファイル名で同じディレクトリに保存します。

## 結論

Aspose.Words for .NET を使用して Word 文書にテキスト透かしを追加することは、管理しやすい手順に分解すれば簡単なプロセスです。このチュートリアルでは、フォント、サイズ、色、レイアウト、透明度など、さまざまな透かしオプションを構成する方法を学習しました。これらのスキルがあれば、ニーズに合わせて文書をカスタマイズしたり、機密性やブランド化などの重要な情報を含めたりすることができます。

ご質問やご不明な点がございましたら、お気軽に[Aspose.Words ドキュメント](https://reference.aspose.com/words/net/)または、[Aspose サポート フォーラム](https://forum.aspose.com/c/words/8)さらに詳しいヘルプについては、

## よくある質問

### 透かしに異なるフォントを使用できますか?

はい、システムにインストールされているフォントを任意に選択できます。`FontFamily`の財産`TextWatermarkOptions`.

### 透かしの色を変更するにはどうすればよいですか?

透かしの色は、`Color`の財産`TextWatermarkOptions`いずれにせよ`System.Drawing.Color`価値。

### 文書に複数の透かしを追加することは可能ですか?

Aspose.Words では、一度に 1 つの透かしを追加できます。複数の透かしを追加するには、透かしを順番に作成して適用する必要があります。

### 透かしの位置を調整できますか？

の`WatermarkLayout`プロパティは方向を決定しますが、正確な位置調整は直接サポートされていません。正確な配置には他の手法を使用する必要がある場合があります。

### 半透明の透かしが必要な場合はどうすればいいですか?

設定する`IsSemitrasparent`財産に`true`透かしを半透明にします。