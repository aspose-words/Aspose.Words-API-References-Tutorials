---
title: Insira objeto Ole como ícone usando Stream
linktitle: Insira objeto Ole como ícone usando Stream
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um objeto OLE como um ícone usando um stream com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo que ilustra como inserir um objeto OLE como um ícone usando um fluxo com Aspose.Words for .NET.

## Passo 1: Importe as referências necessárias
Antes de começar, certifique-se de ter importado as referências necessárias para usar Aspose.Words for .NET em seu projeto. Isso inclui importar a biblioteca Aspose.Words e adicionar os namespaces necessários ao seu arquivo de origem.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Etapa 2: Crie um novo documento e gerador de documentos
 Nesta etapa, criaremos um novo documento usando o`Document` classe e um construtor de documentos usando o`DocumentBuilder` aula.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir um objeto OLE como um ícone de um fluxo
 Use o Construtor de Documentos`InsertOleObjectAsIcon` método para inserir um objeto OLE como um ícone de um fluxo no documento. Especifique o fluxo de dados, o tipo de objeto, o caminho do ícone e o nome do objeto incorporado.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Etapa 4: salve o documento
 Utilize o documento`Save` método para salvar o documento em um arquivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Exemplo de código-fonte para inserir um objeto OLE como um ícone usando um fluxo com Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Este é um exemplo de código completo para inserir um objeto OLE como um ícone usando um fluxo com Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga os passos descritos anteriormente para integrar este código ao seu projeto.

## Conclusão

guia passo a passo acima explica como inserir um objeto OLE como um ícone em um documento do Word usando um fluxo com Aspose.Words for .NET. Seguindo os passos descritos, você poderá integrar esta funcionalidade ao seu projeto. Certifique-se de importar as referências necessárias, criar um novo documento e gerador de documentos, inserir o objeto OLE como um ícone do fluxo e salvar o documento. Use o código de exemplo fornecido como ponto de partida e personalize-o de acordo com suas necessidades.

### Perguntas frequentes

#### P. Como importar as referências necessárias para usar o Aspose.Words for .NET?

A. Para importar as referências necessárias, você deve seguir estes passos:

 Adicione o seguinte`using` instruções no topo do seu arquivo de origem:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Certifique-se de ter adicionado a biblioteca Aspose.Words ao seu projeto.

#### P. Como criar um novo documento e construtor de documentos usando Aspose.Words for .NET?

A. Para criar um novo documento e gerador de documentos, você pode seguir estas etapas:

 Use o`Document` classe para criar um novo documento:

```csharp
Document doc = new Document();
```
 Use o`DocumentBuilder`classe para criar um construtor de documentos associado ao documento criado anteriormente:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P. Como inserir um objeto OLE como um ícone de um fluxo usando Aspose.Words for .NET?

A. Para inserir um objeto OLE como um ícone de um fluxo, siga estas etapas:

 Use o`InsertOleObjectAsIcon` método do gerador de documento para inserir o objeto OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### P. Como salvar o documento em um arquivo?

A.  Para salvar o documento em um arquivo, você pode usar o`Save` método do documento especificando o caminho de destino:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### P. Como incorporar o código para inserir um objeto OLE como um ícone de um fluxo em meu projeto?

A. Para incorporar o código para inserir um objeto OLE como um ícone de um fluxo em seu projeto, siga estas etapas:
-  Importe as referências necessárias adicionando o apropriado`using` declarações.
-  Crie um novo documento e um construtor de documentos usando o`Document`e`DocumentBuilder` Aulas.
- Use o código para inserir o objeto OLE como um ícone de um fluxo.
-  Salve o documento usando o`Save` método com o caminho de destino apropriado.

Seguindo essas etapas, você poderá inserir com êxito um objeto OLE como um ícone de um fluxo usando Aspose.Words for .NET. Certifique-se de seguir as instruções e importar as referências necessárias para obter os resultados desejados.