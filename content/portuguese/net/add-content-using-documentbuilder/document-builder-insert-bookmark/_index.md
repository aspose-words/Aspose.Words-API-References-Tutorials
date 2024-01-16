---
title: Document Builder Inserir marcador em documento do Word
linktitle: Document Builder Inserir marcador em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir marcadores em documentos do Word usando DocumentBuilder no Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---
Neste exemplo abrangente, você aprenderá como inserir marcadores em um documento do Word usando a classe DocumentBuilder em Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você será capaz de criar e gerenciar marcadores em seus documentos.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: Crie um novo documento e DocumentBuilder
Para começar, crie um novo documento usando a classe Document e inicialize um objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: insira um marcador
seguir, use os métodos StartBookmark e EndBookmark da classe DocumentBuilder para inserir um marcador no documento. Forneça um nome exclusivo para o marcador como parâmetro:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Etapa 3: salve o documento
Após inserir o marcador, salve o documento em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Exemplo de código-fonte para DocumentBuilder Inserir marcador usando Aspose.Words para .NET
Aqui está o código-fonte completo para inserir um marcador usando a classe DocumentBuilder em Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como inserir marcadores em um documento do Word usando a classe DocumentBuilder em Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode criar e gerenciar marcadores em seus documentos.

Os marcadores são úteis para vários cenários, como navegar em documentos grandes, fazer referência a seções específicas ou manipular programaticamente o conteúdo em áreas marcadas.

Lembre-se de ajustar o código de acordo com seus requisitos específicos e aprimorá-lo com funcionalidades adicionais conforme necessário.

### Perguntas frequentes

#### P: Posso ter vários marcadores em um único documento do Word?

R: Absolutamente! Você pode inserir quantos marcadores forem necessários em um documento do Word usando Aspose.Words for .NET. Apenas certifique-se de fornecer nomes exclusivos para cada marcador para evitar conflitos.

#### P: Posso modificar o conteúdo de um marcador depois de ele ser inserido?

R: Sim, você pode modificar facilmente o conteúdo de um marcador após inseri-lo. Basta usar o DocumentBuilder para navegar até o marcador pelo nome e manipular o conteúdo conforme desejado.

#### P: Os marcadores podem ser usados para extrair programaticamente seções específicas de um documento?

R: Certamente! Os marcadores são valiosos para extrair programaticamente seções específicas de um documento. Ao usar o nome do marcador, você pode identificar e extrair facilmente o conteúdo dessa área marcada.

#### P: É possível adicionar marcadores a documentos do Word existentes usando Aspose.Words for .NET?

R: Absolutamente! Você pode adicionar marcadores a documentos do Word novos e existentes usando Aspose.Words for .NET. Basta abrir o documento existente, inserir o marcador conforme demonstrado neste tutorial e salvar as alterações.

#### P: Posso navegar até uma seção marcada como favorita no documento de maneira programática?

R: Sim, você pode navegar programaticamente para uma seção específica marcada como favorita no documento. Usando o DocumentBuilder, você pode localizar o marcador pelo nome e executar diversas ações, como adicionar novo conteúdo ou aplicar formatação.