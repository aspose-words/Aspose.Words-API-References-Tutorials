---
title: Aplicar borda de contorno
linktitle: Aplicar borda de contorno
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para aplicar uma borda de contorno a uma tabela usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Neste tutorial, orientaremos você no processo passo a passo para aplicar uma borda de contorno a uma tabela usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você terá uma compreensão clara de como manipular bordas de tabelas em seus documentos do Word usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. É aqui que o seu documento do Word é armazenado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento
 Em seguida, você precisa carregar o documento do Word em uma instância do`Document` aula.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Passo 3: Acesse a tabela
 Para aplicar uma borda de contorno, precisamos acessar a tabela do documento. O`Table` class representa uma tabela em Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Etapa 4: alinhe a tabela ao centro da página
 Agora podemos alinhar a tabela ao centro da página usando o`Alignment` propriedade da tabela.

```csharp
table. Alignment = Table Alignment. Center;
```

## Passo 5: Apague as bordas da tabela existentes
Para começar com uma nova borda de contorno, primeiro precisamos apagar todas as bordas existentes da tabela. Isto pode ser feito usando o`ClearBorders()` método.

```csharp
table. ClearBorders();
```

## Passo 6: Defina uma borda verde ao redor da mesa
 Agora podemos definir uma borda verde ao redor da mesa usando o`SetBorder()` método para cada lado da tabela. Neste exemplo, estamos usando uma borda do tipo “Single” com espessura de 1,5 pontos e cor verde.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Etapa 7: preencha as células com uma cor de fundo
Para melhorar a apresentação visual da tabela, podemos preencher as células com uma cor de fundo básica

ideia. Neste exemplo, estamos usando uma cor verde claro.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Etapa 8: salve o documento modificado
Finalmente, salvamos o documento modificado em um arquivo. Você pode escolher um nome e local apropriado para o documento de saída.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Parabéns! Agora você aplicou uma borda de contorno a uma tabela usando Aspose.Words for .NET.

### Exemplo de código-fonte para Aplicar borda de contorno usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Alinhe a tabela ao centro da página.
	table.Alignment = TableAlignment.Center;
	//Limpe todas as bordas existentes da tabela.
	table.ClearBorders();
	// Defina uma borda verde ao redor da mesa, mas não dentro dela.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Preencha as células com uma cor sólida verde claro.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Conclusão
Neste tutorial, aprendemos como aplicar uma borda de contorno a uma tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode integrar facilmente essa funcionalidade em seus projetos C#. Manipular a formatação da tabela é um aspecto essencial do processamento de documentos, e Aspose.Words oferece uma API poderosa e flexível para conseguir isso. Com esse conhecimento, você poderá melhorar a apresentação visual de seus documentos Word e atender a requisitos específicos.