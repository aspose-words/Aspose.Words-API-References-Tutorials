---
title: 段落内のフィールドを変換する
linktitle: 段落内のフィールドを変換する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、段落内の IF フィールドをプレーン テキストに変換します。
type: docs
weight: 10
url: /ja/net/working-with-fields/convert-fields-in-paragraph/
---

これは、Aspose.Words for .NET でフィールドを段落に変換機能を使用する方法を示すチュートリアルです。このコードは、文書の最後の段落にあるすべての IF タイプのフィールドをプレーン テキストに変換します。このコードを理解して実行するには、次の手順に従ってください。

始める前に、Aspose.Words for .NET がインストールされ、開発環境がセットアップされていることを確認してください。

## ステップ 1: 参照をインポートする

プロジェクトで Aspose.Words を使用するには、必要な参照を追加する必要があります。プロジェクトに Aspose.Words ライブラリへの参照を追加していることを確認してください。

## ステップ 2: ドキュメントをロードする

フィールドを変換する前に、変換するフィールドを含むドキュメントをロードする必要があります。ドキュメントを含むディレクトリへの正しいパスを必ず指定してください。ドキュメントをアップロードする方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします。
Document doc = new Document(dataDir + "Linked fields.docx");
```

「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えます。

## ステップ 3: フィールドをテキストに変換する

ドキュメントがロードされたので、タイプフィールドをプレーンテキストに変換する作業を進めることができます。この例では、ドキュメントの最後の段落に存在するフィールドのみをターゲットとします。この変換を実行するコードは次のとおりです。

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

このコードは、LINQ メソッドの組み合わせを使用してドキュメントの最後の段落にあるフィールドをフィルターで除外し、メソッドを呼び出してフィールドをプレーン テキストに変換します。`Unlink()`方法。

## ステップ 4: 変更したドキュメントを保存する

フィールドが変換されたら、変更したドキュメントを保存できます。使用`Save()`このための方法。以下に例を示します。

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

バックアップには正しいパスとファイル名を指定してください。

### Aspose.Words for .NET を使用した段落内のフィールドの変換のソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします。
Document doc = new Document(dataDir + "Linked fields.docx");

//ドキュメントの最後の段落で IF フィールドをプレーン テキストに変換します。
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

//変更したドキュメントを保存します。
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### よくある質問

#### Q: Aspose.Words のコンバージョン フィールドとは何ですか?

A: Aspose.Words の変換フィールドは、値または式を別の形式またはデータ型に変換するフィールドのタイプです。たとえば、変換フィールドを使用して、日付を特定の形式に変換したり、数値をテキストに変換したり、その他の種類の変換を実行したりできます。

#### Q: Aspose.Words を使用して段落に変換フィールドを挿入するにはどうすればよいですか?

A: Aspose.Words を使用して段落に変換フィールドを挿入するには、次の手順に従います。

1. Aspose.Words 名前空間から Document クラスをインポートします。
2. 既存のドキュメントをロードして、Document のインスタンスを作成します。
3. 変換フィールドを挿入する段落を取得します。
4. InsertField メソッドを使用して、正しい構文で変換フィールドを挿入します。

#### Q: Aspose.Words はどのような変換形式をサポートしていますか?

A: Aspose.Words は、日付形式、数値形式、テキスト形式、通貨形式、パーセント形式などを含むフィールドで幅広い変換形式をサポートしています。利用可能な変換形式の完全なリストについては、Aspose.Words のドキュメントを確認してください。

#### Q: Aspose.Words を使用して Word 文書の変換フィールドを更新するにはどうすればよいですか?

A: Aspose.Words を使用して Word 文書内の変換フィールドを更新するには、UpdateFields メソッドを使用できます。このメソッドはドキュメントをループし、変換フィールドを含むすべてのフィールドを更新し、現在のデータに基づいて値を再計算します。