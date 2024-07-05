---
title: 文書のテキスト方向
linktitle: 文書のテキスト方向
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内のテキストの方向を指定する方法を学習します。右から左に記述する言語の表示を改善します。
type: docs
weight: 10
url: /ja/net/programming-with-txtloadoptions/document-text-direction/
---

このチュートリアルでは、Aspose.Words for .NET の「ドキュメント テキスト方向」機能用に提供されている C# ソース コードについて説明します。この機能を使用すると、ドキュメント内のテキストの方向を指定できます。これは、ヘブライ語やアラビア語など、右から左に記述される言語で特に役立ちます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: アップロードオプションの設定

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

このステップでは、ドキュメントの読み込みオプションを設定します。新しい`TxtLoadOptions`オブジェクトを設定し、`DocumentDirection`財産に`DocumentDirection.Auto`この値は、Aspose.Words に、ドキュメントの内容に基づいてテキストの方向を自動的に決定するように指示します。

## ステップ3: ドキュメントの読み込み

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

このステップでは、`Document`メソッドを実行し、読み込むテキスト ファイルへのパスを渡します。また、指定された読み込みオプションも使用します。

## ステップ4: 段落を操作してテキストの方向を表示する

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

このステップでは、文書の最初の段落にアクセスします。`FirstSection`そして`Body`プロパティにアクセスします。次に、`ParagraphFormat.Bidi`プロパティを使用して段落のテキスト方向を取得します。この値をコンソールに表示します。

## ステップ5: ドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

この最後のステップでは、結果の文書を.docx形式で保存します。`Save`メソッドを実行し、出力ファイルへのパスを渡します。

これで、ソース コードを実行してテキスト ドキュメントを読み込み、テキストの方向を決定できます。結果のドキュメントは、指定されたディレクトリに「WorkingWithTxtLoadOptions.DocumentTextDirection.docx」という名前で保存されます。

### Aspose.Words for .NET を使用したドキュメントのテキスト方向機能のサンプル ソース コード。


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

このチュートリアルでは、Aspose.Words for .NET のドキュメント テキスト方向機能について説明しました。特にヘブライ語やアラビア語など、右から左に記述される言語の場合、ドキュメント内のテキストの方向を指定する方法を学習しました。

この機能は、多言語ドキュメントでテキストが正しく表示されるようにするために不可欠です。適切な読み込みオプションを使用することで、Aspose.Words はテキストの方向を自動的に検出し、ドキュメントに適用できます。

Aspose.Words を使用すると、ドキュメント内のテキストの方向を簡単に操作できるため、ユーザーにスムーズで直感的な読み取りエクスペリエンスを提供できます。

この機能は、特定のテキスト方向を必要とする言語で Words を処理する場合に特に便利です。Aspose.Words は、ドキュメント内のテキストの方向を管理するための強力なツールを提供することで、このタスクを容易にします。

ドキュメントで必要な結果を得るには、自動テキスト方向の設定など、適切な読み込みオプションを使用するようにしてください。

Aspose.Words for .NET は、ドキュメントの操作と生成のための高度な機能を多数提供します。Aspose.Words が提供するドキュメントと例をさらに詳しく調べることで、この強力なライブラリの機能を最大限に活用できるようになります。

したがって、Aspose.Words for .NET プロジェクトにドキュメント テキスト方向をぜひ統合し、その利点を活用して魅力的で高品質な多言語ドキュメントを作成してください。