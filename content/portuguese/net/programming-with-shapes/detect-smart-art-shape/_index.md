---
title: Detectar forma de arte inteligente
linktitle: Detectar forma de arte inteligente
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como detectar formas Smart Art em um documento Word usando Aspose.Words for .NET, identificando representações gráficas.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/detect-smart-art-shape/
---

Este tutorial explica como detectar formas Smart Art em um documento do Word usando Aspose.Words for .NET. As formas Smart Art são representações gráficas usadas para apresentar visualmente informações e ideias.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregue o documento
 Carregue o documento do Word usando o`Document` construtor, passando o caminho para o documento como parâmetro.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Etapa 3: detectar formas de arte inteligente
 Iterar pelos nós filhos do tipo`Shape` no documento usando o`GetChildNodes`método. Verifique se cada forma possui Smart Art usando o`HasSmart Art` propriedade.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Etapa 4: produza o resultado
Imprima a contagem de formas com Smart Art detectadas no documento.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Exemplo de código-fonte para Detectar Smart Art Shape usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

É isso! Você detectou com sucesso formas Smart Art em seu documento do Word usando Aspose.Words for .NET.