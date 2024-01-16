---
title: Word文書の目次を削除する
linktitle: Word文書の目次を削除する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の目次を削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/remove-content/remove-table-of-contents/
---
このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して Word 文書の目次を削除する方法を説明します。目次は冗長または不必要な場合がありますが、このコードはそれを効果的に削除するのに役立ちます。コードを理解し、独自の .NET プロジェクトに実装するのに役立つステップバイステップのガイドを提供します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- 削除する目次を含む Word 文書

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードする
次に、Word 文書を`Document`を使用したクラス`Load`方法。

```csharp
//ドキュメントをロードします
Document doc = new Document(dataDir + "your-document.docx");
```

## ステップ 3: 目次を削除する
目次を削除するには、TOC (目次) タイプをループします。`FieldStart`ドキュメント内のノード。これらのノードにすぐにアクセスして、削除するノードのリストを作成できるように、これらのノードを保存します。

```csharp
//素早くアクセスできるように、目次フィールドの FieldStart ノードをドキュメントに保存します。
List<FieldStart> fieldStarts = new List<FieldStart>();
//これは、指定された TOC 内で見つかったノードを保存するリストです。これらはこのメソッドの終了時に削除されます。
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

//指定された TOC インデックスが存在するかどうかを確認します。
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     //これらのノードを保存し、最後にすべて削除する方が安全です。
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // FieldTOC タイプの FieldEnd ノードに遭遇すると、
     //現在の目次の終わりに来ていることがわかっているので、ここで終了します。
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Aspose.Words for .NET を使用して目次を削除するためのサンプル ソース コード 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//ドキュメントをロードします
Document doc = new Document(dataDir + "your-document.docx");

//素早くアクセスできるように、目次フィールドの FieldStart ノードをドキュメントに保存します。
List<FieldStart> fieldStarts = new List<FieldStart>();
//これは、指定された TOC 内で見つかったノードを保存するリストです。これらはこのメソッドの最後に削除されます。
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

//渡されたインデックスによって指定された TOC が存在することを確認してください。
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	//これらのノードを保存し、後ですべて一度に削除する方が安全です。
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// FieldTOC タイプの FieldEnd ノードに遭遇すると、
	//現在の目次の終わりに来ていることがわかっているので、ここで終了します。
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## 結論
このチュートリアルでは、.NET 用の Aspose.Words ライブラリを使用して Word 文書から目次を削除するためのステップバイステップのガイドを紹介しました。提供されているコードと指示に従うことで、目次を簡単に削除し、ドキュメントのレイアウトを改善できます。特定のニーズに合わせてディレクトリ パスとファイル名を変更することを忘れないでください。

### よくある質問

#### Q: Word 文書の目次を削除するには、Aspose.Words を使用する必要があるのはなぜですか?

A: Aspose.Words は、.NET アプリケーションで Word ドキュメントを操作するための強力で多用途のクラス ライブラリです。 Aspose.Words を使用すると、ドキュメントから目次を効果的に削除できます。これは、目次が冗長または不要な場合に役立ちます。これにより、ドキュメントのコンテンツをカスタマイズし、全体的なプレゼンテーションを改善することができます。

#### Q: Aspose.Words for .NET でドキュメントをアップロードするにはどうすればよいですか?

A: Word 文書の目次を削除するには、まず Aspose.Words の Load() メソッドを使用して文書をメモリにロードする必要があります。特定のディレクトリからドキュメントをロードするサンプル コードを次に示します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントをロードします
Document doc = new Document(dataDir + "your-document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントへの実際のパスを含めます。

#### Q: Aspose.Words を使用してドキュメントの目次を削除するにはどうすればよいですか?

 A: 目次を削除するには、次の手順を繰り返す必要があります。`FieldStart`ドキュメント内の目次のノードを入力します。これらのノードを保存してすぐにアクセスしたり、削除するノードのリストを作成したりできます。サンプルコードは次のとおりです。

```csharp
//素早くアクセスできるように、目次フィールドの FieldStart ノードをドキュメントに保存します。
List<FieldStart> fieldStarts = new List<FieldStart>();
//これは、指定された TOC 内で見つかったノードを格納するリストです。これらはこのメソッドの終了時に削除されます。
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

//指定された目次インデックスが存在するかどうかを確認します。
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
//これらのノードを保存し、最後にすべて削除する方が安全です。
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// FieldTOC タイプの FieldEnd ノードに遭遇すると、
//現在の目次の終わりに来ていることがわかっているので、ここで終了します。
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### Q: Aspose.Words for .NET で編集したドキュメントを保存するにはどうすればよいですか?

A: 目次を削除した後、Save() メソッドを使用して変更したドキュメントを保存する必要があります。編集したドキュメントに必要な出力ファイルのパスと形式 (DOCX など) を指定します。サンプルコードは次のとおりです。

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```