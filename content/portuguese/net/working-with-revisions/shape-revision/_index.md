---
title: Revisão de forma
linktitle: Revisão de forma
second_title: API de processamento de documentos Aspose.Words
description: Revise formas em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-revisions/shape-revision/
---

Neste guia passo a passo, orientaremos você sobre como fazer revisões de formas em um documento do Word usando Aspose.Words for .NET. Forneceremos o código-fonte completo e mostraremos como formatar a saída do markdown.

## Passo 1: Criando o documento e adicionando formas

A primeira etapa é criar um novo documento e adicionar formas.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Etapa 2: acompanhar as revisões e adicionar outra forma

Ativaremos o rastreamento de revisão e adicionaremos outra forma.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Etapa 3: obtenha a coleção de formas e verifique as revisões.

Obteremos a coleção de formas do documento e verificaremos as revisões associadas a cada forma.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Etapa 4: verificar as revisões de movimentação de forma

Carregaremos um documento existente contendo revisões de deslocamento de forma e verificaremos as revisões associadas.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Exemplo de código-fonte para revisão de forma usando Aspose.Words for .NET

Aqui está o código-fonte completo para fazer revisões de formas em um documento usando Aspose.Words for .NET:

```csharp
Document doc = new Document();

//Insira uma forma embutida sem rastrear revisões.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Comece a rastrear as revisões e insira outra forma.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Obtenha a coleção de formas do documento que inclui apenas as duas formas que adicionamos.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Remova a primeira forma.
shapes[0].Remove();

// Como removemos essa forma enquanto as alterações estavam sendo rastreadas, a forma conta como uma revisão de exclusão.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// E inserimos outra forma enquanto rastreamos as alterações, para que essa forma conte como uma revisão de inserção.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// O documento tem uma forma que foi movida, mas as revisões de movimentação de forma terão duas instâncias dessa forma.
// Uma será a forma no seu destino de chegada e a outra será a forma no seu local original.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Este é o movimento para a revisão, também a forma no seu destino de chegada.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Esta é a mudança da revisão, que é a forma em seu local original.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Conclusão

Neste tutorial, aprendemos como fazer revisões de formas em um documento Word usando Aspose.Words for .NET. Seguindo as etapas de criação do documento, habilitando o rastreamento de revisões, verificando as revisões associadas a cada forma e verificando as revisões para mover as formas, conseguimos gerenciar as revisões com sucesso. Aspose.Words for .NET oferece uma API poderosa para processamento de palavras com revisões e formulários em documentos do Word.

### Perguntas frequentes

#### P: Como posso criar um novo documento e adicionar formas no Aspose.Words for .NET?

R: Para criar um novo documento e adicionar formas no Aspose.Words for .NET, você pode usar o código a seguir. Aqui adicionamos duas formas, um cubo e um sol, à primeira seção do documento:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### P: Como habilito o rastreamento de revisão no Aspose.Words for .NET?

 R: Para habilitar o rastreamento de revisão no Aspose.Words for .NET, você pode usar o`StartTrackRevisions` método do`Document` objeto. Este método leva como parâmetro o nome do autor das revisões:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### P: Como posso verificar as revisões associadas a cada forma em um documento Aspose.Words for .NET?

R: Para verificar as revisões associadas a cada forma em um documento Aspose.Words for .NET, você pode obter a coleção de formas do documento usando o`GetChildNodes` método com o`NodeType.Shape` tipo de nó. Então você pode acessar cada forma`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , e`IsMoveToRevision` propriedades para determinar que tipo de revisão está associada à forma:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### P: Como posso verificar revisões de deslocamento de formas em um documento Aspose.Words for .NET?

 R: Para verificar revisões de deslocamento de forma em um documento Aspose.Words para .NET, você pode carregar um documento existente que contenha revisões de deslocamento de forma. Então você pode acessar cada forma`IsMoveFromRevision` e`IsMoveToRevision` propriedades para determinar se ele está sendo movido e, em caso afirmativo, de onde e para onde:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```