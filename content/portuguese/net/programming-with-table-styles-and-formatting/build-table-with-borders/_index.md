---
title: Construir mesa com bordas
linktitle: Construir mesa com bordas
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para construir uma tabela com bordas usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

Neste tutorial, orientaremos você no processo passo a passo para construir uma tabela com bordas usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como criar uma tabela com bordas personalizadas em seus documentos Word usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. É aqui que o seu documento do Word é armazenado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: carregar o documento existente
 Em seguida, você precisa carregar o documento Word existente em uma instância do`Document` aula.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Passo 3: Acesse a tabela e remova as bordas existentes
 Para começar a construir a tabela com bordas, precisamos navegar até a tabela no documento e remover as bordas existentes. O`ClearBorders()` O método remove todas as bordas da tabela.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## Etapa 4: definir bordas da tabela
 Agora podemos definir as bordas da tabela usando o`SetBorders()` método. Neste exemplo, estamos usando uma borda verde com espessura de 1,5 pontos.

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## Etapa 5: salve o documento modificado
Finalmente, salvamos o documento modificado em um arquivo. Você pode escolher um nome e local apropriado para o documento de saída.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

Parabéns! Agora você construiu uma tabela com bordas personalizadas usando Aspose.Words for .NET.

### Exemplo de código-fonte para construir tabela com bordas usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Limpe todas as bordas existentes da tabela.
	table.ClearBorders();
	// Defina uma borda verde ao redor e dentro da mesa.
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## Conclusão
Neste tutorial, aprendemos como construir uma tabela com bordas usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode personalizar facilmente as bordas da tabela em seus documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você poderá melhorar a apresentação visual de seus documentos Word e atender necessidades específicas.