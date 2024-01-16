---
title: Inserir objeto Ole em documento do Word
linktitle: Inserir objeto Ole em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um objeto OLE em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo que ilustra como inserir um objeto OLE em um documento do Word usando Aspose.Words for .NET.

## Passo 1: Importe as referências necessárias
Antes de começar, certifique-se de ter importado as referências necessárias para usar Aspose.Words for .NET em seu projeto. Isso inclui importar a biblioteca Aspose.Words e adicionar os namespaces necessários ao seu arquivo de origem.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Etapa 2: Crie um novo documento e gerador de documentos
 Nesta etapa, criaremos um novo documento usando o`Document` classe e um construtor de documentos usando o`DocumentBuilder` aula.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir um objeto OLE
 Use o Construtor de Documentos`InsertOleObject` método para inserir um objeto OLE no documento. Especifique o URL do objeto OLE, o tipo de objeto, as opções de exibição e outras configurações necessárias.

```csharp
builder. InsertOleObject("http://www.aspose.com", "arquivohtml", verdadeiro, verdadeiro, nulo);
```

## Etapa 4: salve o documento
 Utilize o documento`Save` método para salvar o documento em um arquivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Exemplo de código-fonte para inserir um objeto OLE com Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "arquivohtml", verdadeiro, verdadeiro, nulo);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Este é um exemplo de código completo para inserir um objeto OLE com Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga os passos descritos anteriormente para integrar este código ao seu projeto.

## Conclusão

Concluindo, inserir objetos OLE em um documento do Word é um recurso poderoso oferecido pelo Aspose.Words for .NET. Usando esta biblioteca, você pode incorporar facilmente objetos OLE, como arquivos HTML, planilhas do Excel, apresentações do PowerPoint, etc., em seus documentos do Word.

Neste artigo, percorremos um guia passo a passo para explicar o código-fonte em C# que ilustra como inserir um objeto OLE em um documento do Word. Abordamos as referências necessárias, a criação de um novo documento e um gerador de documentos, e as etapas para inserir um objeto OLE e salvar o documento.

### Perguntas frequentes sobre como inserir um objeto OLE em um documento do Word

#### P: Quais credenciais preciso importar para usar o Aspose.Words for .NET?

R: Para usar Aspose.Words for .NET, você precisa importar as seguintes referências:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### P: Como criar um novo documento e um gerador de documentos?

 R: Você pode criar um novo documento usando o`Document` classe e um construtor de documentos usando o`DocumentBuilder` classe, conforme mostrado abaixo:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P: Como inserir um objeto OLE no documento?

 R: Use o`InsertOleObject`método do construtor de documentos (`DocumentBuilder`) para inserir um objeto OLE no documento. Especifique o URL do objeto OLE, o tipo de objeto, as opções de exibição e outras configurações necessárias. Aqui está um exemplo :

```csharp
builder. InsertOleObject("http://www.aspose.com", "arquivohtml", verdadeiro, verdadeiro, nulo);
```

#### P: Como salvar o documento?

 R: Use o documento`Save` método para salvar o documento em um arquivo. Aqui está um exemplo :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### P: Você pode fornecer um exemplo completo de inserção de um objeto OLE com Aspose.Words for .NET?

R: Aqui está um exemplo de código completo para inserir um objeto OLE com Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga os passos descritos anteriormente para integrar este código ao seu projeto:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "arquivohtml", verdadeiro, verdadeiro, nulo);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
