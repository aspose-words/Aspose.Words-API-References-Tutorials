---
title: リンク
linktitle: リンク
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してリンクを挿入する方法を学びます。ステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/working-with-markdown/link/
---

この例では、Aspose.Words for .NET でリンク機能を使用する方法について説明します。リンクは、Web サイトや他のドキュメントへのクリック可能な参照を作成するために使用されます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: リンクの挿入

リンクを挿入するには`InsertHyperlink`ドキュメント ジェネレーターのメソッド。リンク テキスト (ここでは "Aspose") とリンク先の URL を指定する必要があります。

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", 偽);
```

### Aspose.Words for .NET とのリンクのサンプル ソース コード


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//リンクを挿入します。
builder.InsertHyperlink("Aspose", "https://www.aspose.com", 偽);
```
おめでとうございます！これで、Aspose.Words for .NET のリンク機能の使用方法を学習しました。


### よくある質問

#### Q: Aspose.Words で URL にリンクするにはどうすればよいですか?

 A: Aspose.WordsでURLアドレスにリンクするには、`<a>`タグを付ける`href`URLアドレスを含む属性。例えば、`<a href="https://www.aspose.com">Click Here</a>` 「ここをクリック」という表示テキストを含む URL「https://www.example.com」へのハイパーリンクを作成します。

#### Q: Aspose.Words で内部ブックマークにリンクすることは可能ですか?

 A: はい、Aspose.Wordsの内部ブックマークにリンクすることは可能です。`<a>`タグを付ける`href`ハッシュ（#）に続くブックマーク名を含む属性。例：`<a href="#bookmark1">Go to bookmark 1</a>`ドキュメント内の「bookmark1」という名前のブックマークにリンクします。

#### Q: Aspose.Words でリンクの表示テキストをカスタマイズするにはどうすればよいですか?

 A: Aspose.Wordsでリンクの表示テキストをカスタマイズするには、`<a>`タグ。例えば、`<a href="https://www.aspose.com">Click here</a>` 「ここをクリック」というテキストがハイパーリンクとして表示されます。

#### Q: Aspose.Words でリンクのターゲットを指定できますか?

A: はい、Aspose.Wordsでは、`target`の属性`<a>`タグ。例えば、`<a href="https://www.aspose.com" target="_blank">Open in new window</a>`リンクは新しいウィンドウまたはタブで開きます。