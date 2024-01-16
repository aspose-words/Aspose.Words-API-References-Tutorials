---
title: Adicionar marcas Bidi em documento do Word
linktitle: Adicionar marcas Bidi em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda a adicionar marcas Bidi a um documento do Word usando Aspose.Words for .NET e crie documentos multilíngues profissionais.
type: docs
weight: 10
url: /pt/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e manipular documentos do Word em um aplicativo C#. Entre os recursos oferecidos pelo Aspose.Words está a capacidade de adicionar marcas Bidi (bidirecional) a um documento. Neste guia, orientaremos você sobre como usar o código-fonte C# do Aspose.Words for .NET para adicionar marcas Bidi a um documento.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca popular que torna o processamento de palavras com documentos do Word fácil e eficiente. Oferece uma ampla gama de recursos para criação, edição e manipulação de documentos Word, incluindo adição de marcas Bidi.

## Criando o documento e adicionando conteúdo

A primeira etapa é criar um novo documento e adicionar conteúdo a ele. Use a classe Document para criar uma nova instância de documento. Em seguida, use a classe DocumentBuilder para adicionar texto ao documento. Aqui está um exemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

Neste exemplo, criamos um novo documento e usamos o DocumentBuilder para adicionar texto. Adicionamos três linhas de texto: uma em inglês, uma em hebraico e uma em árabe para demonstrar a adição de conteúdo em diferentes idiomas.

## Adicionadas marcas Bidi

Depois que o conteúdo for adicionado, podemos adicionar marcas Bidi ao documento. Para isso, utilizamos a classe TxtSaveOptions e configuramos a propriedade AddBidiMarks como true. Veja como:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Neste exemplo, criamos uma instância de TxtSaveOptions e definimos a propriedade AddBidiMarks como true. A seguir, usamos o método Save da classe Document para salvar o documento com marcas Bidi.

### Exemplo de código-fonte para a funcionalidade "Adicionar marcas Bidi" com Aspose.Words for .NET

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e adicione conteúdo
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Adicionar marcas Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Conclusão

Neste guia, explicamos como usar Aspose.Words for .NET para adicionar marcas Bidi a um documento do Word usando o código-fonte C# fornecido. Seguindo as etapas fornecidas, você pode adicionar facilmente marcas Bidi aos seus documentos do Word em seu aplicativo C#. Aspose.Words oferece enorme flexibilidade e poder para processamento de palavras com formatação de texto e gerenciamento de idioma, permitindo criar documentos multilíngues profissionalmente.

### perguntas frequentes

#### P: O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e manipular documentos Word em um aplicativo C#. Ele oferece muitos recursos para processamento de palavras com documentos do Word, incluindo a adição de marcas Bidi (bidirecionais).

#### P: Quais recursos o Aspose.Words for .NET oferece?
Aspose.Words for .NET oferece uma ampla gama de recursos para criar, editar e manipular documentos Word. Alguns desses recursos incluem criação de documentos, adição de conteúdo, formatação de texto, gerenciamento de tabelas, mesclagem e divisão de documentos, conversão de documentos e muito mais.

#### P: Como posso adicionar marcas Bidi a um documento do Word usando Aspose.Words for .NET?
Você pode adicionar marcas Bidi a um documento do Word seguindo estas etapas:

 Crie um novo documento usando o`Document` aula.

 Use o`DocumentBuilder` classe para adicionar conteúdo ao documento.

 Depois de adicionar o conteúdo, use o`TxtSaveOptions` classe e definir o`AddBidiMarks`propriedade para`true`.

 Salve o documento com marcas Bidi usando o`Save` método do`Document` aula.

#### P: O Aspose.Words oferece suporte a vários idiomas para adicionar marcas Bidi?
Sim, Aspose.Words oferece suporte a vários idiomas para adicionar marcas Bidi. Você pode adicionar marcas Bidi ao texto em diferentes idiomas, como inglês, hebraico e árabe, usando Aspose.Words for .NET.

#### P: Existem opções adicionais para salvar o documento com marcas Bidi?
 Sim, você pode especificar outras opções ao salvar o documento com marcas Bidi usando o`TxtSaveOptions` aula. Por exemplo, você pode definir o formato de salvamento do documento, opções de codificação, etc.