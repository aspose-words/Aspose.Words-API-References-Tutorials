---
title: Construir tabela em documento Word
linktitle: Construir tabela em documento Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como construir uma tabela em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/build-table/
---
Neste tutorial passo a passo, você aprenderá como construir uma tabela em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você será capaz de criar uma tabela com formatação e conteúdo personalizados usando a classe DocumentBuilder.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: crie um novo documento
Para começar, crie um novo documento usando a classe Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inicie a mesa
A seguir, use o método StartTable da classe DocumentBuilder para começar a construir a tabela:

```csharp
Table table = builder.StartTable();
```

## Etapa 3: inserir células e adicionar conteúdo
Agora você pode inserir células na tabela e adicionar conteúdo a elas usando os métodos InsertCell e Write da classe DocumentBuilder. Personalize a formatação da célula conforme necessário:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Etapa 4: encerrar a linha
Após adicionar conteúdo às células da primeira linha, use o método EndRow da classe DocumentBuilder para finalizar a linha:

```csharp
builder.EndRow();
```

## Etapa 5: personalizar a formatação de linha
Você pode personalizar a formatação de uma linha definindo propriedades dos objetos RowFormat e CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Etapa 6: encerrar a mesa
Para completar a tabela, utilize o método EndTable da classe DocumentBuilder:

```csharp
builder.EndTable();
```

### Exemplo de código-fonte para construir uma tabela usando Aspose.Words for .NET
Aqui está o código-fonte completo para construir uma tabela usando Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como construir uma tabela em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode criar tabelas com formatação personalizada.

### Perguntas frequentes para construir tabela em documento do Word

#### P: O que é Aspose.Words para .NET?

R: Aspose.Words for .NET é uma poderosa biblioteca de processamento de documentos que permite aos desenvolvedores criar, ler, editar e converter documentos do Microsoft Word programaticamente em aplicativos .NET. Ele oferece uma ampla gama de recursos para trabalhar com documentos do Word, como manipulação de texto, criação de tabelas, proteção de documentos, formatação e muito mais.

#### P: Como posso construir uma tabela em um documento do Word usando Aspose.Words for .NET?

R: Para construir uma tabela em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto.
2.  Use o`StartTable` método do`DocumentBuilder`classe para começar a construir a mesa.
3.  Insira células na tabela e adicione conteúdo usando o`InsertCell` e`Write` métodos do`DocumentBuilder` aula.
4.  Termine a linha usando o`EndRow` método do`DocumentBuilder` aula.
5.  Personalize a formatação da linha definindo as propriedades do`RowFormat` e`CellFormat` objetos.
6.  Termine a tabela usando o`EndTable` método do`DocumentBuilder` aula.
7. Salve o documento.

#### P: Como posso personalizar a formatação da tabela e de suas células?

 R: Você pode personalizar a formatação da tabela e de suas células definindo várias propriedades do`RowFormat` e`CellFormat` objetos. Por exemplo, você pode ajustar o alinhamento das células, a orientação do texto vertical e horizontal, a altura das células, a altura das linhas e muito mais. Usando essas propriedades, você pode obter a aparência desejada para a tabela e seu conteúdo.

#### P: Posso criar tabelas complexas com células mescladas e outros recursos avançados?

 R: Sim, o Aspose.Words for .NET fornece recursos avançados para construir tabelas complexas, incluindo suporte para células mescladas, tabelas aninhadas e layouts de tabelas complexos. Você pode usar o`MergeCells` método para mesclar células,`StartTable`método para criar tabelas aninhadas e outros métodos para obter a estrutura de tabela desejada.

#### P: O Aspose.Words for .NET é compatível com diferentes formatos de documentos do Word?

R: Sim, Aspose.Words for .NET é compatível com vários formatos de documentos do Word, incluindo DOC, DOCX, RTF e muito mais. Ele suporta formatos legados (DOC) e formatos modernos baseados em XML (DOCX) e permite trabalhar com documentos em diferentes formatos sem problemas.

#### P: Onde posso encontrar mais informações e documentação do Aspose.Words for .NET?

 R: Você pode encontrar documentação abrangente e exemplos de código em[Referências de API](https://reference.aspose.com/words/net/). A documentação fornecerá informações detalhadas sobre os recursos da biblioteca e como usá-los em seus aplicativos .NET.