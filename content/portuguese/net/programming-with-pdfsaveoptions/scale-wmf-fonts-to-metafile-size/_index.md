---
title: Reduza o tamanho do PDF com a escala de fontes Wmf para o tamanho do metarquivo
linktitle: Reduza o tamanho do PDF com a escala de fontes Wmf para o tamanho do metarquivo
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para reduzir o tamanho do PDF com escala de fontes wmf para o tamanho do metarquivo ao converter para PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---
## Introdução

Ao trabalhar com arquivos PDF, especialmente aqueles gerados a partir de documentos do Word contendo gráficos WMF (Windows Metafile), o gerenciamento de tamanho pode se tornar um aspecto crucial no manuseio de documentos. Uma maneira de controlar o tamanho do PDF é ajustando a forma como as fontes WMF são renderizadas no documento. Neste tutorial, exploraremos como reduzir o tamanho do PDF dimensionando fontes WMF para o tamanho do metarquivo usando Aspose.Words for .NET.

## Pré-requisitos

Antes de mergulhar nas etapas, certifique-se de ter o seguinte:

1. Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words instalada. Se não, você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: este tutorial pressupõe que você tenha um ambiente de desenvolvimento .NET configurado (como o Visual Studio) onde você pode escrever e executar código C#.
3. Compreensão básica de programação .NET: Familiaridade com conceitos básicos de programação .NET e sintaxe C# será útil.
4. Documento Word com gráficos WMF: Você precisará de um documento Word contendo gráficos WMF. Você pode usar seu próprio documento ou criar um para teste.

## Importar namespaces

Primeiro, você precisa importar os namespaces necessários em seu projeto C#. Isso lhe dará acesso às classes e métodos necessários para trabalhar com Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: carregue o documento do Word

 Para começar, carregue o documento do Word que contém os gráficos WMF. Isto é feito usando o`Document` classe de Aspose.Words.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "WMF with text.docx");
```

 Aqui,`dataDir` é um espaço reservado para o caminho do diretório do documento. Criamos uma instância do`Document` class passando o caminho para o arquivo do Word. Isso carrega o documento na memória, pronto para processamento posterior.

## Etapa 2: configurar opções de renderização de metarquivo

 Em seguida, você precisa configurar as opções de renderização do metarquivo. Especificamente, defina o`ScaleWmfFontsToMetafileSize`propriedade para`false`. Isso controla se as fontes WMF são dimensionadas para corresponder ao tamanho do metarquivo.

```csharp
// Crie uma nova instância de MetafileRenderingOptions
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
    ScaleWmfFontsToMetafileSize = false
};
```

 O`MetafileRenderingOptions` classe fornece opções de como os metarquivos (como WMF) são renderizados. Ao definir`ScaleWmfFontsToMetafileSize` para`false`, você está instruindo o Aspose.Words a não dimensionar as fontes de acordo com o tamanho do metarquivo, o que pode ajudar a reduzir o tamanho geral do PDF.

## Etapa 3: definir opções para salvar PDF

Agora, configure as opções de salvamento do PDF para usar as opções de renderização de metarquivo que você acabou de definir. Isso informa ao Aspose.Words como lidar com metarquivos ao salvar o documento como PDF.

```csharp
// Crie uma nova instância de PdfSaveOptions
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    MetafileRenderingOptions = metafileRenderingOptions
};
```

 O`PdfSaveOptions` class permite que você especifique várias configurações para salvar o documento como PDF. Ao atribuir o previamente configurado`MetafileRenderingOptions` para o`MetafileRenderingOptions` propriedade de`PdfSaveOptions`, você garante que o documento seja salvo de acordo com as configurações de renderização de metarquivo desejadas.

## Etapa 4: salve o documento como PDF

Por fim, salve o documento do Word como PDF usando as opções de salvamento configuradas. Isso aplicará todas as configurações, incluindo as opções de renderização de metarquivo, ao PDF de saída.


```csharp
// Salve o documento como PDF
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

 Nesta etapa, o`Save` método do`Document` class é usada para exportar o documento para um arquivo PDF. O caminho onde o PDF será salvo é especificado, juntamente com o`PdfSaveOptions` que incluem as configurações de renderização do metarquivo.

## Conclusão

Ao dimensionar as fontes WMF para o tamanho do metarquivo, você pode reduzir significativamente o tamanho dos arquivos PDF gerados a partir de documentos do Word. Essa técnica auxilia na otimização do armazenamento e distribuição de documentos sem comprometer a qualidade do conteúdo visual. Seguir as etapas descritas acima garante que seus arquivos PDF sejam mais gerenciáveis e de tamanho eficiente.

## Perguntas frequentes

### O que é WMF e por que é importante para o tamanho do PDF?

WMF (Windows Metafile) é um formato gráfico usado no Microsoft Windows. Ele pode conter dados vetoriais e bitmap. Como os dados vetoriais podem ser dimensionados e manipulados, é importante manuseá-los adequadamente para evitar arquivos PDF desnecessariamente grandes.

### Como o dimensionamento de fontes WMF para o tamanho do metarquivo afeta o PDF?

Dimensionar fontes WMF para o tamanho do metarquivo pode ajudar a reduzir o tamanho geral do PDF, evitando a renderização de fontes de alta resolução que pode aumentar o tamanho do arquivo.

### Posso usar outros formatos de metarquivo com Aspose.Words?

Sim, Aspose.Words suporta vários formatos de metarquivo, incluindo EMF (Enhanced Metafile) além de WMF.

### Esta técnica é aplicável a todos os tipos de documentos do Word?

Sim, esta técnica pode ser aplicada a qualquer documento Word que contenha gráficos WMF, auxiliando na otimização do tamanho do PDF gerado.

### Onde posso encontrar mais informações sobre Aspose.Words?

 Você pode explorar mais sobre Aspose.Words no[Documentação Aspose.Words](https://reference.aspose.com/words/net/) . Para downloads, testes e suporte, visite o[Página de download do Aspose.Words](https://releases.aspose.com/words/net/), [Comprar Aspose.Words](https://purchase.aspose.com/buy), [Avaliação Gratuita](https://releases.aspose.com/), [Licença Temporária](https://purchase.aspose.com/temporary-license/) , e[Apoiar](https://forum.aspose.com/c/words/8).