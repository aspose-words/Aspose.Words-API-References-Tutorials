---
title: ブックマークに移動 Word 文書内で終了
linktitle: ブックマークに移動 Word 文書内で終了
second_title: Aspose.Words ドキュメント処理 API
description: このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word ドキュメントのブックマークの末尾に移動する方法を学びます。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/move-to-bookmark-end/
---
この例では、Aspose.Words for .NET のブックマーク末尾に移動機能を調べます。 Aspose.Words は、開発者が Word ドキュメントをプログラムで作成、変更、変換できるようにする強力なドキュメント操作ライブラリです。ブックマークの末尾に移動機能を使用すると、ドキュメント内の特定のブックマークの末尾に移動し、その後にコンテンツを追加できます。

## 環境のセットアップ

実装の詳細を掘り下げる前に、Aspose.Words for .NET を使用するために必要な環境がセットアップされていることを確認してください。以下のものがあることを確認してください。

- Aspose.Words for .NET ライブラリの動作するインストール
- C# プログラミング言語の基本的な知識
- .NET開発環境へのアクセス

## Aspose.Words for .NET のブックマーク末尾に移動機能について

ブックマークの末尾に移動機能を使用すると、Aspose.Words for .NET を使用して Word 文書内のブックマークの末尾に移動できます。この機能は、ドキュメント内の特定のブックマークの後にプログラムでコンテンツを追加する場合に便利です。

## ソースコードをステップバイステップで解説

Aspose.Words for .NET のブックマーク末尾に移動機能の使用方法を理解するために、提供されたソース コードを段階的に分析してみましょう。

## ステップ 1: ドキュメントとドキュメント ビルダーの初期化

まず、初期化する必要があります`Document`そして`DocumentBuilder`オブジェクト:

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: ブックマークの最後に移動する

ブックマークの末尾に移動するには、`MoveToBookmark`の方法`DocumentBuilder`クラス：

```csharp
builder.MoveToBookmark("MyBookmark1", false, true);
```

の`MoveToBookmark`このメソッドは 3 つのパラメータを取ります。
- ブックマーク名: 移動先のブックマークの名前を入力します。
-  IsBookmarkStart: に設定します`false`ブックマークの最後に移動します。
-  IsBookmarkEnd: に設定します`true`をクリックして、ブックマークの最後に移動することを示します。

## ステップ 3: ブックマークの最後にコンテンツを追加する

ブックマークの端に移動すると、ブックマークによって提供されるさまざまな方法を使用してコンテンツを追加できます。`DocumentBuilder`クラス。この例では、`Writeln`テキスト行を書き込むメソッド:

```csharp
builder.Writeln("This is a bookmark.");
```

の`Writeln`メソッドは、指定されたテキストを新しい段落として現在の位置に追加します。`DocumentBuilder`.

### Aspose.Words for .NET を使用したブックマーク終了への移動のソース コード例

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToBookmark("MyBookmark1", false, true);
builder.Writeln("This is a bookmark.");
```

## 結論

Aspose.Words for .NET のブックマーク末尾に移動機能を調べました。ブックマークの末尾に移動し、提供されたソース コードを使用してプログラムでコンテンツを追加する方法を学習しました。この機能により、Aspose.Words for .NET を使用して Word ドキュメントを柔軟に操作できます。

### Word 文書のブックマーク末尾への移動に関する FAQ

#### Q: Aspose.Words for .NET のブックマーク末尾に移動機能の目的は何ですか?

A: Aspose.Words for .NET のブックマークの末尾に移動機能を使用すると、開発者は Word 文書内の特定のブックマークの末尾にプログラム的に移動できます。この機能は、ドキュメント内の特定のブックマークの後にコンテンツを追加する場合に便利です。

#### Q: ブックマークの最後に移動機能を使用するための前提条件は何ですか?

A: ブックマークの最後に移動機能を使用するには、次の前提条件が必要です。
1. Aspose.Words for .NET ライブラリの動作するインストール。
2. C# プログラミング言語の基本的な知識。
3. .NET 開発環境へのアクセス。

#### Q: この機能を使用してブックマークの先頭に移動できますか?

 A: はい、使用できます。`MoveToBookmark`パラメータを使用したメソッド`IsBookmarkStart`に設定`true`ブックマークの先頭に移動します。

#### Q: 指定したブックマークがドキュメント内に存在しない場合はどうなりますか?

 A: 指定したブックマークがドキュメント内に存在しない場合、`MoveToBookmark`このメソッドは何の効果も持たず、ブックマークの最後にコンテンツは追加されません。

#### Q: ブックマークの先頭にコンテンツを追加することはできますか?

 A: はい、設定することで可能です。`IsBookmarkStart`パラメータを`true`をクリックすると、ブックマークの先頭に移動して、その前にコンテンツを追加できます。