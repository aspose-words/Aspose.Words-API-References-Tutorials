---
title: Definir nível de compactação
linktitle: Definir nível de compactação
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir o nível de compactação ao salvar um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
Neste tutorial, exploraremos o código-fonte C# fornecido para definir o nível de compactação ao salvar um documento usando Aspose.Words for .NET. Este recurso permite controlar o nível de compactação do documento gerado.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.Words for .NET. Certifique-se de ter adicionado as referências necessárias e importado os namespaces apropriados.

## Passo 2: Carregando o documento

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Nesta etapa, carregamos o documento usando o`Document` método e passando o caminho para o arquivo DOCX a ser carregado.

## Etapa 3: configurar opções de backup OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 Nesta etapa, configuramos as opções de salvamento OOXML usando o`OoxmlSaveOptions` aula. Definimos o nível de compressão para`SuperFast` para obter uma compactação mais rápida.

## Etapa 4: salve o documento com o nível de compactação especificado

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 Nesta última etapa, salvamos o documento usando o`Save` método e passando o caminho para o arquivo de saída com o`.docx` extensão, junto com as opções de salvamento especificadas.

Agora você pode executar o código-fonte para definir o nível de compactação ao salvar um documento. O arquivo resultante será salvo no diretório especificado com o nome "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Exemplo de código-fonte para definir nível de compactação usando Aspose.Words for .NET 

```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Conclusão

Neste tutorial, exploramos a funcionalidade de definir o nível de compactação ao salvar um documento usando Aspose.Words for .NET. Ao especificar o nível apropriado de compactação, você pode otimizar o tamanho do documento e a velocidade de geração.

 O`OoxmlSaveOptions` classe fornece flexibilidade para controlar o nível de compactação, definindo o`CompressionLevel` propriedade a um valor apropriado, como`SuperFast`. Isso permite que você encontre o equilíbrio certo entre tamanho de arquivo e velocidade de backup com base em suas necessidades específicas.

Usar a compactação pode ser benéfico quando você precisa reduzir o tamanho dos arquivos gerados, especialmente para documentos grandes. Isso pode facilitar o armazenamento, o compartilhamento e a transmissão de documentos.

Aspose.Words for .NET oferece uma gama de opções e recursos poderosos para manipulação de documentos. Ao usar as opções de backup apropriadas, você pode personalizar o processo de geração de documentos e otimizar o desempenho do seu aplicativo.

Sinta-se à vontade para explorar mais recursos do Aspose.Words for .NET para aprimorar seu fluxo de trabalho de geração de documentos.
