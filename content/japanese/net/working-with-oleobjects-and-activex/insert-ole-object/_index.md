---
title: Word 文書に Ole オブジェクトを挿入
linktitle: Word 文書に Ole オブジェクトを挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントに OLE オブジェクトを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object/
---

ここでは、Aspose.Words for .NET を使用して Word ドキュメントに OLE オブジェクトを挿入する方法を示す、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。

## ステップ 1: 必要な参照をインポートする
始める前に、Aspose.Words for .NET を使用するために必要な参照をプロジェクトにインポートしていることを確認してください。これには、Aspose.Words ライブラリのインポートと、ソース ファイルへの必要な名前空間の追加が含まれます。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## ステップ 2: 新しいドキュメントとドキュメント ジェネレーターを作成する
このステップでは、`Document`クラスと、`DocumentBuilder`クラス。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: OLE オブジェクトを挿入する
ドキュメントビルダーを使用する`InsertOleObject`メソッドを使用して、OLE オブジェクトをドキュメントに挿入します。 OLE オブジェクト URL、オブジェクト タイプ、表示オプション、およびその他の必要な設定を指定します。

```csharp
builder. InsertOleObject("http://www.aspose.com"、"htmlfile"、true、true、null);
```

## ステップ 4: ドキュメントを保存する
ドキュメントの`Save`ドキュメントをファイルに保存するメソッド。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Aspose.Words for .NET を使用して OLE オブジェクトを挿入するためのソース コードの例

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com"、"htmlfile"、true、true、null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

これは、Aspose.Words for .NET を使用して OLE オブジェクトを挿入するための完全なコード サンプルです。必ず必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

結論として、Word 文書への OLE オブジェクトの挿入は、Aspose.Words for .NET が提供する強力な機能です。このライブラリを使用すると、HTML ファイル、Excel スプレッドシート、PowerPoint プレゼンテーションなどの OLE オブジェクトを Word ドキュメントに簡単に埋め込むことができます。

この記事では、Word 文書に OLE オブジェクトを挿入する方法を示す C# のソース コードを段階的に説明しました。必要なリファレンス、新しいドキュメントとドキュメント ジェネレーターの作成、OLE オブジェクトを挿入してドキュメントを保存する手順について説明しました。

### Word 文書に OLE オブジェクトを挿入する場合の FAQ

#### Q: Aspose.Words for .NET を使用するにはどのような資格情報をインポートする必要がありますか?

A: Aspose.Words for .NET を使用するには、次の参照をインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q: 新しいドキュメントとドキュメント ジェネレーターを作成するにはどうすればよいですか?

 A: 新しいドキュメントを作成するには、`Document`クラスと、`DocumentBuilder`以下に示すように、クラス:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: ドキュメントに OLE オブジェクトを挿入するにはどうすればよいですか?

 A: を使用してください。`InsertOleObject`ドキュメントビルダーのメソッド (`DocumentBuilder`) OLE オブジェクトをドキュメントに挿入します。 OLE オブジェクト URL、オブジェクト タイプ、表示オプション、およびその他の必要な設定を指定します。以下に例を示します。

```csharp
builder. InsertOleObject("http://www.aspose.com"、"htmlfile"、true、true、null);
```

#### Q: 文書を保存するにはどうすればよいですか?

 A: 文書を使用してください`Save`ドキュメントをファイルに保存するメソッド。以下に例を示します。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Q: Aspose.Words for .NET を使用して OLE オブジェクトを挿入する完全な例を提供していただけますか?

A: これは、Aspose.Words for .NET を使用して OLE オブジェクトを挿入するための完全なサンプル コードです。必ず必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com"、"htmlfile"、true、true、null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
