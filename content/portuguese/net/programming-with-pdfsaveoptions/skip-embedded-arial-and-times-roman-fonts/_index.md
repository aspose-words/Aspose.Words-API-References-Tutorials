---
title: Otimize o tamanho do PDF com fontes Skip Embedded Arial e Times Roman
linktitle: Otimize o tamanho do PDF com fontes Skip Embedded Arial e Times Roman
second_title: API de processamento de documentos Aspose.Words
description: Otimize o tamanho do PDF ignorando as fontes Arial e Times Roman incorporadas usando Aspose.Words for .NET. Siga este guia passo a passo para agilizar seus arquivos PDF.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---
## Introdução

Você já se viu em uma situação em que o tamanho do arquivo PDF é muito grande? É como fazer as malas para as férias e perceber que sua mala está estourando. Você sabe que precisa perder algum peso, mas do que você abre mão? Ao trabalhar com arquivos PDF, especialmente aqueles convertidos de documentos do Word, as fontes incorporadas podem aumentar o tamanho do arquivo. Felizmente, Aspose.Words for .NET oferece uma solução elegante para manter seus PDFs simples e significativos. Neste tutorial, veremos como otimizar o tamanho do PDF ignorando as fontes Arial e Times Roman incorporadas. Vamos começar!

## Pré-requisitos

Antes de entrarmos no âmago da questão, há algumas coisas que você precisará:
-  Aspose.Words for .NET: Certifique-se de ter esta poderosa biblioteca instalada. Caso contrário, você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
- Uma compreensão básica de C#: isso o ajudará a acompanhar os trechos de código.
- Um documento Word: usaremos um documento de amostra para demonstrar o processo. 

## Importar namespaces

Em primeiro lugar, certifique-se de ter importado os namespaces necessários. Isso prepara o terreno para acessar as funcionalidades do Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Tudo bem, vamos detalhar o processo passo a passo.

## Etapa 1: configure seu ambiente

Para começar, você precisa configurar seu ambiente de desenvolvimento. Abra seu IDE C# favorito (como o Visual Studio) e crie um novo projeto.

## Etapa 2: carregue o documento do Word

A próxima etapa é carregar o documento do Word que deseja converter em PDF. Certifique-se de que seu documento esteja no diretório correto.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Neste trecho, substitua`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório do seu documento.

## Passo 3: Configurar opções para salvar PDF

Agora, precisamos configurar as opções de salvamento do PDF para controlar como as fontes são incorporadas. Por padrão, todas as fontes são incorporadas, o que pode aumentar o tamanho do arquivo. Vamos alterar essa configuração.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll
};
```

## Etapa 4: salve o documento como PDF

Por fim, salve o documento como PDF com as opções de salvamento especificadas. É aqui que a mágica acontece.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Este comando salva seu documento como um PDF chamado “OptimizedPDF.pdf” no diretório especificado.

## Conclusão

E aí está! Você acabou de aprender como otimizar o tamanho do seu arquivo PDF ignorando a incorporação de fontes Arial e Times Roman usando Aspose.Words for .NET. Esse simples ajuste pode reduzir significativamente o tamanho dos arquivos, tornando-os mais fáceis de compartilhar e armazenar. É como ir à academia para pegar seus PDFs, perdendo peso desnecessário e mantendo todos os itens essenciais intactos.

## Perguntas frequentes

### Por que devo ignorar a incorporação de fontes Arial e Times Roman?
Ignorar essas fontes comuns pode reduzir o tamanho do arquivo PDF, pois a maioria dos sistemas já possui essas fontes instaladas.

### Isso afetará a aparência do meu PDF?
Não, não vai. Como Arial e Times Roman são fontes padrão, a aparência permanece consistente em diferentes sistemas.

### Posso pular a incorporação de outras fontes também?
Sim, você pode configurar as opções de salvamento para ignorar a incorporação de outras fontes, se necessário.

### O Aspose.Words para .NET é gratuito?
Aspose.Words for .NET oferece uma avaliação gratuita que você pode baixar[aqui](https://releases.aspose.com/) , mas para acesso total, você precisa adquirir uma licença[aqui](https://purchase.aspose.com/buy).

### Onde posso encontrar mais tutoriais sobre Aspose.Words for .NET?
 Você pode encontrar documentação e tutoriais abrangentes[aqui](https://reference.aspose.com/words/net/).