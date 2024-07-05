---
title: 段落内のフィールドを変換
linktitle: 段落内のフィールドを変換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、IF フィールドを段落内のプレーン テキストに変換します。
type: docs
weight: 10
url: /ja/net/working-with-fields/convert-fields-in-paragraph/
---

ここでは、Aspose.Words for .NET でフィールドを段落に変換する機能を使用する方法を説明するチュートリアルを紹介します。このコードは、ドキュメントの最後の段落にあるすべての IF タイプのフィールドをプレーン テキストに変換します。このコードを理解して実行するには、以下の手順に従ってください。

開始する前に、Aspose.Words for .NET がインストールされ、開発環境が設定されていることを確認してください。

## ステップ1: 参照をインポートする

プロジェクトで Aspose.Words を使用するには、必要な参照を追加する必要があります。プロジェクトに Aspose.Words ライブラリへの参照を追加したことを確認してください。

## ステップ2: ドキュメントの読み込み

フィールドを変換する前に、変換するフィールドを含むドキュメントを読み込む必要があります。ドキュメントを含むディレクトリへの正しいパスを必ず指定してください。ドキュメントをアップロードする方法は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込みます。
Document doc = new Document(dataDir + "Linked fields.docx");
```

「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えます。

## ステップ3: フィールドをテキストに変換する

ドキュメントが読み込まれたので、タイプ フィールドをプレーン テキストに変換する作業に進むことができます。この例では、ドキュメントの最後の段落にあるフィールドのみを対象とします。この変換を実行するコードは次のとおりです。

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

このコードは、LINQメソッドの組み合わせを使用して、ドキュメントの最後の段落のフィールドをフィルターし、呼び出してプレーンテキストに変換します。`Unlink()`方法。

## ステップ4: 変更したドキュメントを保存する

フィールドが変換されたら、変更したドキュメントを保存できます。`Save()`これを行う方法。例を示します。

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

バックアップの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用して段落内のフィールドを変換するソース コードの例

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを読み込みます。
Document doc = new Document(dataDir + "Linked fields.docx");

//ドキュメントの最後の段落にある IF フィールドをプレーンテキストに変換します。
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

//変更したドキュメントを保存します。
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### よくある質問

#### Q: Aspose.Words の変換フィールドとは何ですか?

A: Aspose.Words の変換フィールドは、値または式を別の形式またはデータ型に変換するフィールドの一種です。たとえば、変換フィールドを使用して、日付を特定の形式に変換したり、数値をテキストに変換したり、その他の種類の変換を実行したりできます。

#### Q: Aspose.Words を使用して段落に変換フィールドを挿入するにはどうすればよいですか?

A: Aspose.Words を使用して段落に変換フィールドを挿入するには、次の手順に従います。

1. Aspose.Words 名前空間から Document クラスをインポートします。
2. 既存のドキュメントを読み込んで Document のインスタンスを作成します。
3. 変換フィールドを挿入する段落を取得します。
4. InsertField メソッドを使用して、正しい構文で変換フィールドを挿入します。

#### Q: Aspose.Words はどのような変換形式をサポートしていますか?

A: Aspose.Words は、日付形式、数値形式、テキスト形式、通貨形式、パーセンテージ形式など、フィールドのさまざまな変換形式をサポートしています。使用可能な変換形式の完全なリストについては、Aspose.Words のドキュメントを参照してください。

#### Q: Aspose.Words を使用して Word 文書内の変換フィールドを更新するにはどうすればよいですか?

A: Aspose.Words を使用して Word 文書内の変換フィールドを更新するには、UpdateFields メソッドを使用できます。このメソッドは文書をループし、変換フィールドを含むすべてのフィールドを更新し、現在のデータに基づいて値を再計算します。