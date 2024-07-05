---
title: Ole パッケージを使用して Word に Ole オブジェクトを挿入する
linktitle: Ole パッケージを使用して Word に Ole オブジェクトを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、OLE パッケージを含む OLE オブジェクトをドキュメントに挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

ここでは、Aspose.Words for .NET を使用して OLE パッケージで Word に OLE オブジェクトを挿入する方法を示す、以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。

## ステップ1: 必要な参照をインポートする
始める前に、Aspose.Words for .NET を使用するために必要な参照がプロジェクトにインポートされていることを確認してください。これには、Aspose.Words ライブラリのインポートと、ソース ファイルへの必要な名前空間の追加が含まれます。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## ステップ2: 新しいドキュメントとドキュメントジェネレーターを作成する
このステップでは、`Document`クラスとドキュメントビルダー`DocumentBuilder`クラス。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: OLEパッケージを使用してOLEオブジェクトを挿入する
ドキュメントジェネレーターの`InsertOleObject`OLE パッケージを含む OLE オブジェクトをドキュメントに挿入する方法。データ ストリーム、オブジェクトの種類、表示オプション、その他の必要な設定を指定します。

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

## ステップ4: ドキュメントを保存する
文書の`Save`ドキュメントをファイルに保存する方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Aspose.Words for .NET で OLE パッケージを使用して OLE オブジェクトを挿入するためのサンプル ソース コード

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

これは、Aspose.Words for .NET を使用して OLE パッケージで OLE オブジェクトを挿入するための完全なコード サンプルです。必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

結論として、Aspose.Words for .NET を使用して OLE パッケージを含む Word 文書に OLE オブジェクトを挿入するためのステップ バイ ステップ ガイドを説明しました。

これらの手順に従うと、Aspose.Words for .NET を使用して、OLE パッケージを含む OLE オブジェクトを Word 文書に正常に挿入できるようになります。必要な参照をインポートし、指示に注意深く従って、目的の結果を得てください。

### ole パッケージを使用して word に ole オブジェクトを挿入するための FAQ

#### Q: Aspose.Words for .NET を使用するには、どのような資格情報をインポートする必要がありますか?

A: Aspose.Words for .NET を使用するには、次の参照をインポートする必要があります。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Q: 新しいドキュメントとドキュメント ジェネレーターを作成するにはどうすればよいですか?

 A: 新しい文書を作成するには、`Document`クラスとドキュメントビルダー`DocumentBuilder`クラスは次のようになります。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: OLE パッケージを含む OLE オブジェクトをドキュメントに挿入するにはどうすればよいですか?

 A:`InsertOleObject`ドキュメントビルダーのメソッド（`DocumentBuilder`) を使用して、OLE パッケージを含む OLE オブジェクトをドキュメントに挿入します。データ ストリーム、オブジェクトの種類、表示オプション、その他の必要な設定を指定します。次に例を示します。

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

#### Q: ドキュメントを保存するにはどうすればよいですか?

 A: 文書を使用する`Save`ドキュメントをファイルに保存する方法。次に例を示します。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Q: Aspose.Words for .NET を使用して OLE パッケージで OLE オブジェクトを挿入する完全な例を提供できますか?

A: Aspose.Words for .NET を使用して OLE パッケージで OLE オブジェクトを挿入する完全なサンプル コードを以下に示します。必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

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

これで、Aspose.Words for .NET を使用して OLE パッケージを含む OLE オブジェクトを Word 文書に挿入するチュートリアルは終了です。必要な参照を自由にインポートし、説明されている手順に従ってこのコードをプロジェクトに統合してください。さらに質問がある場合は、お気軽にお問い合わせください。