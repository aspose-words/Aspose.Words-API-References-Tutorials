---
title: Aspose.Words for Java でのリビジョンの使用
linktitle: リビジョンの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java のリビジョンを効率的に使用する方法を学びます。開発者向けのステップバイステップのガイド。ドキュメント管理を最適化します。
type: docs
weight: 22
url: /ja/java/using-document-elements/using-revisions/
---

Java 開発者がドキュメントの操作を検討しており、リビジョン管理を実装する必要がある場合、Aspose.Words for Java はリビジョンを効果的に管理するための強力なツール セットを提供します。このチュートリアルでは、Aspose.Words for Java でのリビジョンの使用方法を段階的に説明します。 

## 1. Aspose.Words for Java の概要

Aspose.Words for Java は、Microsoft Word を必要とせずに Word ドキュメントを作成、変更、操作できる堅牢な Java API です。これは、ドキュメント内でリビジョンを実装する必要がある場合に特に便利です。

## 2. 開発環境のセットアップ

Aspose.Words for Java の使用に入る前に、開発環境をセットアップする必要があります。必要な Java 開発ツールと Aspose.Words for Java ライブラリがインストールされていることを確認してください。

## 3. 新しいドキュメントの作成

まずは、Aspose.Words for Java を使用して新しい Word ドキュメントを作成しましょう。その方法は次のとおりです。

```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
```

## 4. ドキュメントへのコンテンツの追加

空のドキュメントが完成したので、そこにコンテンツを追加できます。この例では、3 つの段落を追加します。

```java
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
```

## 5. リビジョン追跡の開始

ドキュメントのリビジョンを追跡するには、次のコードを使用できます。

```java
doc.startTrackRevisions("John Doe", new Date());
```

## 6. 修正の実施

別の段落を追加して修正してみましょう。

```java
para = body.appendParagraph("Paragraph 4. ");
```

## 7. 改訂の承認と拒否

Aspose.Words for Java を使用して、ドキュメントのリビジョンを承認または拒否できます。ドキュメントの生成後、改訂は Microsoft Word で簡単に管理できます。

## 8. リビジョン追跡の停止

リビジョンの追跡を停止するには、次のコードを使用します。

```java
doc.stopTrackRevisions();
```

## 9. 文書の保存

最後に、ドキュメントを保存します。

```java
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
```

## 10. 結論

このチュートリアルでは、Aspose.Words for Java でのリビジョンの使用の基本について説明しました。ドキュメントの作成、コンテンツの追加、リビジョン追跡の開始と停止、ドキュメントの保存の方法を学習しました。

これで、Aspose.Words for Java を使用して Java アプリケーションのリビジョンを効果的に管理するために必要なツールが手に入りました。

## 完全なソースコード
```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
//最初の段落にテキストを追加し、さらに 2 つの段落を追加します。
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
// つの段落がありますが、いずれのタイプの改訂としても登録されていません
//リビジョンの追跡中にドキュメント内のコンテンツを追加または削除すると、
//それらは文書内にそのように表示され、承認または拒否できます。
doc.startTrackRevisions("John Doe", new Date());
//この段落はリビジョンであり、それに応じて「IsInsertRevision」フラグが設定されます。
para = body.appendParagraph("Paragraph 4. ");
Assert.assertTrue(para.isInsertRevision());
//ドキュメントの段落コレクションを取得し、段落を削除します。
ParagraphCollection paragraphs = body.getParagraphs();
Assert.assertEquals(4, paragraphs.getCount());
para = paragraphs.get(2);
para.remove();
//リビジョンを追跡しているため、段落は文書内にまだ存在しており、「IsDeleteRevision」が設定されています。
//すべてのリビジョンが承認または拒否されるまで、Microsoft Word ではリビジョンとして表示されます。
Assert.assertEquals(4, paragraphs.getCount());
Assert.assertTrue(para.isDeleteRevision());
//リビジョン削除の段落は、変更を受け入れると削除されます。
doc.acceptAllRevisions();
Assert.assertEquals(3, paragraphs.getCount());
Assert.assertEquals(para.getRuns().getCount(), 0); //Is.Emptyでした
//リビジョンの追跡を停止すると、このテキストは通常のテキストとして表示されます。
//ドキュメントが変更された場合、リビジョンはカウントされません。
doc.stopTrackRevisions();
//文書を保存します。
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
  
```

## よくある質問

### 1. Aspose.Words for Java を他のプログラミング言語で使用できますか?

いいえ、Aspose.Words for Java は Java 開発用に特別に設計されています。

### 2. Aspose.Words for Java は Microsoft Word のすべてのバージョンと互換性がありますか?

はい、Aspose.Words for Java は、さまざまなバージョンの Microsoft Word と互換性があるように設計されています。

### 3. 既存の Word 文書のリビジョンを追跡できますか?

はい、Aspose.Words for Java を使用して、既存の Word ドキュメントのリビジョンを追跡できます。

### 4. Aspose.Words for Java を使用するためのライセンス要件はありますか?

はい、プロジェクトで Aspose.Words for Java を使用するにはライセンスを取得する必要があります。あなたはできる[ここからライセンスにアクセスしてください](https://purchase.aspose.com/buy).

### 5. Aspose.Words for Java のサポートはどこで見つけられますか?

ご質問や問題がある場合は、次のサイトにアクセスしてください。[Aspose.Words for Java サポート フォーラム](https://forum.aspose.com/).

今すぐ Aspose.Words for Java を使い始めて、ドキュメント管理プロセスを合理化してください。
