---
title: Reduza o tamanho do arquivo PDF não incorporando fontes principais
linktitle: Reduza o tamanho do arquivo PDF não incorporando fontes principais
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como reduzir o tamanho do arquivo PDF não incorporando fontes principais usando Aspose.Words for .NET. Siga nosso guia passo a passo para otimizar seus PDFs.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---
## Introdução

Você já coçou a cabeça e se perguntou por que seus arquivos PDF são tão grandes? Bem, você não está sozinho. Um culpado comum é a incorporação de fontes básicas como Arial e Times New Roman. Felizmente, o Aspose.Words for .NET tem uma maneira bacana de resolver esse problema. Neste tutorial, mostrarei como reduzir o tamanho do arquivo PDF evitando a incorporação dessas fontes principais. Vamos mergulhar de cabeça!

## Pré-requisitos

Antes de embarcarmos nesta jornada emocionante, vamos ter certeza de que você tem tudo o que precisa. Aqui está uma lista de verificação rápida:

-  Aspose.Words for .NET: Certifique-se de ter o Aspose.Words for .NET instalado. Se você ainda não tem, pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: você precisará de um ambiente de desenvolvimento como o Visual Studio.
- Um documento do Word: usaremos um documento do Word (por exemplo, "Rendering.docx") para este tutorial.
- Conhecimento básico de C#: Um entendimento básico de C# o ajudará a acompanhar.

Tudo bem, agora que estamos todos prontos, vamos ao que interessa!

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Esta etapa garante que tenhamos acesso a todas as funcionalidades do Aspose.Words de que precisamos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: inicialize seu diretório de documentos

Antes de começarmos a manipular nosso documento, precisamos especificar o diretório onde nossos documentos estão armazenados. Isso é essencial para acessar os arquivos.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde seu documento do Word está localizado.

## Etapa 2: carregue o documento do Word

A seguir, precisamos carregar o documento Word que queremos converter para PDF. Neste exemplo, estamos usando um documento chamado “Rendering.docx”.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Esta linha de código carrega o documento na memória, pronto para processamento posterior.

## Passo 3: Configurar opções para salvar PDF

Agora vem a parte mágica! Configuraremos as opções de salvamento de PDF para evitar a incorporação de fontes principais. Esta é a etapa principal que ajuda a reduzir o tamanho do arquivo PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    UseCoreFonts = true
};
```

 Contexto`UseCoreFonts` para`true` garante que fontes básicas como Arial e Times New Roman não sejam incorporadas no PDF, o que reduz significativamente o tamanho do arquivo.

## Etapa 4: salve o documento como PDF

Por fim, salvamos o documento do Word como PDF usando as opções de salvamento configuradas. Esta etapa gera o arquivo PDF sem incorporar as fontes principais.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

E aí está! Seu arquivo PDF agora está salvo no diretório especificado, sem aquelas fontes principais volumosas.

## Conclusão

Reduzir o tamanho do arquivo PDF pode ser muito fácil com Aspose.Words for .NET. Ao evitar a incorporação de fontes principais, você pode diminuir significativamente o tamanho do arquivo, facilitando o compartilhamento e o armazenamento de seus documentos. Espero que este tutorial tenha sido útil e tenha lhe dado uma compreensão clara do processo. Lembre-se de que pequenos ajustes podem fazer uma grande diferença!

## Perguntas frequentes

### Por que devo evitar incorporar fontes principais em PDFs?
Evitar a incorporação de fontes principais reduz o tamanho do arquivo, facilitando o compartilhamento e o armazenamento.

### Ainda posso visualizar o PDF corretamente sem fontes principais incorporadas?
Sim, fontes básicas como Arial e Times New Roman geralmente estão disponíveis na maioria dos sistemas.

### E se eu precisar incorporar fontes personalizadas?
 Você pode personalizar o`PdfSaveOptions`para incorporar fontes específicas conforme necessário.

### O uso do Aspose.Words for .NET é gratuito?
 Aspose.Words for .NET requer uma licença. Você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Onde posso encontrar mais documentação sobre Aspose.Words for .NET?
 Você pode encontrar documentação detalhada[aqui](https://reference.aspose.com/words/net/).