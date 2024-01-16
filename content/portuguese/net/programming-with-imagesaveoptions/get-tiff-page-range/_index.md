---
title: Obtenha o intervalo de páginas Tiff
linktitle: Obtenha o intervalo de páginas Tiff
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como extrair uma série de páginas TIFF com Aspose.Words for .NET. Tutorial completo para arquivos TIFF personalizados.
type: docs
weight: 10
url: /pt/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

Neste tutorial, exploraremos o código-fonte C# fornecido para obter uma variedade de páginas TIFF com Aspose.Words for .NET. Este recurso permite extrair um intervalo específico de páginas de um documento e salvá-las como um arquivo TIFF.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.Words for .NET. Certifique-se de ter adicionado as referências necessárias e importado os namespaces apropriados.

## Passo 2: Carregando o documento

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Nesta etapa, carregamos o documento usando o`Document` método e passando o caminho para o arquivo DOCX a ser carregado.

## Passo 3: Salvando o documento completo em TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

Nesta etapa salvamos o documento completo em formato TIFF utilizando o`Save` método e especificando o caminho para o arquivo de saída com a extensão`.tiff`.

## Etapa 4: configurar opções de backup para o intervalo de páginas

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Nesta etapa, configuramos opções de backup para o intervalo de páginas específico. Criamos um novo`ImageSaveOptions` objeto especificando o formato de salvamento desejado, aqui "Tiff" para o formato TIFF. Nós usamos`PageSet` para especificar o intervalo de páginas que queremos extrair, aqui da página 0 à página 1 (inclusive). Também definimos a compactação TIFF para`Ccitt4` e a resolução para 160 dpi.

## Etapa 5: salvando o intervalo de páginas em TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Nesta última etapa, salvamos o intervalo de páginas especificado no formato TIFF usando o`Save` método e passando o caminho para o arquivo de saída com`.tiff` extensão, junto com as opções de salvamento especificadas.

Agora você pode executar o código-fonte para obter um intervalo específico de páginas do seu documento e salvá-las como um arquivo TIFF. Os arquivos resultantes serão salvos no diretório especificado com os nomes "WorkingWithImageSaveOptions.MultipageTiff.tiff" para o documento completo e "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" para o intervalo de páginas especificado.

### Exemplo de código-fonte de obter intervalo de páginas Tiff usando Aspose.Words for .NET

```csharp 

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Conclusão

Neste tutorial, exploramos a funcionalidade de obter uma variedade de páginas TIFF com Aspose.Words for .NET. Aprendemos como extrair um intervalo específico de páginas de um documento e salvá-las como um arquivo TIFF.

Este recurso é útil quando você deseja extrair apenas determinadas páginas de um documento e salvá-las em um formato de imagem padrão, como TIFF. Você também pode personalizar as opções de compactação e resolução para obter arquivos TIFF da melhor qualidade.

Aspose.Words for .NET oferece uma ampla gama de recursos avançados para manipulação e geração de documentos. Obter um intervalo de páginas TIFF é uma das muitas ferramentas poderosas que ele coloca à sua disposição.

Sinta-se à vontade para integrar esta funcionalidade em seus projetos Aspose.Words for .NET para extrair e salvar intervalos específicos de páginas de seus documentos no formato TIFF.