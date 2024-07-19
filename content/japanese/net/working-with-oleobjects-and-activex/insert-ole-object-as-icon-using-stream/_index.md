---
title: ストリームを使用して OLE オブジェクトをアイコンとして挿入する
linktitle: ストリームを使用して OLE オブジェクトをアイコンとして挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でストリームを使用して OLE オブジェクトをアイコンとして挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

ここでは、Aspose.Words for .NET でストリームを使用して OLE オブジェクトをアイコンとして挿入する方法を示す、以下の C# ソース コードを説明するステップ バイ ステップ ガイドを示します。

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

## ステップ3: ストリームからOLEオブジェクトをアイコンとして挿入する
ドキュメントビルダーの`InsertOleObjectAsIcon`ストリームから OLE オブジェクトをアイコンとしてドキュメントに挿入するメソッド。データ ストリーム、オブジェクトの種類、アイコン パス、および埋め込みオブジェクト名を指定します。

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## ステップ4: ドキュメントを保存する
文書の`Save`ドキュメントをファイルに保存する方法。

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Aspose.Words for .NET でストリームを使用して OLE オブジェクトをアイコンとして挿入するサンプル ソース コード

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

これは、Aspose.Words for .NET でストリームを使用して OLE オブジェクトをアイコンとして挿入するための完全なコード サンプルです。必要な参照をインポートし、前述の手順に従ってこのコードをプロジェクトに統合してください。

## 結論

上記のステップバイステップ ガイドでは、Aspose.Words for .NET のフローを使用して Word 文書に OLE オブジェクトをアイコンとして挿入する方法を説明しています。説明されている手順に従うことで、この機能をプロジェクトに統合できます。必要な参照をインポートし、新しいドキュメントとドキュメント ジェネレーターを作成し、ストリームから OLE オブジェクトをアイコンとして挿入して、ドキュメントを保存してください。提供されているサンプル コードを開始点として使用し、ニーズに合わせてカスタマイズしてください。

### よくある質問

#### Q. Aspose.Words for .NET を使用するために必要な参照をインポートするにはどうすればよいですか?

A. 必要な参照をインポートするには、次の手順に従う必要があります。

以下を追加`using`ソースファイルの先頭に次のステートメントを追加します。

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Aspose.Words ライブラリがプロジェクトに追加されていることを確認してください。

#### Q. Aspose.Words for .NET を使用して新しいドキュメントとドキュメント ビルダーを作成するにはどうすればよいですか?

A. 新しいドキュメントとドキュメント ジェネレーターを作成するには、次の手順に従います。

使用`Document`新しいドキュメントを作成するクラス:

```csharp
Document doc = new Document();
```
使用`DocumentBuilder`以前に作成したドキュメントに関連付けられたドキュメント ビルダーを作成するクラス:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. Aspose.Words for .NET を使用してストリームから OLE オブジェクトをアイコンとして挿入するにはどうすればよいですか?

A. ストリームから OLE オブジェクトをアイコンとして挿入するには、次の手順に従います。

使用`InsertOleObjectAsIcon` OLE オブジェクトを挿入するためのドキュメント ジェネレーターのメソッド:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q. 文書をファイルに保存するにはどうすればいいですか?

A. 文書をファイルに保存するには、`Save`宛先パスを指定するドキュメントのメソッド:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q. ストリームから OLE オブジェクトをアイコンとして挿入するコードをプロジェクトに埋め込むにはどうすればよいでしょうか?

A. ストリームから OLE オブジェクトをアイコンとしてプロジェクトに挿入するコードを埋め込むには、次の手順に従います。
- 適切な参照を追加して必要な参照をインポートします`using`声明。
- 新しいドキュメントとドキュメントビルダーを作成するには、`Document`そして`DocumentBuilder`クラス。
- ストリームから OLE オブジェクトをアイコンとして挿入するためのコードを使用します。
- ドキュメントを保存するには、`Save`適切な宛先パスを持つメソッド。

これらの手順に従うと、Aspose.Words for .NET を使用して、ストリームから OLE オブジェクトをアイコンとして正常に挿入できるようになります。 目的の結果を得るには、必ず指示に従い、必要な参照をインポートしてください。