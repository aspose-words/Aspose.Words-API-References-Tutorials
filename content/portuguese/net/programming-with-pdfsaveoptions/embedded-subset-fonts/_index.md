---
title: Incorporar fontes de subconjunto em documento PDF
linktitle: Incorporar fontes de subconjunto em documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Reduza o tamanho do arquivo PDF incorporando apenas os subconjuntos de fontes necessários usando Aspose.Words for .NET. Siga nosso guia passo a passo para otimizar seus PDFs com eficiência.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---
## Introdução

Você já percebeu como alguns arquivos PDF são muito maiores que outros, mesmo quando contêm conteúdo semelhante? O culpado geralmente está nas fontes. Incorporar fontes em um PDF garante que ele tenha a mesma aparência em qualquer dispositivo, mas também pode aumentar o tamanho do arquivo. Felizmente, Aspose.Words for .NET oferece um recurso útil para incorporar apenas os subconjuntos de fontes necessários, mantendo seus PDFs simples e eficientes. Este tutorial irá guiá-lo através do processo, passo a passo.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Aspose.Words para .NET: você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
- Ambiente .NET: certifique-se de ter um ambiente de desenvolvimento .NET funcional.
- Conhecimento básico de C#: A familiaridade com a programação C# o ajudará a acompanhar.

## Importar namespaces

Para usar Aspose.Words for .NET, você precisa importar os namespaces necessários em seu projeto. Adicione-os no topo do seu arquivo C#:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: carregue o documento

 Primeiro, precisamos carregar o documento Word que queremos converter para PDF. Isto é feito usando o`Document` classe fornecida por Aspose.Words.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Este trecho de código carrega o documento localizado em`dataDir` . Certifique-se de substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o seu documento.

## Passo 2: Configurar opções para salvar PDF

 A seguir, configuramos o`PdfSaveOptions` para garantir que apenas os subconjuntos de fontes necessários sejam incorporados. Definindo`EmbedFullFonts` para`false`, dizemos ao Aspose.Words para incorporar apenas os glifos usados no documento.

```csharp
// O PDF de saída conterá subconjuntos das fontes do documento.
// Somente os glifos usados no documento são incluídos nas fontes do PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

Esta etapa pequena, mas crucial, ajuda a reduzir significativamente o tamanho do arquivo PDF.

## Etapa 3: salve o documento como PDF

 Finalmente, salvamos o documento como PDF usando o`Save` método, aplicando o configurado`PdfSaveOptions`.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf", saveOptions);
```

 Este código irá gerar um arquivo PDF com o nome`WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf` no diretório especificado, com apenas os subconjuntos de fontes necessários incorporados.

## Conclusão

aí está! Seguindo estas etapas simples, você pode reduzir com eficiência o tamanho de seus arquivos PDF incorporando apenas os subconjuntos de fontes necessários usando Aspose.Words for .NET. Isto não só economiza espaço de armazenamento, mas também garante tempos de carregamento mais rápidos e melhor desempenho, especialmente para documentos com fontes extensas.

## Perguntas frequentes

### Por que devo incorporar apenas subconjuntos de fontes em um PDF?
Incorporar apenas os subconjuntos de fontes necessários pode reduzir significativamente o tamanho do arquivo PDF sem comprometer a aparência e a legibilidade do documento.

### Posso voltar a incorporar fontes completas, se necessário?
 Sim você pode. Basta definir o`EmbedFullFonts`propriedade para`true` no`PdfSaveOptions`.

### O Aspose.Words for .NET oferece suporte a outros recursos de otimização de PDF?
Absolutamente! Aspose.Words for .NET oferece uma variedade de opções para otimizar PDFs, incluindo compactação de imagens e remoção de objetos não utilizados.

### Que tipos de fontes podem ser incorporados em subconjuntos usando Aspose.Words for .NET?
Aspose.Words for .NET suporta incorporação de subconjuntos para todas as fontes TrueType usadas no documento.

### Como posso verificar quais fontes estão incorporadas no meu PDF?
Você pode abrir o PDF no Adobe Acrobat Reader e verificar as propriedades na guia Fontes para ver as fontes incorporadas.
