---
title: Word 文書に Ole オブジェクトを挿入する
linktitle: Word 文書に Ole オブジェクトを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に OLE オブジェクトを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object/
---

ここでは、Aspose.Words for .NET を使用して Word 文書に OLE オブジェクトを挿入する方法を示す、以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。

## ステップ1: 必要な参照をインポートする
始める前に、Aspose.Words for .NET を使用するために必要な参照がプロジェクトにインポートされていることを確認してください。これには、Aspose.Words ライブラリのインポートと、ソース ファイルへの必要な名前空間の追加が含まれます。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## ステップ2: 新しいドキュメントとドキュメントジェネレーターを作成する
このステップでは、`Document`クラスとドキュメントビルダー`DocumentBuilder`クラス。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: OLEオブジェクトを挿入する
ドキュメントビルダーの`InsertOleObject`ドキュメントに OLE オブジェクトを挿入するメソッド。OLE オブジェクトの URL、オブジェクトの種類、表示オプション、その他の必要な設定を指定します。

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## ステップ4: ドキュメントを保存する
文書の`Save`ドキュメントをファイルに保存する方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Aspose.Words for .NET を使用して OLE オブジェクトを挿入するためのサンプル ソース コード

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

これは、Aspose.Words for .NET を使用して OLE オブジェクトを挿入するための完全なコード サンプルです。必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

結論として、Word 文書に OLE オブジェクトを挿入することは、Aspose.Words for .NET が提供する強力な機能です。このライブラリを使用すると、HTML ファイル、Excel スプレッドシート、PowerPoint プレゼンテーションなどの OLE オブジェクトを Word 文書に簡単に埋め込むことができます。

この記事では、Word 文書に OLE オブジェクトを挿入する方法を示す C# のソース コードをステップ バイ ステップで説明しました。必要な参照、新しい文書と文書ジェネレーターの作成、OLE オブジェクトを挿入して文書を保存する手順について説明しました。

### Word 文書に OLE オブジェクトを挿入するための FAQ

#### Q: Aspose.Words for .NET を使用するには、どのような資格情報をインポートする必要がありますか?

A: Aspose.Words for .NET を使用するには、次の参照をインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q: 新しいドキュメントとドキュメント ジェネレーターを作成するにはどうすればよいですか?

 A: 新しい文書を作成するには、`Document`クラスとドキュメントビルダー`DocumentBuilder`クラスは次のようになります。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: ドキュメントに OLE オブジェクトを挿入するにはどうすればよいですか?

 A:`InsertOleObject`ドキュメントビルダーのメソッド（`DocumentBuilder`) を使用して、ドキュメントに OLE オブジェクトを挿入します。OLE オブジェクトの URL、オブジェクトの種類、表示オプション、その他の必要な設定を指定します。次に例を示します。

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### Q: ドキュメントを保存するにはどうすればよいですか?

 A: 文書を使用する`Save`ドキュメントをファイルに保存する方法。次に例を示します。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Q: Aspose.Words for .NET を使用して OLE オブジェクトを挿入する完全な例を提供できますか?

A: Aspose.Words for .NET を使用して OLE オブジェクトを挿入するための完全なサンプル コードを以下に示します。必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
