---
title: Formato de linha desabilita quebra entre páginas
linktitle: Formato de linha desabilita quebra entre páginas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como desabilitar quebras de linha nas páginas em documentos do Word usando Aspose.Words for .NET para manter a legibilidade e a formatação da tabela.
type: docs
weight: 10
url: /pt/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Introdução

Ao trabalhar com tabelas em documentos do Word, você pode querer garantir que as linhas não se quebrem nas páginas, o que pode ser essencial para manter a legibilidade e a formatação dos seus documentos. Aspose.Words for .NET fornece uma maneira fácil de desabilitar quebras de linha nas páginas.

Neste tutorial, orientaremos você no processo de desabilitar quebras de linha nas páginas de um documento do Word usando Aspose.Words for .NET.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words para .NET instalada.
- Um documento do Word com uma tabela que abrange várias páginas.

## Importar namespaces

Primeiro, importe os namespaces necessários para o seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Etapa 1: carregue o documento

Carregue o documento que contém a tabela que abrange várias páginas.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Passo 2: Acesse a Tabela

Acesse a primeira tabela do documento. Isso pressupõe que a tabela que você deseja modificar é a primeira tabela do documento.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Etapa 3: desativar a quebra de páginas para todas as linhas

 Percorra cada linha da tabela e defina o`AllowBreakAcrossPages`propriedade para`false`. Isso garante que as linhas não serão quebradas nas páginas.

```csharp
// Desative a quebra de páginas para todas as linhas da tabela.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Etapa 4: salve o documento

Salve o documento modificado no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusão

Neste tutorial, demonstramos como desabilitar quebras de linha entre páginas em um documento do Word usando Aspose.Words for .NET. Seguindo as etapas descritas acima, você pode garantir que as linhas da tabela permaneçam intactas e não se dividam nas páginas, mantendo a legibilidade e a formatação do documento.

## Perguntas frequentes

### Posso desativar quebras de linha nas páginas para uma linha específica em vez de todas as linhas?  
 Sim, você pode desabilitar quebras de linha para linhas específicas acessando a linha desejada e definindo seu`AllowBreakAcrossPages`propriedade para`false`.

### Este método funciona para tabelas com células mescladas?  
 Sim, este método funciona para tabelas com células mescladas. A propriedade`AllowBreakAcrossPages` aplica-se a toda a linha, independentemente da mesclagem de células.

### Este método funcionará se a tabela estiver aninhada dentro de outra tabela?  
Sim, você pode acessar e modificar tabelas aninhadas da mesma maneira. Certifique-se de fazer referência correta à tabela aninhada por seu índice ou outras propriedades.

### Como posso verificar se uma linha permite a quebra entre páginas?  
 Você pode verificar se uma linha permite a quebra entre páginas acessando o`AllowBreakAcrossPages` propriedade do`RowFormat` e verificando seu valor.

### Existe uma maneira de aplicar essa configuração a todas as tabelas de um documento?  
Sim, você pode percorrer todas as tabelas do documento e aplicar esta configuração a cada uma delas.