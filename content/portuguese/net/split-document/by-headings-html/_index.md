---
title: Dividir documento do Word por títulos HTML
linktitle: Por títulos HTML
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para explicar o código-fonte C# do documento de palavra dividida por título do recurso HTML do Aspose.Words for .NET
type: docs
weight: 10
url: /pt/net/split-document/by-headings-html/
---
Neste tutorial, orientaremos você sobre como dividir um documento do Word em partes menores usando o recurso By HTML Heading do Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e gerar documentos HTML separados com base no título.

## Passo 1: Carregando o documento

Para começar, especifique o diretório do seu documento e carregue-o em um objeto Document. Veja como:

```csharp
//Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Passo 2: Dividir o documento por Título em formato HTML

Agora definiremos opções de salvamento para dividir o documento em partes menores com base no título no formato HTML. Veja como:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Divida o documento em partes menores, neste caso separando-o por título.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Exemplo de código-fonte para By Headings HTML usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso By HTML Heading do Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Divida um documento em partes menores, neste caso dividida por título.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Com este código, você poderá dividir um documento do Word em partes menores usando Aspose.Words for .NET, com base em títulos. Você pode então gerar documentos HTML separados para cada parte.

## Conclusão

 Neste tutorial, aprendemos como dividir um documento do Word em partes menores usando o recurso By HTML Heading do Aspose.Words for .NET. Ao especificar o`DocumentSplitCriteria` como`HeadingParagraph` no`HtmlSaveOptions`, conseguimos gerar documentos HTML separados com base nos títulos presentes no documento original.

Dividir um documento por títulos pode ser útil para organizar e gerenciar conteúdo, especialmente em documentos grandes com múltiplas seções. Aspose.Words for .NET fornece uma solução confiável e eficiente para lidar com a divisão de documentos e gerar saída em vários formatos.

Sinta-se à vontade para explorar recursos e opções adicionais fornecidos pelo Aspose.Words for .NET para aprimorar ainda mais seus recursos de processamento de documentos e agilizar seu fluxo de trabalho.

### Perguntas frequentes

#### Como posso dividir um documento do Word em partes menores com base em títulos usando Aspose.Words for .NET?

 Para dividir um documento do Word com base em títulos, você pode usar o recurso Por título HTML do Aspose.Words for .NET. Siga o código-fonte fornecido e defina o`DocumentSplitCriteria` para`HeadingParagraph` no`HtmlSaveOptions` objeto. Isso dividirá o documento em partes menores em cada título.

#### Em quais formatos posso dividir o documento do Word?

 O código-fonte fornecido demonstra a divisão do documento do Word em partes menores no formato HTML. No entanto, Aspose.Words for .NET oferece suporte a vários formatos de saída, incluindo DOCX, PDF, EPUB e muito mais. Você pode modificar o código e especificar o formato de saída desejado no campo`HtmlSaveOptions` objeto em conformidade.

#### Posso escolher um critério diferente para dividir o documento?

Sim, você pode escolher critérios diferentes para dividir o documento com base em suas necessidades. Aspose.Words for .NET oferece várias opções de critérios, como`HeadingParagraph`, `Page`, `Section` , e mais. Modifique o`DocumentSplitCriteria` propriedade no`HtmlSaveOptions` objeto para selecionar os critérios apropriados para divisão.

#### Como posso personalizar o HTML de saída para as partes divididas?

 Aspose.Words for .NET permite que você personalize o HTML de saída para as partes divididas, especificando opções adicionais no`HtmlSaveOptions` objeto. Você pode controlar vários aspectos, como estilos CSS, imagens, fontes e muito mais. Consulte a documentação do Aspose.Words para obter mais detalhes sobre como personalizar a saída HTML.

#### Posso dividir o documento com base em vários critérios?

 Sim, você pode dividir o documento com base em vários critérios, combinando as opções de critérios de acordo. Por exemplo, você pode dividir o documento por título e página, definindo a opção`DocumentSplitCriteria`propriedade para`HeadingParagraph | Page`. Isso dividirá o documento em cada título e em cada página, criando partes menores com base em ambos os critérios.