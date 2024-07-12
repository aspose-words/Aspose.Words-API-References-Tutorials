---
title: Recuperar tipo de largura preferencial
linktitle: Recuperar tipo de largura preferencial
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como recuperar o tipo e o valor de largura preferencial de uma célula em uma tabela do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/retrieve-preferred-width-type/
---

Neste tutorial, aprenderemos como recuperar o tipo de largura preferido e seu valor de uma célula de tabela em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá recuperar o tipo de largura preferido (absoluta, relativa ou automática) e seu valor para uma célula específica nas tabelas de documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento
Para iniciar o processamento de palavras com o documento, siga estas etapas:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Tables.docx");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos e forneça o nome de arquivo correto.

## Etapa 3: recuperar o tipo e valor de largura preferido
A seguir, recuperaremos o tipo de largura preferido e seu valor para uma célula específica da tabela. Use o seguinte código:

```csharp
// Recuperar a tabela
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Ative o ajuste automático da mesa
table. AllowAutoFit = true;

//Recuperar a primeira célula da primeira linha
Cell firstCell = table.FirstRow.FirstCell;

// Recuperar o tipo de largura preferido e seu valor
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Aqui usamos o documento para buscar a primeira tabela, depois habilitamos o ajuste automático da tabela com o`AllowAutoFit` propriedade. Em seguida, recuperamos a primeira célula da primeira linha da tabela. A partir desta célula, podemos recuperar o tipo de largura preferido com o`PreferredWidth.Type` propriedade e seu valor com o`PreferredWidth.Value` propriedade.

### Exemplo de código-fonte para recuperar tipo de largura preferencial usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Conclusão
Neste tutorial, aprendemos como recuperar o tipo de largura preferido e seu valor de uma célula de tabela em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode recuperar essas informações para células específicas em suas tabelas de documentos do Word.