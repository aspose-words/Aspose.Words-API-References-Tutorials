---
title: Ole パッケージを使用して Word に Ole オブジェクトを挿入する
linktitle: Ole パッケージを使用して Word に Ole オブジェクトを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、OLE パッケージを含む OLE オブジェクトをドキュメントに挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

ここでは、Aspose.Words for .NET を使用して OLE パッケージを使用して Word に OLE オブジェクトを挿入する方法を示す、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。

## ステップ 1: 必要な参照をインポートする
始める前に、Aspose.Words for .NET を使用するために必要な参照をプロジェクトにインポートしていることを確認してください。これには、Aspose.Words ライブラリのインポートと、ソース ファイルへの必要な名前空間の追加が含まれます。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## ステップ 2: 新しいドキュメントとドキュメント ジェネレーターを作成する
このステップでは、`Document`クラスと、`DocumentBuilder`クラス。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: OLE パッケージを含む OLE オブジェクトを挿入する
ドキュメントジェネレーターを使用する`InsertOleObject`メソッドを使用して、OLE パッケージを含む OLE オブジェクトをドキュメントに挿入します。データ ストリーム、オブジェクト タイプ、表示オプション、およびその他の必要な設定を指定します。

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## ステップ 4: ドキュメントを保存する
ドキュメントの`Save`ドキュメントをファイルに保存するメソッド。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Aspose.Words for .NET を使用して OLE パッケージを含む OLE オブジェクトを挿入するためのサンプル ソース コード

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

これは、Aspose.Words for .NET を使用して OLE パッケージを含む OLE オブジェクトを挿入するための完全なコード サンプルです。必ず必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

結論として、Aspose.Words for .NET を使用して、OLE パッケージを含む Word 文書に OLE オブジェクトを挿入するためのステップバイステップ ガイドを説明しました。

これらの手順に従うと、Aspose.Words for .NET を使用して、OLE パッケージを含む OLE オブジェクトを Word 文書に正常に挿入できるようになります。必要な参照をインポートし、指示に注意深く従って、望ましい結果を得るようにしてください。

### ole パッケージを使用して Word に ole オブジェクトを挿入するための FAQ

#### Q: Aspose.Words for .NET を使用するにはどのような資格情報をインポートする必要がありますか?

A: Aspose.Words for .NET を使用するには、次の参照をインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Q: 新しいドキュメントとドキュメント ジェネレーターを作成するにはどうすればよいですか?

 A: 新しいドキュメントを作成するには、`Document`クラスと、`DocumentBuilder`以下に示すように、クラス:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: OLE パッケージを含む OLE オブジェクトをドキュメントに挿入するにはどうすればよいですか?

 A: を使用してください。`InsertOleObject`ドキュメントビルダーのメソッド (`DocumentBuilder`) OLE パッケージを含む OLE オブジェクトをドキュメントに挿入します。データ ストリーム、オブジェクト タイプ、表示オプション、およびその他の必要な設定を指定します。以下に例を示します。

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Q: 文書を保存するにはどうすればよいですか?

 A: 文書を使用してください`Save`ドキュメントをファイルに保存するメソッド。以下に例を示します。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Q: Aspose.Words for .NET を使用して OLE パッケージに OLE オブジェクトを挿入する完全な例を提供していただけますか?

A: これは、Aspose.Words for .NET を使用して OLE パッケージに OLE オブジェクトを挿入するための完全なサンプル コードです。必ず必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Aspose.Words for .NET を使用して、OLE パッケージを含む OLE オブジェクトを Word 文書に挿入するチュートリアルはこれで終了です。必要な参照を自由にインポートし、説明されている手順に従ってこのコードをプロジェクトに統合してください。さらにご不明な点がございましたら、お気軽にお問い合わせください。