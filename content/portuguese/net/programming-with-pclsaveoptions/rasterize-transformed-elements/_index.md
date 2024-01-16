---
title: Rasterizar elementos transformados
linktitle: Rasterizar elementos transformados
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como desabilitar a rasterização de elementos transformados ao converter para o formato PCL com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET é uma biblioteca poderosa para criar, manipular e converter documentos Word em um aplicativo C#. Entre os recursos oferecidos pelo Aspose.Words está a capacidade de rasterizar elementos transformados ao converter documentos para diferentes formatos. Neste guia, mostraremos como usar o código-fonte C# do Aspose.Words for .NET para desabilitar a rasterização de elementos transformados ao converter um documento para o formato PCL.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca popular que torna o processamento de palavras com documentos do Word fácil e eficiente. Ele oferece uma ampla gama de recursos para criação, edição e conversão de documentos do Word, incluindo suporte para rasterização de elementos transformados durante a conversão.

## Carregando o documento do Word

O primeiro passo é carregar o documento Word que deseja converter para o formato PCL. Use a classe Document para carregar o documento do arquivo de origem. Aqui está um exemplo :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Neste exemplo, estamos carregando o documento "Rendering.docx" localizado no diretório de documentos.

## Configurando opções de backup

A próxima etapa é configurar as opções de salvamento para conversão para o formato PCL. Use a classe PclSaveOptions e defina a propriedade RasterizeTransformedElements como false. Veja como fazer isso:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Criamos um novo objeto PclSaveOptions e definimos a propriedade SaveFormat como SaveFormat.Pcl para especificar que queremos salvar o documento no formato PCL. A seguir, definimos a propriedade RasterizeTransformedElements como false para desabilitar a rasterização de elementos transformados.

## Convertendo o documento para o formato PCL

Agora que configuramos as opções de salvamento, podemos prosseguir com a conversão do documento para o formato PCL. Use o método Save da classe Document para salvar o documento convertido no formato PCL especificando opções de salvamento. Aqui está um exemplo :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

Neste exemplo, salvamos o documento convertido como "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" usando as opções de salvamento especificadas.

### Exemplo de código-fonte para o recurso "Rasterizar elementos transformados" com Aspose.Words for .NET

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento do Word


Document doc = new Document(dataDir + "Rendering.docx");

// Configure opções de backup para conversão para formato PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Converta o documento para o formato PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Conclusão

Neste guia, abordamos como usar Aspose.Words for .NET para desabilitar a rasterização de elementos transformados ao converter um documento para o formato PCL usando o código-fonte C# fornecido. Seguindo as etapas fornecidas, você pode controlar facilmente o comportamento de rasterização dos elementos transformados ao converter seus documentos do Word para diferentes formatos. Aspose.Words oferece enorme flexibilidade e poder para trabalhar com os elementos transformados, permitindo criar documentos convertidos precisamente para suas necessidades específicas.