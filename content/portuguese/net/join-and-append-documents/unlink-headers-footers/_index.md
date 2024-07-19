---
title: Desvincular cabeçalhos e rodapés
linktitle: Desvincular cabeçalhos e rodapés
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como desvincular cabeçalhos e rodapés em documentos do Word usando Aspose.Words for .NET. Siga nosso guia passo a passo detalhado para dominar a manipulação de documentos.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/unlink-headers-footers/
---
## Introdução

No mundo do processamento de documentos, manter cabeçalhos e rodapés consistentes às vezes pode ser um desafio. Esteja você mesclando documentos ou apenas procurando cabeçalhos e rodapés diferentes para seções diferentes, saber como desvinculá-los é essencial. Hoje, vamos nos aprofundar em como você pode conseguir isso usando Aspose.Words for .NET. Iremos detalhar passo a passo para que você possa acompanhar facilmente. Pronto para dominar a manipulação de documentos? Vamos começar!

## Pré-requisitos

Antes de mergulharmos no âmago da questão, há algumas coisas que você precisará:

-  Biblioteca Aspose.Words for .NET: você pode baixá-lo do[Página de lançamentos do Aspose](https://releases.aspose.com/words/net/).
- .NET Framework: certifique-se de ter um .NET framework compatível instalado.
- IDE: Visual Studio ou qualquer outro ambiente de desenvolvimento integrado compatível com .NET.
- Compreensão básica de C#: você precisará de uma compreensão básica da linguagem de programação C#.

## Importar namespaces

Para começar, certifique-se de importar os namespaces necessários em seu projeto. Isso permitirá que você acesse a biblioteca Aspose.Words e seus recursos.

```csharp
using Aspose.Words;
```

Vamos dividir o processo em etapas gerenciáveis para ajudá-lo a desvincular cabeçalhos e rodapés em seus documentos do Word.

## Etapa 1: configure seu projeto

Primeiro, você precisará configurar o ambiente do seu projeto. Abra seu IDE e crie um novo projeto .NET. Adicione uma referência à biblioteca Aspose.Words que você baixou anteriormente.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o documento de origem

Em seguida, você precisa carregar o documento de origem que deseja modificar. Este documento terá seus cabeçalhos e rodapés desvinculados.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Etapa 3: carregue o documento de destino

Agora, carregue o documento de destino onde você anexará o documento de origem após desvincular seus cabeçalhos e rodapés.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Etapa 4: desvincular cabeçalhos e rodapés

 Esta etapa é crucial. Para desvincular os cabeçalhos e rodapés do documento de origem daqueles do documento de destino, você usará o comando`LinkToPrevious` método. Este método garante que os cabeçalhos e rodapés não sejam transferidos para o documento anexado.

```csharp
// Desvincule os cabeçalhos e rodapés do documento de origem para impedir isso
//de continuar os cabeçalhos e rodapés do documento de destino.
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Etapa 5: anexar o documento de origem

 Depois de desvincular os cabeçalhos e rodapés, você poderá anexar o documento de origem ao documento de destino. Use o`AppendDocument` método e defina o modo de formato de importação para`KeepSourceFormatting` para manter a formatação original do documento de origem.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 6: salve o documento final

Finalmente, salve o documento recém-criado. Este documento terá o conteúdo do documento de origem anexado ao documento de destino, com os cabeçalhos e rodapés desvinculados.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

## Conclusão

E aí está! Seguindo essas etapas, você desvinculou com êxito os cabeçalhos e rodapés do documento de origem e anexou-os ao documento de destino usando Aspose.Words for .NET. Essa técnica pode ser particularmente útil quando você trabalha com documentos complexos que exigem cabeçalhos e rodapés diferentes para seções diferentes. Boa codificação!

## Perguntas frequentes

### O que é Aspose.Words para .NET?  
Aspose.Words for .NET é uma biblioteca poderosa para trabalhar com documentos do Word em aplicativos .NET. Ele permite que os desenvolvedores criem, modifiquem, convertam e imprimam documentos programaticamente.

### Posso desvincular cabeçalhos e rodapés apenas de seções específicas?  
 Sim, você pode desvincular cabeçalhos e rodapés de seções específicas acessando o`HeadersFooters` propriedade da seção desejada e usando o`LinkToPrevious` método.

### É possível manter a formatação original do documento de origem?  
 Sim, ao anexar o documento de origem, use o`ImportFormatMode.KeepSourceFormatting` opção de manter a formatação original.

### Posso usar Aspose.Words for .NET com outras linguagens .NET além de C#?  
Absolutamente! Aspose.Words for .NET pode ser usado com qualquer linguagem .NET, incluindo VB.NET e F#.

### Onde posso encontrar mais documentação e suporte para Aspose.Words for .NET?  
 Você pode encontrar documentação abrangente sobre o[Página de documentação do Aspose.Words para .NET](https://reference.aspose.com/words/net/) e o suporte está disponível no[Aspor fórum](https://forum.aspose.com/c/words/8).
