---
title: Retorno de chamada para salvar página
linktitle: Retorno de chamada para salvar página
second_title: API de processamento de documentos Aspose.Words
description: Aprenda a salvar cada página de um documento do Word como uma imagem PNG separada usando Aspose.Words for .NET com nosso guia passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/programming-with-imagesaveoptions/page-saving-callback/
---
## Introdução

Ei! Você já sentiu a necessidade de salvar cada página de um documento do Word como imagens separadas? Talvez você queira dividir um relatório grande em recursos visuais de fácil digestão ou talvez precise criar miniaturas para uma visualização. Seja qual for o motivo, usar Aspose.Words for .NET torna essa tarefa muito fácil. Neste guia, orientaremos você no processo de configuração de um retorno de chamada para salvar página para salvar cada página de um documento como uma imagem PNG individual. Vamos mergulhar de cabeça!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Aspose.Words for .NET: Se ainda não o fez, baixe e instale-o em[aqui](https://releases.aspose.com/words/net/).
2. Visual Studio: qualquer versão deve funcionar, mas usarei o Visual Studio 2019 para este guia.
3. Conhecimento básico de C#: você precisará de um conhecimento básico de C# para acompanhar.

## Importar namespaces

Primeiro, precisamos importar os namespaces necessários. Isso nos ajuda a acessar as classes e métodos necessários sem digitar o namespace completo todas as vezes.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: configure seu diretório de documentos

Tudo bem, vamos começar definindo o caminho para o diretório do seu documento. É aqui que o documento do Word de entrada está localizado e onde as imagens de saída serão salvas.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregue seu documento

A seguir, carregaremos o documento que você deseja processar. Certifique-se de que seu documento ("Rendering.docx") esteja no diretório especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: configurar opções para salvar imagens

Precisamos configurar as opções para salvar imagens. Neste caso, estamos salvando as páginas como arquivos PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 Aqui,`PageSet` especifica o intervalo de páginas a serem salvas e`PageSavingCallback` aponta para nossa classe de retorno de chamada personalizada.

## Etapa 4: implementar o retorno de chamada para salvar página

Agora, vamos implementar a classe de retorno de chamada que trata de como cada página é salva.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 Esta classe implementa o`IPageSavingCallback` interface e dentro do`PageSaving` método, definimos o padrão de nomenclatura para cada página salva.

## Etapa 5: salve o documento como imagens

Por fim, salvamos o documento usando as opções configuradas.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Conclusão

E aí está! Você configurou com êxito um retorno de chamada de salvamento de página para salvar cada página de um documento do Word como uma imagem PNG separada usando Aspose.Words for .NET. Essa técnica é extremamente útil para vários aplicativos, desde a criação de visualizações de páginas até a geração de imagens de páginas individuais para relatórios. 

Boa codificação!

## Perguntas frequentes

### Posso salvar páginas em formatos diferentes de PNG?  
 Sim, você pode salvar páginas em diferentes formatos, como JPEG, BMP e TIFF, alterando o`SaveFormat` em`ImageSaveOptions`.

### E se eu quiser salvar apenas páginas específicas?  
 Você pode especificar as páginas que deseja salvar ajustando o`PageSet` parâmetro em`ImageSaveOptions`.

### É possível personalizar a qualidade da imagem?  
 Absolutamente! Você pode definir propriedades como`ImageSaveOptions.JpegQuality` para controlar a qualidade das imagens de saída.

### Como posso lidar com documentos grandes de forma eficiente?  
Para documentos grandes, considere processar páginas em lotes para gerenciar o uso de memória de maneira eficaz.

### Onde posso encontrar mais informações sobre Aspose.Words for .NET?  
 Confira a[documentação](https://reference.aspose.com/words/net/) para guias e exemplos completos.