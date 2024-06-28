---
title: ドキュメントのテキストの方向
linktitle: ドキュメントのテキストの方向
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内のテキストの方向を指定する方法を学びます。右から左に記述する言語の表示を改善しました。
type: docs
weight: 10
url: /ja/net/programming-with-txtloadoptions/document-text-direction/
---

このチュートリアルでは、Aspose.Words for .NET の「ドキュメント テキスト方向」機能用に提供されている C# ソース コードを調べます。この機能を使用すると、ドキュメント内のテキストの方向を指定できます。これは、ヘブライ語やアラビア語など、右から左に書かれる言語で特に便利です。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用して開発環境がセットアップされていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ 2: アップロード オプションの構成

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

このステップでは、ドキュメント読み込みオプションを構成します。新しいものを作成します`TxtLoadOptions`オブジェクトを設定して、`DocumentDirection`財産を`DocumentDirection.Auto`。この値は、Aspose.Words に、ドキュメントの内容に基づいてテキストの方向を自動的に決定するように指示します。

## ステップ 3: ドキュメントをロードする

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

このステップでは、`Document`メソッドを呼び出し、ロードするテキスト ファイルへのパスを渡します。指定された読み込みオプションも使用します。

## ステップ 4: 段落を操作してテキストの方向を表示する

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

このステップでは、`FirstSection`そして`Body`プロパティ。次に、にアクセスします。`ParagraphFormat.Bidi`プロパティを使用して段落のテキスト方向を取得します。次に、この値をコンソールに表示します。

## ステップ 5: ドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

この最後のステップでは、結果のドキュメントを .docx 形式で保存します。`Save`メソッドを実行し、出力ファイルへのパスを渡します。

これで、ソース コードを実行してテキスト ドキュメントをロードし、テキストの方向を決定できるようになります。結果のドキュメントは、指定されたディレクトリに「WorkingWithTxtLoadOptions.DocumentTextDirection.docx」という名前で保存されます。

### Aspose.Words for .NET を使用したドキュメント テキスト方向機能のサンプル ソース コード。


```csharp

            
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET のドキュメント テキスト方向機能を検討しました。特にヘブライ語やアラビア語など、右から左に書かれる言語の場合、文書内のテキストの方向を指定する方法を学びました。

この機能は、多言語ドキュメントでテキストが正しく表示されるようにするために不可欠です。適切な読み込みオプションを使用することで、Aspose.Words はテキストの方向を自動的に検出し、それを文書に適用できます。

Aspose.Words を使用すると、ドキュメント内のテキストの方向を簡単に操作でき、ユーザーにスムーズで直感的な読書体験を提供できます。

この機能は、特定のテキスト方向を必要とする言語で文書処理を行う場合に特に便利であることに注意することが重要です。 Aspose.Words は、ドキュメント内のテキストの方向を管理する強力なツールを提供することで、このタスクを簡単にします。

文書内で必要な結果を得るには、自動テキスト方向の設定など、適切な読み込みオプションを必ず使用してください。

Aspose.Words for .NET は、ドキュメントの操作と生成のための多くの高度な機能を提供します。 Aspose.Words が提供するドキュメントと例をさらに詳しく調べることで、この強力なライブラリの機能を最大限に活用できるようになります。

したがって、ドキュメント テキストの方向を Aspose.Words for .NET プロジェクトに躊躇せずに統合し、その利点を活用して魅力的で高品質な多言語ドキュメントを作成してください。