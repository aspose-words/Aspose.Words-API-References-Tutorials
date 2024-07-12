---
title: Retorno de chamada para salvar página
linktitle: Retorno de chamada para salvar página
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como personalizar o salvamento de páginas de documentos em imagens com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-imagesaveoptions/page-saving-callback/
---

Neste tutorial, exploraremos o código-fonte C# fornecido para usar o retorno de chamada de salvamento de página com opções de salvamento de imagem Aspose.Words para .NET. Este recurso permite realizar ações personalizadas ao salvar cada página de um documento como uma imagem.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Nesta etapa, configuramos as opções de salvamento da imagem criando um novo`ImageSaveOptions` objeto. Especificamos o formato de backup desejado, aqui “Png” para o formato PNG. Nós usamos`PageSet` para especificar o intervalo de páginas a salvar, aqui da primeira à última página do documento (`doc.PageCount - 1`). Também definimos`PageSavingCallback` para uma instância de`HandlePageSavingCallback`, que é uma classe personalizada para lidar com o retorno de chamada de salvamento de página.

## Etapa 4: implementando o retorno de chamada para salvar página

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implemente suas ações personalizadas aqui
         // Você pode acessar as informações da página através da propriedade "args.PageIndex"
         // Você também pode alterar as opções de salvamento de cada página individualmente
     }
}
```

 Nesta etapa, implementamos o`HandlePageSavingCallback` classe que implementa o`IPageSavingCallback` interface. Você pode personalizar esta classe adicionando suas ações específicas no`PageSaving` método. Você pode acessar as informações da página através do`args.PageIndex` propriedade do`PageSavingArgs` objeto passado como argumento.

## Etapa 5: Salvar páginas como imagens

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Nesta etapa final, salvamos cada página do documento como uma imagem usando o`Save` método e passando o caminho para o arquivo de saída com o`.png` extensão, juntamente com as opções de salvamento especificadas.

Agora você pode executar o código-fonte para realizar ações personalizadas ao salvar cada página do documento como uma imagem. O arquivo resultante será salvo no diretório especificado com o nome "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Exemplo de código-fonte para retorno de chamada para salvar página usando Aspose.Words for .NET


```csharp 
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Conclusão

Neste tutorial, exploramos a funcionalidade de retorno de chamada para salvar página com opções de salvamento de imagem Aspose.Words para .NET. Aprendemos como realizar ações personalizadas ao salvar cada página de um documento como uma imagem.

Este recurso é útil quando você deseja realizar operações específicas em cada página ao converter para imagens. Você pode acessar informações da página e usá-las para personalizar opções de backup ou executar outro processamento específico da página.

Aspose.Words for .NET oferece uma ampla gama de recursos avançados para manipulação e geração de documentos. O Lembrete de Salvar Página é uma das muitas ferramentas poderosas que oferece para personalizar o processo de salvar páginas em imagens.