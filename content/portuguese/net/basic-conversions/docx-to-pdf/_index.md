---
title: Converter arquivo do Word em PDF
linktitle: Converter arquivo do Word em PDF
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter documentos Word de Docx para PDF usando Aspose.Words for .NET. Tutorial passo a passo com exemplo de código-fonte.
type: docs
weight: 10
url: /pt/net/basic-conversions/docx-to-pdf/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como usar Aspose.Words for .NET para converter um documento Word no formato Docx para PDF. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Caso ainda não tenha feito isso, baixe e instale a biblioteca do[Aspose.Lançamentos](https://releases.aspose.com/words/net/).

## Etapa 1: inicializando o objeto Documento

 Primeiro, inicialize o`Document`objeto com o caminho para o seu documento de origem no formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Passo 2: Salvando o Documento em Formato PDF

 A seguir, salve o documento em formato PDF chamando o`Save` método no`Document` objeto e fornecendo o caminho e o nome do arquivo para o documento PDF de saída:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

É isso! Você converteu com sucesso um documento Word no formato Docx para PDF usando Aspose.Words for .NET.

### Exemplo de código-fonte para Docx To Pdf usando Aspose.Words for .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo de acordo com suas necessidades específicas.

### Perguntas frequentes sobre conversão de Word para PDF

#### Q1. Quais são os requisitos para realizar a conversão de DOCX em PDF com Aspose.Words for .NET?
Para executar a conversão de DOCX para PDF com Aspose.Words for .NET, você precisa:
Aspose.Words for .NET instalado em sua máquina
Um arquivo DOCX válido para converter
Uma licença válida para usar Aspose.Words for .NET (ou você pode usar a versão de teste gratuita)

#### Q2. Como posso instalar o Aspose.Words para .NET?
Você pode instalar o Aspose.Words for .NET seguindo estas etapas:

Abra o Visual Studio ou seu ambiente de desenvolvimento preferido.

Crie um novo projeto ou abra um projeto existente.

Clique com o botão direito no projeto no Solution Explorer.

Selecione "Gerenciar pacotes NuGet" no menu de contexto.

Procure por "Aspose.Words" na caixa de pesquisa.

Selecione a versão mais recente do Aspose.Words for .NET.

Clique em “Instalar” para adicionar a referência ao seu projeto.

#### Q3. Que outras opções de conversão estão disponíveis com Aspose.Words for .NET?
Além de converter DOCX em PDF, Aspose.Words for .NET suporta várias outras conversões, como:

DOCX para outros formatos de arquivo, como DOC, RTF, HTML, XML, etc.

Converta arquivos PDF para formatos como DOCX, DOC, HTML, etc.

Conversão de arquivos EPUB, ODT, OTT, TXT, etc. para outros formatos.


#### Q4. Onde posso encontrar mais exemplos de código e recursos para processamento de palavras com Aspose.Words for .NET?
 Você pode encontrar mais exemplos de código e recursos no[Referência da API Aspose.Words para .NET](https://reference.aspose.com/words/net/) e[Tutoriais da API Aspose.Words para .NET](https://reference.aspose.com/tutorials/words/net/). Esses recursos fornecem guias passo a passo, exemplos de código e tutoriais.