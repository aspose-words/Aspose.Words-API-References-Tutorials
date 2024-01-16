---
title: Remover índice do documento do Word
linktitle: Remover índice do documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como remover o índice analítico de um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/remove-content/remove-table-of-contents/
---
Neste tutorial, orientaremos você sobre como remover o índice analítico de um documento do Word usando a biblioteca Aspose.Words para .NET. O índice às vezes pode ser redundante ou desnecessário, e este código o ajudará a removê-lo de forma eficaz. Forneceremos um guia passo a passo para ajudá-lo a compreender e implementar o código em seu próprio projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto
- Um documento do Word contendo um índice que você deseja excluir

## Passo 1: Defina o diretório do documento
 Primeiro, você precisa definir o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento
 A seguir, carregaremos o documento Word em uma instância do`Document` aula usando o`Load` método.

```csharp
// Carregue o documento
Document doc = new Document(dataDir + "your-document.docx");
```

## Etapa 3: excluir o índice
 Para remover o índice, faremos um loop pelo tipo TOC (índice)`FieldStart` nós no documento. Armazenaremos esses nós para que possamos acessá-los rapidamente e criar uma lista de nós para excluir.

```csharp
// Armazene nós FieldStart de campos TOC no documento para acesso rápido.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Esta é uma lista para armazenar os nós encontrados dentro do TOC especificado. Eles serão excluídos no final deste método.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Verifique se o índice TOC especificado existe.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // É mais seguro armazenar esses nós e excluí-los todos no final.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Quando encontramos um nó FieldEnd do tipo FieldTOC,
     //sabemos que estamos no final do TOC atual e paramos por aqui.
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


### Exemplo de código-fonte para remover índice usando Aspose.Words for .NET 
```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Carregue o documento
Document doc = new Document(dataDir + "your-document.docx");

// Armazene os nós FieldStart dos campos TOC no documento para acesso rápido.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Esta é uma lista para armazenar os nós encontrados dentro do TOC especificado. Eles serão removidos ao final deste método.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Certifique-se de que o TOC especificado pelo índice passado exista.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// É mais seguro armazenar esses nós e excluí-los todos de uma vez mais tarde.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Assim que encontrarmos um nó FieldEnd do tipo FieldTOC,
	// sabemos que estamos no final do TOC atual e paramos por aqui.
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

## Conclusão
Neste tutorial, apresentamos um guia passo a passo para remover o índice analítico de um documento do Word usando a biblioteca Aspose.Words para .NET. Seguindo o código e as instruções fornecidas, você pode facilmente eliminar o índice e melhorar o layout do seu documento. Lembre-se de adaptar o caminho do diretório e os nomes dos arquivos para atender às suas necessidades específicas.

### Perguntas frequentes

#### P: Por que devo usar Aspose.Words para remover o índice analítico de um documento do Word?

R: Aspose.Words é uma biblioteca de classes poderosa e versátil para manipular documentos do Word em aplicativos .NET. Ao usar Aspose.Words, você pode remover efetivamente o índice analítico de seus documentos, o que pode ser útil se o índice analítico for redundante ou desnecessário. Isso permite personalizar o conteúdo do seu documento e melhorar sua apresentação geral.

#### P: Como faço upload de um documento no Aspose.Words for .NET?

R: Para remover o índice analítico de um documento do Word, você deve primeiro carregar o documento na memória usando o método Load() de Aspose.Words. Aqui está um exemplo de código para carregar um documento de um diretório específico:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "your-document.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real para o seu documento.

#### P: Como faço para remover o índice analítico de um documento usando Aspose.Words?

 R: Para remover o TOC, você precisa percorrer o`FieldStart` digite nós do sumário no documento. Você pode armazenar esses nós para acesso rápido e criar uma lista de nós para excluir. Aqui está um exemplo de código:

```csharp
// Armazene nós FieldStart de campos TOC no documento para acesso rápido.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Esta é uma lista para armazenar nós encontrados dentro do TOC especificado. Eles serão excluídos no final deste método.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Verifique se o índice do índice especificado existe.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// É mais seguro armazenar esses nós e excluí-los todos no final.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Quando encontramos um nó FieldEnd do tipo FieldTOC,
//sabemos que estamos no final do TOC atual e paramos por aqui.
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

#### P: Como salvar o documento editado no Aspose.Words for .NET?

R: Após excluir o índice, você deve salvar o documento modificado usando o método Save(). Especifique o caminho e formato do arquivo de saída desejado (por exemplo, DOCX) para o documento editado. Aqui está um exemplo de código:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```