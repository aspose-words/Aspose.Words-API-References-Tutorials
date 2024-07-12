---
title: Obtenha o intervalo de páginas JPEG
linktitle: Obtenha o intervalo de páginas JPEG
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como obter uma variedade de páginas JPEG com Aspose.Words for .NET. Tutorial completo para extrair imagens personalizadas.
type: docs
weight: 10
url: /pt/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Neste tutorial, exploraremos o código-fonte C# fornecido para o recurso "Obter intervalo de páginas JPEG" com Aspose.Words for .NET. Este recurso permite converter um intervalo específico de páginas de um documento em imagens no formato JPEG.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.Words for .NET. Certifique-se de ter adicionado as referências necessárias e importado os namespaces apropriados.

## Passo 2: Carregando o documento

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Nesta etapa, carregamos o documento usando o`Document` método e passando o caminho para o arquivo DOCX a ser carregado.

## Etapa 3: configurar opções de backup de imagem

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Nesta etapa, configuramos opções de backup para imagens. Criamos um novo`ImageSaveOptions` objeto especificando o formato de salvamento desejado, aqui "Jpeg" para o formato JPEG. Também definimos o intervalo de páginas a serem convertidas usando o`PageSet`objeto. Finalmente, ajustamos o brilho e o contraste da imagem usando o`ImageBrightness`e`ImageContrast` propriedades, respectivamente. Também alteramos a resolução horizontal usando o`HorizontalResolution` propriedade.

## Etapa 4: fazer backup de imagens

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Nesta última etapa, salvamos as imagens do intervalo de páginas especificado no formato JPEG usando o`Save` método e passando o caminho para o arquivo de saída, junto com as opções de salvamento especificadas.

Agora você pode executar o código-fonte para converter um intervalo específico de páginas do seu documento em imagens JPEG. O arquivo resultante será salvo no diretório especificado com o nome "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Exemplo de código-fonte para obter intervalo de páginas Jpeg usando Aspose.Words For .NET

```csharp 
 // Caminho para o diretório do seu documento
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Defina “PageSet” como “0” para converter apenas a primeira página de um documento.
options.PageSet = new PageSet(0);

// Altere o brilho e o contraste da imagem.
// Ambos estão em uma escala de 0 a 1 e estão em 0,5 por padrão.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Altere a resolução horizontal.
// O valor padrão para essas propriedades é 96,0, para uma resolução de 96 dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Conclusão

Neste tutorial, exploramos a funcionalidade de obter um intervalo de páginas JPEG com Aspose.Words for .NET. Aprendemos como converter um intervalo específico de páginas de um documento em imagens no formato JPEG, enquanto personalizamos as opções de salvamento.

Este recurso é útil quando você deseja extrair páginas específicas de um documento e salvá-las como imagens JPEG. Você também pode ajustar o brilho, o contraste e a resolução horizontal das imagens para obter resultados personalizados.

Aspose.Words for .NET oferece uma ampla gama de recursos avançados para manipulação e geração de documentos. Obter um intervalo de páginas JPEG é uma das muitas ferramentas poderosas que ele coloca à sua disposição.

Sinta-se à vontade para integrar esse recurso em seus projetos Aspose.Words for .NET para obter imagens JPEG de alta qualidade de seus documentos.