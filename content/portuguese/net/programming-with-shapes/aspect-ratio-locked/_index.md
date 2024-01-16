---
title: Proporção bloqueada
linktitle: Proporção bloqueada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como bloquear ou desbloquear a proporção de uma forma em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/aspect-ratio-locked/
---

Este tutorial explica como bloquear ou desbloquear a proporção de uma forma em um documento do Word usando Aspose.Words for .NET. Ao bloquear a proporção, você pode manter as proporções originais da forma ao redimensioná-la.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um novo documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir um formato de imagem
 Use o`InsertImage` método do`DocumentBuilder` objeto para inserir uma forma de imagem no documento. Forneça o caminho para o arquivo de imagem como parâmetro.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Etapa 4: bloquear ou desbloquear a proporção
 Colocou o`AspectRatioLocked` propriedade da forma para`true` ou`false` para bloquear ou desbloquear a proporção, respectivamente.

```csharp
shape.AspectRatioLocked = false; //Desbloqueie a proporção
```

## Etapa 5: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Exemplo de código-fonte para Aspect Ratio Locked usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

É isso! Você bloqueou ou desbloqueou com êxito a proporção de uma forma em seu documento do Word usando Aspose.Words for .NET.