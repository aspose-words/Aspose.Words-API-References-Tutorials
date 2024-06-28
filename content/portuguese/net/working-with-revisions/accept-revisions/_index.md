---
title: Aceitar avaliações
linktitle: Aceitar avaliações
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como aceitar revisões em um documento do Word usando Aspose.Words for .NET
type: docs
weight: 10
url: /pt/net/working-with-revisions/accept-revisions/
---

Neste tutorial, orientaremos você na aceitação de revisões em um documento do Word usando o recurso Aceitar revisões do Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e aceitar as alterações no documento.

## Etapa 1: adicionar e editar o conteúdo do documento

Neste exemplo, estamos criando um documento e adicionando conteúdo. Usamos vários parágrafos para ilustrar alterações e revisões. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Adicione texto ao primeiro parágrafo e, em seguida, adicione mais dois parágrafos.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Etapa 2: rastrear comentários e adicionar comentários

Ativamos o rastreamento de revisão e adicionamos uma revisão ao documento. Veja como:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Este parágrafo é uma revisão e terá o sinalizador "IsInsertRevision" correspondente definido.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Etapa 3: exclua um parágrafo e gerencie as revisões

Excluímos um parágrafo e verificamos as revisões salvas. Veja como:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Como estamos acompanhando as revisões, o parágrafo ainda existe no documento, terá o sinalizador "IsDeleteRevision" definido
// e será exibido como uma revisão no Microsoft Word, até aceitarmos ou rejeitarmos todas as revisões.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Etapa 4: aceitar as alterações

Aceitamos todas as alterações no documento. Veja como:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Etapa 5: parar de rastrear avaliações

Pararemos de rastrear revisões para que as alterações no documento não apareçam mais como revisões. Veja como:

```csharp
doc.StopTrackRevisions();
```
## Passo 6: Salvando o documento

 Após inserir o campo do formulário de entrada de texto, salve o documento no local desejado usando o`Save` método. Certifique-se de fornecer o caminho de arquivo apropriado:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Exemplo de código-fonte para aceitar revisões usando Aspose.Words for .NET

Aqui está o código-fonte completo para aceitar alterações em um documento usando Aspose.Words for .NET:


```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Adicione texto ao primeiro parágrafo e, em seguida, adicione mais dois parágrafos.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Temos três parágrafos, nenhum deles registrado como qualquer tipo de revisão
// Se adicionarmos/removermos qualquer conteúdo do documento enquanto rastreamos as revisões,
// eles serão exibidos como tal no documento e poderão ser aceitos/rejeitados.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Este parágrafo é uma revisão e terá o sinalizador "IsInsertRevision" definido.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Obtenha a coleção de parágrafos do documento e remova um parágrafo.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Como estamos rastreando revisões, o parágrafo ainda existe no documento e terá o conjunto "IsDeleteRevision"
// e será exibido como uma revisão no Microsoft Word, até aceitarmos ou rejeitarmos todas as revisões.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// O parágrafo de revisão excluído será removido assim que aceitarmos as alterações.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Interromper o rastreamento de revisões faz com que este texto apareça como texto normal.
// As revisões não são contabilizadas quando o documento é alterado.
doc.StopTrackRevisions();

// Salve o documento.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Conclusão

Neste tutorial, aprendemos como aceitar revisões em um documento do Word usando o recurso Aceitar Revisões do Aspose.Words for .NET. Seguimos as etapas para adicionar e editar o conteúdo do documento, rastrear revisões, excluir um parágrafo revisado, aceitar todas as alterações e parar de rastrear revisões. Agora você pode aplicar esse conhecimento para gerenciar revisões com eficácia em seus próprios documentos do Word usando Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como habilito o rastreamento de revisão no Aspose.Words for .NET?

#### Solução 1:

 R: Para habilitar o rastreamento de revisão no Aspose.Words for .NET, use o`StartTrackRevisions` método do`Document` objeto e especifique o nome do autor e a data de início do rastreamento de revisão.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Solução 2:

 R: Você também pode ativar o rastreamento de revisão usando o`Document` construtor que aceita`trackRevisions` e`author` parâmetros.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### P: Como aceitar todas as alterações em um documento com Aspose.Words for .NET?

 R: Use o`AcceptAllRevisions` método do`Document` opor-se a aceitar todas as alterações feitas no documento.

```csharp
doc.AcceptAllRevisions();
```

#### P: Como salvo um documento modificado com revisões aceitas?

 Use o`Save` método do`Document` objeto para salvar o documento modificado com as revisões aceitas. Certifique-se de fornecer o caminho correto do arquivo.

```csharp
doc.Save("path/to/the/document.docx");
```

#### P: Como faço para parar de rastrear revisões no Aspose.Words for .NET?

 R: Use o`StopTrackRevisions` método do`Document` objeto para interromper as revisões de rastreamento.

```csharp
doc.StopTrackRevisions();
```

#### P: Como excluo um parágrafo revisado em um documento com Aspose.Words for .NET?

 R: Para remover um parágrafo revisado de um documento, você pode usar o`Remove` método da coleção de parágrafos.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```