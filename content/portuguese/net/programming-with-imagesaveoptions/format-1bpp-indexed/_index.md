---
title: Formato 1Bpp indexado
linktitle: Formato 1Bpp indexado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como formatar imagens em 1 bpp indexadas com Aspose.Words for .NET. Tutorial completo para imagens com baixa profundidade de cor.
type: docs
weight: 10
url: /pt/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Neste tutorial, exploraremos o código-fonte C# fornecido para a funcionalidade "Format 1Bpp Indexed" com Aspose.Words for .NET. Este recurso permite formatar imagens em um documento no formato PNG com profundidade de cor de 1 bit por pixel (1 bpp) e modo de cor indexada.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Nesta etapa, configuramos opções de backup para imagens. Criamos um novo`ImageSaveOptions`objeto especificando o formato de salvamento desejado, aqui "Png" para o formato PNG. Definimos também a página a incluir na imagem, o modo de cor preto e branco e o formato de pixel indexado de 1 bpp.

## Etapa 4: fazer backup de imagens

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Nesta última etapa, salvamos as imagens do documento no formato PNG usando o`Save` método e passando o caminho para o arquivo de saída, junto com as opções de salvamento especificadas.

Agora você pode executar o código-fonte para formatar as imagens do documento no formato PNG com profundidade de cor indexada de 1 bpp. O arquivo resultante será salvo no diretório especificado com o nome "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Exemplo de código-fonte para formato 1Bpp indexado usando Aspose.Words for .NET

```csharp 
 
			 // Caminho para o diretório do seu documento
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Conclusão

Neste tutorial, exploramos o recurso de formato indexado de 1Bpp com Aspose.Words for .NET. Aprendemos como formatar imagens em um documento no formato PNG com profundidade de cor de 1 bit por pixel (1 bpp) e modo de cor indexada.

Este recurso é útil quando você deseja obter imagens com baixa profundidade de cores e tamanho de arquivo pequeno. O formato indexado 1Bpp permite que as imagens sejam representadas usando uma paleta de cores indexadas, o que pode ser benéfico para algumas aplicações específicas.

Aspose.Words for .NET oferece uma ampla gama de recursos avançados para manipulação e geração de documentos. O formato indexado 1Bpp é uma das muitas ferramentas poderosas que coloca à sua disposição.