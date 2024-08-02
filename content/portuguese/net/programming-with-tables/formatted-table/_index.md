---
title: Tabela formatada
linktitle: Tabela formatada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar e formatar tabelas em documentos do Word usando Aspose.Words for .NET com este guia passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/programming-with-tables/formatted-table/
---
## Introdução

Criar e formatar tabelas em documentos do Word programaticamente pode parecer uma tarefa difícil, mas com Aspose.Words for .NET, torna-se simples e gerenciável. Neste tutorial, orientaremos você sobre como criar uma tabela formatada em um documento do Word usando Aspose.Words for .NET. Abordaremos tudo, desde a configuração do seu ambiente até salvar seu documento com uma tabela lindamente formatada.

## Pré-requisitos

Antes de mergulhar no código, vamos ter certeza de que você tem tudo o que precisa:

1. Biblioteca Aspose.Words for .NET: Faça o download em[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: um IDE como o Visual Studio.
3. .NET Framework: certifique-se de ter o .NET Framework instalado em sua máquina.

## Importar namespaces

Antes de escrever o código real, você precisa importar os namespaces necessários:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa definir o caminho onde seu documento será salvo.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde você deseja salvar o documento.

## Etapa 2: inicializar o documento e o DocumentBuilder

Agora inicialize um novo documento e um objeto DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 O`DocumentBuilder` é uma classe auxiliar que simplifica o processo de construção de documentos.

## Etapa 3: inicie a mesa

 A seguir, comece a criar a tabela usando o`StartTable` método.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

É necessário inserir uma célula para iniciar a tabela.

## Etapa 4: aplicar formatação em toda a tabela

Você pode aplicar formatação que afete toda a tabela. Por exemplo, definindo o recuo à esquerda:

```csharp
table.LeftIndent = 20.0;
```

## Etapa 5: formate a linha do cabeçalho

Defina a altura, o alinhamento e outras propriedades da linha do cabeçalho.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

Nesta etapa, destacamos a linha do cabeçalho definindo a cor de fundo, o tamanho da fonte e o alinhamento.

## Etapa 6: inserir células de cabeçalho adicionais

Insira mais células para a linha do cabeçalho:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## Etapa 7: formate as linhas do corpo

Após configurar o cabeçalho, formate o corpo da tabela:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## Etapa 8: inserir linhas do corpo

Insira as linhas do corpo com conteúdo:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

Repita para linhas adicionais:

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## Etapa 9: salve o documento

Finalmente, salve o documento no diretório especificado:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Isso criará e salvará um documento do Word com a tabela formatada.

## Conclusão

E aí está! Seguindo essas etapas, você pode criar uma tabela bem formatada em um documento do Word usando Aspose.Words for .NET. Esta poderosa biblioteca facilita a manipulação programática de documentos do Word, economizando tempo e esforço.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e converter documentos do Word programaticamente.

### Posso usar cores diferentes para linhas diferentes?
Sim, você pode aplicar formatações diferentes, incluindo cores, a linhas ou células diferentes.

### O Aspose.Words para .NET é gratuito?
 Aspose.Words for .NET é uma biblioteca paga, mas você pode obter um[teste grátis](https://releases.aspose.com/).

### Como obtenho suporte para Aspose.Words for .NET?
 Você pode obter suporte do[Aspose fóruns da comunidade](https://forum.aspose.com/c/words/8).

### Posso criar outros tipos de documentos com Aspose.Words for .NET?
Sim, Aspose.Words for .NET oferece suporte a vários formatos de documentos, incluindo PDF, HTML e TXT.