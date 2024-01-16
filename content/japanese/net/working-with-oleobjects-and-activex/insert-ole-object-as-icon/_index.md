---
title: Ole オブジェクトを Word 文書にアイコンとして挿入
linktitle: Ole オブジェクトを Word 文書にアイコンとして挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、OLE オブジェクトを Word 文書にアイコンとして挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

ここでは、Aspose.Words for .NET を使用して Word ドキュメントに OLE オブジェクトをアイコンとして挿入する方法を示す、以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。

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

## ステップ 3: OLE オブジェクトをアイコンとして挿入する
ドキュメントビルダーを使用する`InsertOleObjectAsIcon`OLE オブジェクトをアイコンとしてドキュメントに挿入するメソッド。 OLE ファイルのパス、表示フラグ、アイコンのパス、埋め込みオブジェクト名を指定します。

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## ステップ 4: ドキュメントを保存する
ドキュメントの`Save`ドキュメントをファイルに保存するメソッド。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Aspose.Words for .NET を使用して OLE オブジェクトをアイコンとして挿入するためのソース コードの例

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

これは、Aspose.Words for .NET を使用して OLE オブジェクトをアイコンとして挿入するための完全なコード サンプルです。必ず必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

結論として、Aspose.Words for .NET を使用して OLE オブジェクトを Word 文書にアイコンとして挿入するためのステップバイステップ ガイドを調べました。

これらの手順に従うと、Aspose.Words for .NET を使用して OLE オブジェクトを Word 文書にアイコンとして正常に挿入できるようになります。必要な参照をインポートし、指示に注意深く従って、望ましい結果を得るようにしてください。

### Word 文書に ole オブジェクトをアイコンとして挿入するための FAQ

#### Q. Aspose.Words for .NET を使用して OLE オブジェクトを Word 文書にアイコンとして挿入するには、どのような参照が必要ですか?

A: Aspose.Words for .NET を使用するには、次の参照をプロジェクトにインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q.Aspose.Words for .NET で新しいドキュメントとドキュメント ジェネレーターを作成するにはどうすればよいですか?

 A: 新しいドキュメントを作成するには、`Document`クラスと、`DocumentBuilder`クラス。以下に例を示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. OLE オブジェクトをアイコンとしてドキュメントに挿入するにはどうすればよいですか?

 A: ドキュメントビルダーを使用してください。`InsertOleObjectAsIcon` OLE オブジェクトをアイコンとして挿入するメソッド。 OLE ファイルのパス、表示フラグ、アイコンのパス、埋め込みオブジェクト名を指定します。以下に例を示します。

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. OLE オブジェクトをアイコンとして挿入した文書を保存するにはどうすればよいですか?

 A: 文書を使用してください`Save`ドキュメントをファイルに保存するメソッド。以下に例を示します。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```