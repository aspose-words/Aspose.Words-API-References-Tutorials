---
title: Insira objeto Ole em documento do Word como ícone
linktitle: Insira objeto Ole em documento do Word como ícone
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um objeto OLE em um documento do Word como ícone com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo que ilustra como inserir um objeto OLE em um documento do Word como um ícone usando Aspose.Words for .NET.

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

## Etapa 3: insira um objeto OLE como um ícone
 Use o Construtor de Documentos`InsertOleObjectAsIcon` método para inserir um objeto OLE como um ícone no documento. Especifique o caminho do arquivo OLE, o sinalizador de exibição, o caminho do ícone e o nome do objeto incorporado.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Etapa 4: salve o documento
 Utilize o documento`Save` método para salvar o documento em um arquivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Exemplo de código-fonte para inserir um objeto OLE como um ícone com Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Este é um exemplo de código completo para inserir um objeto OLE como um ícone com Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga os passos descritos anteriormente para integrar este código ao seu projeto.

## Conclusão

Concluindo, exploramos um guia passo a passo para inserir um objeto OLE como um ícone em um documento do Word usando Aspose.Words for .NET.

Seguindo essas etapas, você poderá inserir com êxito um objeto OLE como um ícone em seus documentos do Word usando Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga as instruções cuidadosamente para obter os resultados desejados.

### Perguntas frequentes para inserir objeto ole em documento do Word como ícone

#### P. Quais referências são necessárias para inserir um objeto OLE como um ícone em um documento do Word usando Aspose.Words for .NET?

R: Você precisa importar as seguintes referências para o seu projeto para usar o Aspose.Words for .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### P. Como criar um novo documento e gerador de documentos no Aspose.Words for .NET?

 R: Você pode criar um novo documento usando o`Document` classe e um construtor de documentos usando o`DocumentBuilder`aula. Aqui está um exemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P. Como inserir um objeto OLE como ícone no documento?

 R: Use o Document Builder`InsertOleObjectAsIcon` método para inserir um objeto OLE como um ícone. Especifique o caminho do arquivo OLE, o sinalizador de exibição, o caminho do ícone e o nome do objeto incorporado. Aqui está um exemplo :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### P. Como salvar o documento com o objeto OLE inserido como ícone?

 R: Use o documento`Save`método para salvar o documento em um arquivo. Aqui está um exemplo :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```