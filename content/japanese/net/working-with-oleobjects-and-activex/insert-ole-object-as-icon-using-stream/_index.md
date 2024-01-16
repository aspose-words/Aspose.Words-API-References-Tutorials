---
title: ストリームを使用して Ole オブジェクトをアイコンとして挿入
linktitle: ストリームを使用して Ole オブジェクトをアイコンとして挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のストリームを使用して OLE オブジェクトをアイコンとして挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

ここでは、Aspose.Words for .NET のストリームを使用して OLE オブジェクトをアイコンとして挿入する方法を示す、以下の C# ソース コードを説明するステップバイステップ ガイドを示します。

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

## ステップ 3: ストリームから OLE オブジェクトをアイコンとして挿入する
ドキュメントビルダーを使用する`InsertOleObjectAsIcon`メソッドを使用して、OLE オブジェクトをアイコンとしてストリームからドキュメントに挿入します。データ ストリーム、オブジェクト タイプ、アイコン パス、および埋め込みオブジェクト名を指定します。

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## ステップ 4: ドキュメントを保存する
ドキュメントの`Save`ドキュメントをファイルに保存するメソッド。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Aspose.Words for .NET のストリームを使用して OLE オブジェクトをアイコンとして挿入するソース コードの例

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

これは、Aspose.Words for .NET のストリームを使用して OLE オブジェクトをアイコンとして挿入するための完全なコード サンプルです。必ず必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

上記のステップバイステップ ガイドでは、Aspose.Words for .NET のフローを使用して、OLE オブジェクトを Word 文書にアイコンとして挿入する方法を説明しています。説明されている手順に従うことで、この機能をプロジェクトに統合できます。必ず必要な参照をインポートし、新しいドキュメントとドキュメント ジェネレーターを作成し、ストリームから OLE オブジェクトをアイコンとして挿入してから、ドキュメントを保存してください。提供されているサンプル コードを出発点として使用し、ニーズに合わせてカスタマイズします。

### よくある質問

#### Q.Aspose.Words for .NET を使用するために必要な参照をインポートするにはどうすればよいですか?

A. 必要な参照をインポートするには、次の手順に従う必要があります。

以下を追加します`using`ソース ファイルの先頭にあるステートメント:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Aspose.Words ライブラリがプロジェクトに追加されていることを確認してください。

#### Q.Aspose.Words for .NET を使用して新しいドキュメントとドキュメント ビルダーを作成するにはどうすればよいですか?

A. 新しいドキュメントとドキュメント ジェネレーターを作成するには、次の手順に従います。

使用`Document`新しいドキュメントを作成するクラス:

```csharp
Document doc = new Document();
```
使用`DocumentBuilder`クラスを使用して、以前に作成したドキュメントに関連付けられたドキュメント ビルダーを作成します。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q.Aspose.Words for .NET を使用して、ストリームから OLE オブジェクトをアイコンとして挿入するにはどうすればよいですか?

A. OLE オブジェクトをストリームからアイコンとして挿入するには、次の手順に従います。

使用`InsertOleObjectAsIcon`ドキュメント ジェネレーターのメソッドを使用して OLE オブジェクトを挿入します。

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q. 文書をファイルに保存するにはどうすればよいですか?

A. ドキュメントをファイルに保存するには、`Save`宛先パスを指定するドキュメントのメソッド:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q. OLE オブジェクトをストリームからプロジェクトにアイコンとして挿入するコードを埋め込むにはどうすればよいですか?

A. OLE オブジェクトをアイコンとしてストリームからプロジェクトに挿入するコードを埋め込むには、次の手順に従います。
- 適切な参照を追加して、必要な参照をインポートします。`using`発言。
- を使用して、新しいドキュメントとドキュメント ビルダーを作成します。`Document`そして`DocumentBuilder`クラス。
- ストリームから OLE オブジェクトをアイコンとして挿入するコードを使用します。
- を使用して文書を保存します。`Save`メソッドに適切な宛先パスを指定します。

これらの手順に従うと、Aspose.Words for .NET を使用してストリームから OLE オブジェクトをアイコンとして正常に挿入できるようになります。望ましい結果を得るために、必ず指示に従い、必要な参照をインポートしてください。