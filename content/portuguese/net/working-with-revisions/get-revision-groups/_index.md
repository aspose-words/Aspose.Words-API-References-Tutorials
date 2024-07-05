---
title: Obtenha grupos de revisão
linktitle: Obtenha grupos de revisão
second_title: API de processamento de documentos Aspose.Words
description: Obtenha grupos de revisão em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/get-revision-groups/
---

Neste guia passo a passo, mostraremos como obter os grupos de revisão em um documento do Word usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Carregando o documento

primeiro passo é fazer o upload do documento contendo as revisões.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Etapa 2: navegar pelos grupos de revisão

seguir, percorreremos os grupos de revisão presentes no documento e exibiremos seus detalhes, como autor, tipo de revisão e texto revisado.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Exemplo de código-fonte para obter grupos de revisão usando Aspose.Words for .NET

Aqui está o código-fonte completo para obter os grupos de revisão em um documento usando Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Conclusão

Neste tutorial, aprendemos como obter os grupos de revisão em um documento do Word usando Aspose.Words for .NET. Seguimos os passos para carregar o documento e navegar pelos grupos de revisão, exibindo detalhes como autor e tipo de revisão. Agora você pode aplicar esse conhecimento para analisar revisões de seu próprio documento do Word usando Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como fazer upload de um documento no Aspose.Words for .NET?

 R: Use o`Document` classe de Aspose.Words for .NET para carregar um documento de um arquivo. Você pode especificar o caminho completo do documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: Como navegar por grupos de revisão em um documento no Aspose.Words for .NET?

 R: Use o`Groups` propriedade do documento`Revisions`objeto para obter a coleção de grupos de revisão. Você pode então usar um loop para percorrer cada grupo de revisão.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Processe cada grupo de revisão aqui
}
```

#### P: Como conseguir o autor de um grupo de revisão no Aspose.Words for .NET?

 R: Use o`Author` propriedade do`RevisionGroup` objeto para obter o autor do grupo de revisão.

```csharp
string author = group.Author;
```

#### P: Como obter o tipo de revisão de um grupo de revisão no Aspose.Words for .NET?

 R: Use o`RevisionType` propriedade do`RevisionGroup` object para obter o tipo de revisão do grupo.

```csharp
string revisionType = group.RevisionType;
```