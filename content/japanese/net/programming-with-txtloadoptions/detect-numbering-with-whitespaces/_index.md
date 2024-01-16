---
title: 空白を含む番号付けの検出
linktitle: 空白を含む番号付けの検出
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で空白を含むリスト番号を検出する方法を学びます。ドキュメントの構造を簡単に改善します。
type: docs
weight: 10
url: /ja/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
このチュートリアルでは、Aspose.Words for .NET の「空白を含む番号付けの検出」機能用に提供されている C# ソース コードを調べます。この機能を使用すると、リスト番号の後に空白が含まれるテキスト文書からリストを検出して作成できます。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用して開発環境がセットアップされていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ 2: テキストドキュメントの作成

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

このステップでは、リスト番号とそれに続く空白を含むテキスト ドキュメントをシミュレートするテキスト文字列を作成します。ピリオド、右括弧、箇条書き記号、空白などのさまざまなリスト区切り文字を使用します。

## ステップ 3: アップロード オプションの構成

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

このステップでは、ドキュメント読み込みオプションを構成します。新しいものを作成します`TxtLoadOptions`オブジェクトを設定して、`DetectNumberingWithWhitespaces`財産を`true`。これにより、Aspose.Words はリスト番号の後に空白が続いている場合でもリスト番号を検出できるようになります。

## ステップ 4: ドキュメントのロードと保存

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

このステップでは、指定されたテキスト文字列と読み込みオプションを使用してドキュメントを読み込みます。私たちは、`MemoryStream`テキスト文字列をメモリ ストリームに変換します。次に、結果のドキュメントを .docx 形式で保存します。

### Aspose.Words for .NET を使用した空白番号検出機能のサンプル ソース コード。

```csharp

            
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
//リストとして解釈される可能性のある部分を含む文字列の形式でプレーンテキストのドキュメントを作成します。
//ロード時に、最初の 3 つのリストは常に Aspose.Words によって検出されます。
//ロード後にリスト オブジェクトが作成されます。
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

// 番目のリスト (リスト番号とリスト項目の内容の間に空白が入っています)
// LoadOptions オブジェクトの "DetectNumberingWithWhitespaces" が true に設定されている場合にのみ、リストとして検出されます。
//数字で始まる段落が誤ってリストとして検出されるのを避けるため。
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// LoadOptions をパラメータとして適用しながらドキュメントをロードし、結果を確認します。
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

これで、ソース コードを実行して、空白を含むリスト番号を含むテキスト ドキュメントをロードし、検出されたリストを含む .docx ドキュメントを作成できるようになります。出力ファイルは、指定したディレクトリに「WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx」という名前で保存されます。

## 結論
このチュートリアルでは、Aspose.Words for .NET の空白番号付け検出機能を調べました。リスト番号とそれに続く空白を含むテキスト文書からリストを作成する方法を学びました。

この機能は、さまざまな方法でフォーマットされたリスト番号を含むドキュメントを処理する場合に非常に役立ちます。適切な読み込みオプションを使用することで、Aspose.Words はこれらのリスト番号の後に空白文字が続いている場合でもこれらのリスト番号を検出し、最終的な文書の構造化リストに変換できます。

この機能を使用すると、時間を節約し、ワークフローの効率を向上させることができます。テキスト文書から情報を簡単に抽出し、適切なリストを含む適切に構造化された文書に変換できます。

望ましい結果を達成するには、空白文字ダイヤル検出の構成などの読み込みオプションを忘れずに検討してください。

Aspose.Words for .NET は、ドキュメントの操作と生成のための多くの高度な機能を提供します。 Aspose.Words が提供するドキュメントと例をさらに詳しく調べることで、この強力なライブラリの機能を最大限に活用できるようになります。

したがって、躊躇せずに空白番号検出を Aspose.Words for .NET プロジェクトに統合し、その利点を活用して、適切に構造化された読みやすいドキュメントを作成してください。


