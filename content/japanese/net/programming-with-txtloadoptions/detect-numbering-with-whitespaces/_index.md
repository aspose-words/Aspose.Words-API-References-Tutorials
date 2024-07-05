---
title: 空白を含む番号を検出する
linktitle: 空白を含む番号を検出する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で空白のあるリスト番号を検出する方法を学びます。ドキュメントの構造を簡単に改善します。
type: docs
weight: 10
url: /ja/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
このチュートリアルでは、Aspose.Words for .NET の「空白を含む番号の検出」機能用に提供されている C# ソース コードについて説明します。この機能を使用すると、リスト番号の後に空白が続くテキスト ドキュメントからリストを検出して作成できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: テキストドキュメントの作成

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

この手順では、リスト番号とそれに続く空白を含むテキスト ドキュメントをシミュレートするテキスト文字列を作成します。ピリオド、右括弧、箇条書き記号、空白などのさまざまなリスト区切り文字を使用します。

## ステップ3: アップロードオプションの設定

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

このステップでは、ドキュメントの読み込みオプションを設定します。新しい`TxtLoadOptions`オブジェクトを設定し、`DetectNumberingWithWhitespaces`財産に`true`これにより、リスト番号の後に空白があっても、Aspose.Words はリスト番号を検出できるようになります。

## ステップ4: ドキュメントの読み込みと保存

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

このステップでは、指定されたテキスト文字列と読み込みオプションを使用してドキュメントを読み込みます。`MemoryStream`テキスト文字列をメモリ ストリームに変換します。次に、結果のドキュメントを .docx 形式で保存します。

### Aspose.Words for .NET の空白番号検出機能のサンプル ソース コード。

```csharp

            
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
//リストとして解釈できる部分を含む文字列形式のプレーンテキスト ドキュメントを作成します。
//ロード時に、最初の3つのリストは常にAspose.Wordsによって検出されます。
//ロード後にそれらのリスト オブジェクトが作成されます。
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

//4番目のリストでは、リスト番号とリスト項目の内容の間に空白が入っています。
// LoadOptionsオブジェクトの「DetectNumberingWithWhitespaces」がtrueに設定されている場合にのみリストとして検出されます。
//数字で始まる段落が誤ってリストとして検出されるのを避けるためです。
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// LoadOptions をパラメータとして適用しながらドキュメントをロードし、結果を確認します。
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

これで、ソース コードを実行して、空白のあるリスト番号を含むテキスト ドキュメントを読み込み、検出されたリストを含む .docx ドキュメントを作成できます。出力ファイルは、指定されたディレクトリに「WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx」という名前で保存されます。

## 結論
このチュートリアルでは、Aspose.Words for .NET の空白番号検出機能について説明しました。リスト番号の後に空白が続くテキスト ドキュメントからリストを作成する方法を学習しました。

この機能は、さまざまな方法でフォーマットされたリスト番号を含むドキュメントを処理する場合に非常に便利です。適切な読み込みオプションを使用することで、Aspose.Words は、リスト番号の後に空白があってもこれらのリスト番号を検出し、最終ドキュメントで構造化されたリストに変換できます。

この機能を使用すると、時間を節約し、ワークフローの効率を向上させることができます。テキスト ドキュメントから情報を簡単に抽出し、適切なリストを含む適切に構造化されたドキュメントに変換できます。

望ましい結果を得るには、空白文字のダイヤル検出を構成するなどの読み込みオプションを考慮することを忘れないでください。

Aspose.Words for .NET は、ドキュメントの操作と生成のための高度な機能を多数提供します。Aspose.Words が提供するドキュメントと例をさらに詳しく調べることで、この強力なライブラリの機能を最大限に活用できるようになります。

したがって、躊躇せずに空白番号検出を Aspose.Words for .NET プロジェクトに統合し、その利点を活用して、構造化され読みやすいドキュメントを作成してください。


