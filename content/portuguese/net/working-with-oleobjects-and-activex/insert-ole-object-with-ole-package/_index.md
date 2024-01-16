---
title: Insira objeto Ole no Word com pacote Ole
linktitle: Insira objeto Ole no Word com pacote Ole
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um objeto OLE com um pacote OLE em um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo que ilustra como inserir um objeto OLE no Word com um pacote OLE usando Aspose.Words for .NET.

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

## Etapa 3: inserir um objeto OLE com um pacote OLE
 Use o Gerador de Documentos`InsertOleObject` método para inserir um objeto OLE com um pacote OLE no documento. Especifique o fluxo de dados, tipo de objeto, opções de exibição e outras configurações necessárias.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Etapa 4: salve o documento
 Utilize o documento`Save` método para salvar o documento em um arquivo.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Exemplo de código-fonte para inserir um objeto OLE com um pacote OLE com Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Este é um exemplo de código completo para inserir um objeto OLE com um pacote OLE com Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga os passos descritos anteriormente para integrar este código ao seu projeto.

## Conclusão

Concluindo, seguimos um guia passo a passo para inserir um objeto OLE em um documento do Word com um pacote OLE usando Aspose.Words for .NET.

Seguindo essas etapas, você poderá inserir objetos OLE com pacotes OLE em seus documentos do Word usando Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga as instruções cuidadosamente para obter os resultados desejados.

### Perguntas frequentes para inserir objeto ole no word com pacote ole

#### P: Quais credenciais preciso importar para usar o Aspose.Words for .NET?

R: Para usar Aspose.Words for .NET, você precisa importar as seguintes referências:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### P: Como criar um novo documento e um gerador de documentos?

 R: Você pode criar um novo documento usando o`Document` classe e um construtor de documentos usando o`DocumentBuilder` classe, conforme mostrado abaixo:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### P: Como inserir um objeto OLE com um pacote OLE no documento?

 R: Use o`InsertOleObject`método do construtor de documentos (`DocumentBuilder`) para inserir um objeto OLE com um pacote OLE no documento. Especifique o fluxo de dados, tipo de objeto, opções de exibição e outras configurações necessárias. Aqui está um exemplo :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### P: Como salvar o documento?

 R: Use o documento`Save` método para salvar o documento em um arquivo. Aqui está um exemplo :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### P: Você pode fornecer um exemplo completo de inserção de um objeto OLE com um pacote OLE com Aspose.Words for .NET?

R: Aqui está um exemplo de código completo para inserir um objeto OLE com um pacote OLE usando Aspose.Words for .NET. Certifique-se de importar as referências necessárias e siga os passos descritos anteriormente para integrar este código ao seu projeto:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Isso conclui nosso tutorial sobre como inserir um objeto OLE com um pacote OLE em um documento do Word usando Aspose.Words for .NET. Fique à vontade para importar as referências necessárias e seguir os passos descritos para integrar este código ao seu projeto. Se você tiver mais alguma dúvida, não hesite em nos contatar.