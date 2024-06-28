---
title: ハイフネーションコールバック
linktitle: ハイフネーションコールバック
second_title: Aspose.Words ドキュメント処理 API
description: この包括的なステップバイステップ ガイドを使用して、Aspose.Words for .NET でハイフネーション コールバックを実装し、ドキュメントの書式設定を強化する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-hyphenation/hyphenation-callback/
---

## 導入

ちょっと、そこ！特にハイフネーションが必要な言語を扱う場合、テキストの書式設定の複雑さに巻き込まれたことはありますか?あなたは一人じゃない。ハイフネーションはテキストを適切にレイアウトするために重要ですが、少し頭の痛い問題になる場合があります。でも、どうだろう？ Aspose.Words for .NET があなたの味方です。この強力なライブラリを使用すると、コールバック メカニズムによるハイフネーションの処理など、テキストの書式設定をシームレスに管理できます。興味をそそられましたか? Aspose.Words for .NET を使用してハイフネーション コールバックを実装する方法の核心を見てみましょう。

## 前提条件

コードに実際に取り組む前に、必要なものがすべて揃っていることを確認しましょう。

1.  Aspose.Words for .NET: ライブラリがあることを確認してください。あなたはできる[ここからダウンロードしてください](https://releases.aspose.com/words/net/).
2. IDE: Visual Studio のような開発環境。
3. C# の基礎知識: C# と .NET Framework についての理解。
4. ハイフネーション辞書: 使用する予定の言語のハイフネーション辞書。
5.  Aspose ライセンス: 有効な Aspose ライセンス。を得ることができます[仮免許](https://purchase.aspose.com/temporary-license/)持っていない場合。

## 名前空間のインポート

まず最初に、必要な名前空間をインポートしましょう。これにより、コードが Aspose.Words から必要なすべてのクラスとメソッドにアクセスできるようになります。

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## ステップ 1: ハイフネーション コールバックを登録する

まず、ハイフネーション コールバックを登録する必要があります。ここで、カスタム ハイフネーション ロジックを使用するように Aspose.Words に指示します。

```csharp
try
{
    //ハイフネーションコールバックを登録します。
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

ここでは、カスタム コールバックのインスタンスを作成し、それを割り当てています。`Hyphenation.Callback`.

## ステップ 2: ドキュメント パスを定義する

次に、ドキュメントを保存するディレクトリを定義する必要があります。このパスからドキュメントをロードおよび保存するため、これは非常に重要です。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントへの実際のパスを含めます。

## ステップ 3: ドキュメントをロードする

次に、ハイフネーションが必要なドキュメントをロードしましょう。

```csharp
Document document = new Document(dataDir + "German text.docx");
```

ここでは、ドイツ語のテキストドキュメントをロードしています。交換できます`"German text.docx"`ドキュメントのファイル名を付けます。

## ステップ 4: ドキュメントを保存する

ドキュメントをロードした後、プロセス内でハイフネーション コールバックを適用して、ドキュメントを新しいファイルに保存します。

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

この行は、ハイフネーションが適用された PDF としてドキュメントを保存します。

## ステップ 5: ハイフネーション辞書の欠落例外の処理

場合によっては、ハイフネーション辞書が見つからないという問題が発生することがあります。それを処理しましょう。

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

このブロックでは、辞書の欠落に関連する特定の例外をキャッチし、メッセージを出力します。

## ステップ 6: カスタム ハイフネーション コールバック クラスを実装する

それでは、実装してみましょう`CustomHyphenationCallback`ハイフネーション辞書のリクエストを処理するクラス。

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        //要求された言語の辞書を登録します。
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

このクラスでは、`RequestDictionary`ハイフネーション辞書が必要になるたびにメソッドが呼び出されます。言語をチェックして適切な辞書を登録します。

## 結論

そして、それができました！ Aspose.Words for .NET でハイフネーション コールバックを実装する方法を学習しました。これらの手順に従うことで、言語に関係なく、ドキュメントを美しくフォーマットすることができます。英語、ドイツ語、その他の言語を扱う場合でも、この方法を使用するとハイフネーションを簡単に処理できます。

## よくある質問

### Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者がプログラムでドキュメントを作成、変更、変換できるようにする強力なドキュメント操作ライブラリです。

### 文書の書式設定においてハイフネーションが重要なのはなぜですか?
ハイフネーションを使用すると、適切な場所で単語が区切られるため、テキストのレイアウトが改善され、文書がより読みやすく視覚的に魅力的になります。

### Aspose.Words を無料で使用できますか?
 Aspose.Words は無料トライアルを提供しています。がんばって[ここ](https://releases.aspose.com/).

### ハイフネーション辞書を入手するにはどうすればよいですか?
さまざまなオンライン リソースからハイフネーション辞書をダウンロードしたり、必要に応じて独自の辞書を作成したりできます。

### ハイフネーション辞書が見つからない場合はどうなりますか?
辞書が見つからない場合は、`RequestDictionary`メソッドは例外をスローします。これを処理してユーザーに通知したり、フォールバックを提供したりできます。