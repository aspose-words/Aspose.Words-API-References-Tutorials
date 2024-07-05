---
title: オートリンク
linktitle: オートリンク
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して自動リンクを挿入する方法をステップバイステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/autolink/
---

この例では、Aspose.Words for .NET で「自動リンク」機能を使用する方法について説明します。この機能を使用すると、ドキュメントにハイパーリンクを自動的に挿入できます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: ハイパーリンクの挿入

ハイパーリンクを挿入するには、`InsertHyperlink`ドキュメント ジェネレーターのメソッド。リンクに表示する URL とテキストを指定します。

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## ステップ3: メールアドレスをリンクとして挿入する

「mailto:」プレフィックスを使用して、電子メール アドレスをリンクとして挿入することもできます。これにより、ユーザーはリンクをクリックしてデフォルトの電子メール クライアントを開くことができます。

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## ステップ4: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。

### Aspose.Words for .NET を使用した Autolink のサンプル ソース コード


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//ハイパーリンクを挿入します。
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


おめでとうございます！これで、Aspose.Words for .NET で「自動リンク」機能を使用する方法を学習しました。


### よくある質問

#### Q: Aspose.Words で URL アドレスへの自動リンクを作成するにはどうすればよいですか?

 A: Aspose.WordsでURLアドレスへの自動リンクを作成するには、`<a>`タグを付ける`href`URLアドレスを含む属性。例えば、`<a href="https://www.aspose.com">https://www.aspose.com</a>` 「https://www.aspose.com」に自動的にリンクします。

#### Q: Aspose.Words で自動リンクの表示テキストをカスタマイズすることは可能ですか?

 A: はい、Aspose.Wordsでは自動リンクの表示テキストをカスタマイズできます。表示テキストとしてURLアドレスを使用する代わりに、URLとURLの間の内容を置き換えることで他のテキストを使用できます。`<a>`タグ。例えば、`<a href="https://www.aspose.com">Click here</a>` 「ここをクリック」というテキストを自動リンクとして表示します。

#### Q: Aspose.Words の自動リンクに追加の属性を追加するにはどうすればよいですか?

A: Aspose.Wordsの自動リンクに追加の属性を追加するには、`<a>`タグ。例えば、`<a href="https://www.aspose.com" target="_blank">Link</a>`リンクを新しいウィンドウまたはタブで開くには、` attribute target="_blank"`.