---
title: Exportar marcadores de rodapé de cabeçalho de documento do Word para documento PDF
linktitle: Exportar marcadores de rodapé de cabeçalho de documento do Word para documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exportar marcadores de cabeçalho e rodapé de um documento do Word para PDF usando Aspose.Words for .NET com nosso guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---
## Introdução

Converter documentos Word em PDF é uma tarefa comum, especialmente quando você deseja compartilhar ou arquivar documentos preservando sua formatação. Às vezes, esses documentos contêm marcadores importantes nos cabeçalhos e rodapés. Neste tutorial, percorreremos o processo de exportação desses marcadores de um documento Word para um PDF usando Aspose.Words for .NET.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

- Aspose.Words for .NET: Você precisa ter o Aspose.Words for .NET instalado. Você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento. Você pode usar o Visual Studio ou qualquer outro IDE compatível com .NET.
- Conhecimento básico de C#: É necessária familiaridade com programação C# para acompanhar os exemplos de código.

## Importar namespaces

Primeiramente, você precisa importar os namespaces necessários em seu projeto C#. Adicione estas linhas no topo do seu arquivo de código:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Vamos dividir o processo em etapas fáceis de seguir.

## Etapa 1: inicializar o documento

primeiro passo é carregar seu documento Word. Veja como você pode fazer isso:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

Nesta etapa, você simplesmente especifica o caminho para o diretório do documento e carrega o documento do Word.

## Passo 2: Configurar opções para salvar PDF

Em seguida, você precisa configurar as opções de salvamento do PDF para garantir que os marcadores nos cabeçalhos e rodapés sejam exportados corretamente.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

 Aqui, estamos configurando o`PdfSaveOptions` . O`DefaultBookmarksOutlineLevel` propriedade define o nível de estrutura de tópicos para marcadores e a propriedade`HeaderFooterBookmarksExportMode` propriedade garante que apenas a primeira ocorrência de marcadores em cabeçalhos e rodapés seja exportada.

## Etapa 3: salve o documento como PDF

Por fim, salve seu documento como PDF com as opções configuradas.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Nesta etapa, você salva o documento no caminho especificado com as opções configuradas.

## Conclusão

aí está! Seguindo essas etapas, você pode exportar facilmente marcadores de cabeçalhos e rodapés de um documento do Word para um PDF usando Aspose.Words for .NET. Este método garante que importantes auxílios à navegação em seu documento sejam preservados no formato PDF, facilitando a navegação dos leitores pelo documento.

## Perguntas frequentes

### Posso exportar todos os marcadores do documento Word para PDF?

 Sim você pode. No`PdfSaveOptions`, você pode ajustar as configurações para incluir todos os marcadores, se necessário.

### E se eu quiser exportar marcadores também do corpo do documento?

 Você pode configurar o`OutlineOptions` em`PdfSaveOptions` para incluir marcadores do corpo do documento.

### É possível personalizar os níveis de marcadores no PDF?

 Absolutamente! Você pode personalizar o`DefaultBookmarksOutlineLevel` propriedade para definir diferentes níveis de estrutura de tópicos para seus marcadores.

### Como lidar com documentos sem marcadores?

Se o seu documento não tiver marcadores, o PDF será gerado sem nenhum contorno de marcador. Certifique-se de que seu documento contenha marcadores se precisar deles no PDF.

### Posso usar este método para outros tipos de documentos como DOCX ou RTF?

Sim, Aspose.Words for .NET oferece suporte a vários tipos de documentos, incluindo DOCX, RTF e outros.