---
title: ハイフネーションコールバック
linktitle: ハイフネーションコールバック
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でハイフネーション コールバックを使用して単語のハイフネーションを処理する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-hyphenation/hyphenation-callback/
---

このステップバイステップのチュートリアルでは、Aspose.Words for .NET のハイフネーション コールバック機能の使用方法を説明します。提供されている C# ソース コードについて説明し、それを独自のプロジェクトに実装する方法を示します。

開始するには、開発環境に Aspose.Words for .NET がインストールされ、構成されていることを確認してください。まだライブラリをダウンロードしてインストールしていない場合は、次からライブラリをダウンロードしてインストールします。[Aspose.Releases]https://releases.aspose.com/words/net/。

## ステップ 1: ハイフネーションのリマインダーを保存する

まず、カスタム メソッドを使用してハイフネーション コールバックを登録します。`CustomHyphenationCallback`クラス。これにより、独自のルールに従って単語のハイフネーションを処理できるようになります。

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

を実装していることを確認してください`CustomHyphenationCallback`あなたの特定のニーズに応じたクラス。

## ステップ 2: ドキュメントをロードしてハイフネーションを適用する

次に、指定したディレクトリからドキュメントを読み込み、Aspose.Words を使用して単語をハイフネーションします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## ステップ 3: 辞書欠落エラーの処理

ハイフネーション辞書が見つからない場合は、対応する例外をキャッチし、エラー メッセージを表示します。

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## ステップ 4: ハイフネーション リマインダーをクリーンアップして無効にする

最後に、清潔を保つために、ハイフネーションのリマインダーをオフにするには、次の手順を実行します。

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

これにより、処理終了後にハイフネーションのリマインダーがクリーンアップされ、無効になります。

それで ！ Aspose.Words for .NET でハイフネーション コールバックを正常に使用できました。

### Aspose.Words for .NET を使用したハイフネーション コールバックのサンプル ソース コード

```csharp
try
{
	 //ハイフネーションコールバックを登録します。
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

このコードを独自のプロジェクトで自由に使用し、特定のニーズに合わせて変更してください。

### よくある質問

#### Q: Aspose.Words の音節化リマインダーとは何ですか?

A: Aspose.Words の音節化リマインダーは、ドキュメント内の単語の音節化方法をカスタマイズできる機能です。音節化リマインダーを使用すると、単語の音節化に関するカスタム ルールを指定できます。これは、デフォルトの音節化では望ましい結果が得られない特定の言語や特定のシナリオに役立ちます。

#### Q: Aspose.Words で音節化リマインダーを設定するにはどうすればよいですか?

 A: Aspose.Words でハイフネーション コールバックを定義するには、`HyphenationCallback`インターフェイスと実装`HandleWord()`方法。このメソッドは、音節化中に出現した単語ごとに呼び出されます。カスタムの音節化ルールを適用して、音節化された単語を返すことができます。次に、次を使用してハイフネーション コールバックをバインドできます。`Document.HyphenationCallback`ドキュメントのプロパティ。

#### Q: Aspose.Words で音節化リマインダーを使用する利点は何ですか?

A: Aspose.Words で音節化リマインダーを使用する利点は、文書内の単語の音節化方法をカスタマイズできることです。これにより、特にデフォルトの音節化では望ましい結果が得られない特定の言語やシナリオで、音節化をより詳細に制御できるようになります。各単語に特定のルールを適用して、ニーズに応じて正確な音節化を行うことができます。

#### Q: シラビゼーション リマインダーの使用が役立つ一般的なシナリオにはどのようなものがありますか?

A: シラビゼーション ブースターの使用は、次のようないくつかのシナリオで役立ちます。
- 特定の音節化ルールを持つ特定の言語の単語の音節化。
- 頭字語または専門用語に対するパーソナライズされた音節化ルールの適用。
- 文体の好みや活字の標準に従って音節化を適応させる。

#### Q: Aspose.Words の音節化リマインダーを使用してカスタム音節化をテストするにはどうすればよいですか?

 A: Aspose.Words の音節リマインダーを使用してカスタム音節化をテストするには、カスタム音節化ルールを適用する単語を含むテスト ドキュメントを作成できます。次に、カスタムの音節化コールバックを設定して、`Document.Range.Replace()`メソッドを使用して文書内の単語を置換し、`Hyphenate()`の方法`Hyphenation`単語の音節化を取得するクラス。その後、音節間にハイフンを追加するなど、必要に応じて音節化された単語をフォーマットできます。