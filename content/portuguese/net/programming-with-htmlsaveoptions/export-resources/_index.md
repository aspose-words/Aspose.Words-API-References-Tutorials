---
title: Exportar recursos
linktitle: Exportar recursos
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exportar recursos como CSS e fontes enquanto salva documentos do Word como HTML usando Aspose.Words for .NET. Siga nosso guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-resources/
---
## Introdução

Olá, colega entusiasta de tecnologia! Se você já precisou converter documentos do Word em HTML, você está no lugar certo. Hoje estamos mergulhando no maravilhoso mundo do Aspose.Words for .NET. Esta poderosa biblioteca facilita o trabalho programático com documentos do Word. Neste tutorial, percorreremos as etapas para exportar recursos, como fontes e CSS, ao salvar um documento do Word como HTML usando Aspose.Words for .NET. Aperte o cinto para um passeio divertido e informativo!

## Pré-requisitos

Antes de mergulharmos no código, vamos ter certeza de que você tem tudo o que precisa para começar. Aqui está uma lista de verificação rápida:

1.  Visual Studio: certifique-se de ter o Visual Studio instalado em sua máquina. Você pode baixá-lo no[Site do Visual Studio](https://visualstudio.microsoft.com/).
2.  Aspose.Words for .NET: Você precisará da biblioteca Aspose.Words for .NET. Se você ainda não o adquiriu, faça um teste gratuito em[Aspose Lançamentos](https://releases.aspose.com/words/net/) ou compre-o no[Aspose Loja](https://purchase.aspose.com/buy).
3. Conhecimento básico de C#: uma compreensão fundamental de C# o ajudará a acompanhar os exemplos de código.

Entendeu tudo isso? Ótimo! Vamos prosseguir com a importação dos namespaces necessários.

## Importar namespaces

Para usar Aspose.Words for .NET, você precisa incluir os namespaces relevantes em seu projeto. Veja como você faz isso:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Esses namespaces são cruciais para acessar as classes e métodos Aspose.Words que usaremos em nosso tutorial.

Vamos detalhar o processo de exportação de recursos ao salvar um documento do Word como HTML. Faremos isso passo a passo, para que seja fácil de seguir.

## Etapa 1: configure seu diretório de documentos

Em primeiro lugar, você precisa especificar o caminho para o diretório de documentos. É aqui que o seu documento Word está localizado e onde o arquivo HTML será salvo.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o seu diretório.

## Etapa 2: carregue o documento do Word

 A seguir, vamos carregar o documento Word que deseja converter para HTML. Para este tutorial, usaremos um documento chamado`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Esta linha de código carrega o documento do diretório especificado.

## Etapa 3: configurar opções de salvamento de HTML

Para exportar recursos como CSS e fontes, você precisa configurar o`HtmlSaveOptions`. Esta etapa é crucial para garantir que sua saída HTML esteja bem estruturada e inclua os recursos necessários.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://exemplo.com/recursos"
};
```

Vamos detalhar o que cada opção faz:
- `CssStyleSheetType = CssStyleSheetType.External`: esta opção especifica que os estilos CSS devem ser salvos em uma folha de estilo externa.
- `ExportFontResources = true`: isso permite a exportação de recursos de fontes.
- `ResourceFolder = dataDir + "Resources"`: especifica a pasta local onde os recursos (como fontes e arquivos CSS) serão salvos.
- `ResourceFolderAlias = "http://example.com/resources"`: define um alias para a pasta de recursos, que será usada no arquivo HTML.

## Etapa 4: salve o documento como HTML

Com as opções de salvamento configuradas, a etapa final é salvar o documento como um arquivo HTML. Veja como você faz isso:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Esta linha de código salva o documento em formato HTML, junto com os recursos exportados.

## Conclusão

aí está! Você exportou recursos com êxito ao salvar um documento do Word como HTML usando Aspose.Words for .NET. Com esta biblioteca poderosa, lidar programaticamente com documentos do Word torna-se muito fácil. Esteja você trabalhando em um aplicativo da web ou apenas precise converter documentos para uso offline, o Aspose.Words tem o que você precisa.

## Perguntas frequentes

### Posso exportar imagens junto com fontes e CSS?
 Sim você pode! Aspose.Words for .NET também oferece suporte à exportação de imagens. Apenas certifique-se de configurar o`HtmlSaveOptions` de acordo.

### Existe uma maneira de incorporar CSS em vez de usar uma folha de estilo externa?
 Absolutamente. Você pode definir`CssStyleSheetType` para`CssStyleSheetType.Embedded` se você preferir estilos incorporados.

### Como posso personalizar o nome do arquivo HTML de saída?
 Você pode especificar qualquer nome de arquivo que desejar no`doc.Save` método. Por exemplo,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### O Aspose.Words oferece suporte a outros formatos além de HTML?
 Sim, suporta vários formatos, incluindo PDF, DOCX, TXT e muito mais. Confira a[documentação](https://reference.aspose.com/words/net/) para obter uma lista completa.

### Onde posso obter mais suporte e recursos?
Para obter mais ajuda, visite o[Fórum de suporte Aspose.Words](https://forum.aspose.com/c/words/8) . Você também pode encontrar documentação detalhada e exemplos no[Aspor site](https://reference.aspose.com/words/net/).