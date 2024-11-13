---
title: 単語の修正タイプを取得する
linktitle: 単語の修正タイプを取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の単語の修正タイプを取得する方法を学びます。このステップ バイ ステップ ガイドは、文書の修正を効率的に処理するのに役立ちます。
type: docs
weight: 10
url: /ja/net/working-with-revisions/get-revision-types/
---
## 導入

ドキュメントの改訂の海にどっぷりつかって、誰が何をいつ移動したのか分からなくなったことはありませんか? あなただけではありません。ドキュメントの改訂を処理するのは、特に大規模なドキュメントを扱う場合には、面倒な作業になることがあります。しかし、心配はいりません。Aspose.Words for .NET を使用すると、これらの改訂を簡単に識別して管理できます。このガイドでは、Aspose.Words for .NET を使用して Word ドキュメント内の単語の改訂タイプを取得する方法を、ステップ バイ ステップで説明します。さあ、シートベルトを締めて、始めましょう!

## 前提条件

実際にコードに取り掛かる前に、いくつか必要なものがあります。

1.  Aspose.Words for .NETライブラリ:まだダウンロードしていない場合は、こちらからダウンロードしてください。[ここ](https://releases.aspose.com/words/net/).
2. 開発環境: Visual Studio またはその他の .NET 互換 IDE。
3. C# の基礎知識: C# プログラミング言語を理解していると役立ちます。
4. 修正を加えたWord文書:`.docx`コードをテストするための変更追跡ファイル。

## 名前空間のインポート

開始するには、C# プロジェクトに必要な名前空間をインポートする必要があります。これにより、Aspose.Words for .NET によって提供される機能にアクセスできるようになります。

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

理解と実装を容易にするために、例を複数のステップに分解してみましょう。

## ステップ1: ドキュメントディレクトリを設定する

まず最初に、ドキュメント ディレクトリへのパスを定義する必要があります。ここに、変更を加えた Word ドキュメントが保存されます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメント フォルダーへの実際のパスを入力します。

## ステップ2: Word文書を読み込む

次に、Word 文書をプロジェクトに読み込む必要があります。この文書には、分析するリビジョンが含まれている必要があります。

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

ファイルが`Revisions.docx`指定されたディレクトリに存在します。

## ステップ3: 段落コレクションにアクセスする

ドキュメントが読み込まれたら、ドキュメント本体の最初のセクション内の段落にアクセスする必要があります。これにより、各段落を反復処理して変更を確認することができます。

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## ステップ4: 段落を繰り返して修正箇所を確認する

ここで魔法が起こります。各段落を反復処理して、移動 (削除または挿入) されたかどうかを確認します。

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

このループは各段落を巡回し、`IsMoveFromRevision`そして`IsMoveToRevision`段落が移動 (削除) されたか、移動 (挿入) されたかを判断するプロパティ。

## 結論

これで完了です。わずか数行のコードで、Aspose.Words for .NET を使用して Word 文書内の変更の種類を簡単に識別できます。この強力なライブラリにより、文書の変更を簡単に処理できるため、より重要なタスクに集中できます。 

## よくある質問

### Aspose.Words for .NET を使用して、特定のユーザーによる変更を追跡できますか?

はい、Aspose.Words for .NET には、変更の作成者を含むリビジョンの詳細にアクセスする機能が用意されています。

### Aspose.Words for .NET の無料試用版はありますか?

もちろんです！無料トライアルをご利用いただけます[ここ](https://releases.aspose.com/).

### Aspose.Words for .NET の一時ライセンスを適用するにはどうすればよいですか?

一時ライセンスの申請と申請は、[ここ](https://purchase.aspose.com/temporary-license/).

### Aspose.Words for .NET の詳細なドキュメントはどこで入手できますか?

詳細なドキュメントは、[Aspose ウェブサイト](https://reference.aspose.com/words/net/).

### Aspose.Words for .NET を非商用プロジェクトで使用できますか?

はい、Aspose.Words for .NET は商用プロジェクトと非商用プロジェクトの両方で使用できますが、ライセンス条件を必ず確認してください。