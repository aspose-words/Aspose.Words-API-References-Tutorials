---
title: リンク
linktitle: リンク
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してリンクを挿入する方法を学びます。ステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/working-with-markdown/link/
---

この例では、Aspose.Words for .NET でリンク機能を使用する方法を説明します。リンクは、Web サイトまたは他のドキュメントへのクリック可能な参照を作成するために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: リンクを挿入する

を使用してリンクを挿入できます`Insertlink`ドキュメントジェネレーターのメソッド。リンクテキスト (ここでは「Aspose」) とリンク先 URL を指定する必要があります。

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com"、false);
```

### Aspose.Words for .NET を使用したリンクのソース コードの例


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//リンクを挿入します。
builder.Insertlink("Aspose", "https://www.aspose.com"、false);
```
おめでとうございます！これで、Aspose.Words for .NET でリンク機能を使用する方法を学習しました。


### よくある質問

#### Q: Aspose.Words で URL にリンクするにはどうすればよいですか?

 A: Aspose.Words の URL アドレスにリンクするには、`<a>`のタグを付けます`href`URL アドレスを含む属性。たとえば、次のように使用できます`<a href="https://www.aspose.com">Click Here</a>` URL「https://www.example.com」に「ここをクリックしてください」という表示テキストを含むハイパーリンクを設定します。

#### Q: Aspose.Words の内部ブックマークにリンクすることはできますか?

 A: はい、Aspose.Words の内部ブックマークにリンクすることができます。使用できます`<a>`のタグを付けます`href`ハッシュ (#) が前に付いたブックマークの名前を含む属性。例えば、`<a href="#bookmark1">Go to bookmark 1</a>`ドキュメント内の「bookmark1」という名前のブックマークにリンクします。

#### Q: Aspose.Words でリンクの表示テキストをカスタマイズするにはどうすればよいですか?

A: Aspose.Words でリンクの表示テキストをカスタマイズするには、`<a>`タグ。例えば、`<a href="https://www.aspose.com">Click here</a>` 「ここをクリック」というテキストがハイパーリンクとして表示されます。

#### Q: Aspose.Words でリンクのターゲットを指定できますか?

 A: はい、Aspose.Words でリンクのターゲットを指定するには、`target`の属性`<a>`鬼ごっこ。例えば、`<a href="https://www.aspose.com" target="_blank">Open in new window</a>`リンクが新しいウィンドウまたはタブで開きます。