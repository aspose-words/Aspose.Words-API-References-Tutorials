---
title: Obtenha detalhes do grupo de revisão
linktitle: Obtenha detalhes do grupo de revisão
second_title: API de processamento de documentos Aspose.Words
description: Obtenha detalhes do grupo de revisão em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/get-revision-group-details/
---

Neste guia passo a passo, mostraremos como obter os detalhes de um grupo de revisões em um documento do Word usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Carregando o documento

O primeiro passo é fazer o upload do documento contendo as revisões.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Etapa 2: navegar pelas revisões

A seguir, percorreremos as revisões presentes no documento e exibiremos seus detalhes, como tipo, autor, data e texto revisado.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Exemplo de código-fonte para obter detalhes do grupo de revisão usando Aspose.Words for .NET

Aqui está o código-fonte completo para obter os detalhes de um grupo de revisões em um documento usando Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Conclusão

Neste tutorial, aprendemos como obter os detalhes de um grupo de revisões em um documento Word usando Aspose.Words for .NET. Usando um loop e as propriedades apropriadas, conseguimos exibir detalhes como tipo de revisão, autor, data e texto revisado. Aspose.Words for .NET oferece muitos recursos poderosos para manipular documentos do Word, incluindo gerenciamento de revisões. Agora você pode usar esse conhecimento para obter detalhes do grupo de revisão em seus próprios documentos do Word usando Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como carrego um documento com revisões no Aspose.Words for .NET?

 R: Use o`Document`classe de Aspose.Words for .NET para carregar um documento de um arquivo contendo revisões. Você pode especificar o caminho completo do documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Como obtenho os detalhes de um grupo de revisão no Aspose.Words for .NET?

 R: Percorra as revisões do documento usando um loop e acesse as propriedades de cada revisão para obter os detalhes desejados. Você pode usar o`RevisionType`, `Author`, `DateTime` e`ParentNode` propriedades para obter o tipo de revisão, autor, data e texto revisado respectivamente.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### P: Como verificar se uma revisão pertence a um grupo no Aspose.Words for .NET?

 R: Use o`Group` propriedade do`Revision` objeto para verificar se uma revisão pertence a um grupo. Se o`Group` propriedade é`null`significa que a revisão não pertence a nenhum grupo.

```csharp
if (revision.Group != null)
{
      // A revisão pertence a um grupo
}
else
{
      // A revisão não pertence a nenhum grupo
}
```