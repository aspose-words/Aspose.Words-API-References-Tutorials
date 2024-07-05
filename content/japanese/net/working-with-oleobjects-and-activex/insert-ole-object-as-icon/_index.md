---
title: Word 文書に Ole オブジェクトをアイコンとして挿入する
linktitle: Word 文書に Ole オブジェクトをアイコンとして挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書に OLE オブジェクトをアイコンとして挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

ここでは、Aspose.Words for .NET を使用して Word 文書に OLE オブジェクトをアイコンとして挿入する方法を示す、以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。

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

## ステップ3: OLEオブジェクトをアイコンとして挿入する
ドキュメントビルダーの`InsertOleObjectAsIcon`OLE オブジェクトをアイコンとしてドキュメントに挿入するメソッド。OLE ファイル パス、表示フラグ、アイコン パス、および埋め込みオブジェクト名を指定します。

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## ステップ4: ドキュメントを保存する
文書の`Save`ドキュメントをファイルに保存する方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Aspose.Words for .NET を使用して OLE オブジェクトをアイコンとして挿入するためのサンプル ソース コード

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

これは、Aspose.Words for .NET を使用して OLE オブジェクトをアイコンとして挿入するための完全なコード サンプルです。必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

結論として、Aspose.Words for .NET を使用して Word 文書に OLE オブジェクトをアイコンとして挿入するためのステップバイステップ ガイドを検討しました。

これらの手順に従うと、Aspose.Words for .NET を使用して Word 文書に OLE オブジェクトをアイコンとして正常に挿入できるようになります。必要な参照をインポートし、指示に注意深く従って、目的の結果を得てください。

### Word 文書に OLE オブジェクトをアイコンとして挿入するための FAQ

#### Q. Aspose.Words for .NET を使用して Word 文書に OLE オブジェクトをアイコンとして挿入するには、どのような参照が必要ですか?

A: Aspose.Words for .NET を使用するには、次の参照をプロジェクトにインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q. Aspose.Words for .NET で新しいドキュメントとドキュメント ジェネレーターを作成するにはどうすればよいですか?

 A: 新しい文書を作成するには、`Document`クラスとドキュメントビルダー`DocumentBuilder`クラス。次に例を示します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. ドキュメントに OLE オブジェクトをアイコンとして挿入するにはどうすればよいですか?

 A: ドキュメントビルダーの`InsertOleObjectAsIcon`OLE オブジェクトをアイコンとして挿入する方法。OLE ファイル パス、表示フラグ、アイコン パス、および埋め込みオブジェクト名を指定します。次に例を示します。

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. OLE オブジェクトをアイコンとして挿入したドキュメントを保存するにはどうすればよいですか?

 A: 文書を使用する`Save`ドキュメントをファイルに保存する方法。次に例を示します。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```