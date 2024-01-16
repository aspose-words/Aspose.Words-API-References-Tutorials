---
title: オートリンク
linktitle: オートリンク
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドを使用して自動リンクを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/autolink/
---

この例では、Aspose.Words for .NET で「オートリンク」機能を使用する方法を説明します。この機能を使用すると、ドキュメントにハイパーリンクを自動的に挿入できます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: ハイパーリンクの挿入

を使用してハイパーリンクを挿入できます。`InsertHyperlink`ドキュメントジェネレーターのメソッド。 URL とリンクに表示するテキストを指定します。

```csharp
builder.InsertHyperlink("https://www.aspose.com」、「https://www.aspose.com」、false);
```

## ステップ 3: 電子メール アドレスをリンクとして挿入する

「mailto:」プレフィックスを使用して、電子メール アドレスをリンクとして挿入することもできます。これにより、ユーザーはリンクをクリックしてデフォルトの電子メール クライアントを開くことができるようになります。

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## ステップ 4: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。

### Aspose.Words for .NET を使用したオートリンクのソース コード例


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//ハイパーリンクを挿入します。
builder.InsertHyperlink("https://www.aspose.com」、「https://www.aspose.com」、false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


おめでとうございます！これで、Aspose.Words for .NET で「オートリンク」機能を使用する方法を学習しました。


### よくある質問

#### Q: Aspose.Words で URL アドレスへの自動リンクを作成するにはどうすればよいですか?

A: Aspose.Words で URL アドレスへの自動リンクを作成するには、`<a>`のタグを付けます`href`URL アドレスを含む属性。たとえば、次のように使用できます`<a href="https://www.aspose.com">https://www.aspose.com</a>`「https://www.aspose.com」に自動的にリンクします。

#### Q: Aspose.Words で自動リンクの表示テキストをカスタマイズすることはできますか?

 A: はい、Aspose.Words で自動リンクの表示テキストをカスタマイズできます。 URL アドレスを表示テキストとして使用する代わりに、次の内容を置き換えることにより、他のテキストを使用できます。`<a>`タグ。たとえば、次のように使用できます`<a href="https://www.aspose.com">Click here</a>`「ここをクリック」というテキストを自動リンクとして表示します。

#### Q: Aspose.Words のオートリンクに属性を追加するにはどうすればよいですか?

 A: Aspose.Words の自動リンクに追加の属性を追加するには、`<a>`鬼ごっこ。たとえば、次のように使用できます`<a href="https://www.aspose.com" target="_blank">Link</a>`新しいウィンドウまたはタブでリンクを開くには、` attribute target="_blank"`.