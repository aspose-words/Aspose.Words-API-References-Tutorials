---
title: Definir posição relativa horizontal ou vertical
linktitle: Definir posição relativa horizontal ou vertical
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir a posição relativa horizontal ou vertical de uma tabela em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Neste tutorial, aprenderemos como definir a posição relativa horizontal ou vertical de uma tabela em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá definir a posição relativa horizontal ou vertical de sua tabela em seus documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento
Para iniciar o processamento de palavras com o documento, siga estas etapas:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos e forneça o nome de arquivo correto.

## Passo 3: Definir a posição relativa da mesa
A seguir, definiremos a posição horizontal ou vertical relativa da tabela. Use o seguinte código:

```csharp
// Recuperar a tabela
Table table = doc.FirstSection.Body.Tables[0];

//Definição da posição horizontal relativa da mesa
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Defina a posição vertical relativa da mesa
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Aqui usamos o documento para recuperar a primeira tabela do corpo da primeira seção. A seguir, definimos a posição horizontal relativa da mesa com o`HorizontalAnchor` propriedade usando o`RelativeHorizontalPosition.Column` valor. Da mesma forma, definimos a posição vertical relativa da mesa com o`VerticalAnchor` propriedade usando o`RelativeVerticalPosition.Page` valor.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com a posição relativa da tabela definida. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para definir posição relativa horizontal ou vertical usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Conclusão
Neste tutorial, aprendemos como definir a posição relativa horizontal ou vertical de uma tabela em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode aplicar essa posição relativa às tabelas em seus documentos do Word.