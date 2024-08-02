---
title: Mantenha a mesa unida
linktitle: Mantenha a mesa unida
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como evitar que tabelas se quebrem nas páginas de documentos do Word usando Aspose.Words for .NET. Siga nosso guia para manter documentos profissionais e legíveis.
type: docs
weight: 10
url: /pt/net/programming-with-tables/keep-table-together/
---
## Introdução

Você já ficou frustrado quando uma tabela em seu documento do Word se divide em duas páginas? É como se suas informações cuidadosamente organizadas de repente decidissem fazer uma pausa no meio do caminho! Manter as tabelas juntas em uma página é crucial para a legibilidade e a apresentação. Seja para um relatório, uma proposta de projeto ou apenas um documento pessoal, dividir tabelas pode ser bastante chocante. Para nossa sorte, o Aspose.Words for .NET tem uma maneira bacana de resolver esse problema. Neste tutorial, percorreremos as etapas para manter suas tabelas intactas e com aparência nítida. Vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Aspose.Words for .NET - Se você ainda não o instalou, pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
2. Um documento do Word com uma tabela - trabalharemos com um documento de exemplo que possui uma tabela abrangendo várias páginas.
3. Conhecimento básico de C# – Este tutorial pressupõe que você tenha um conhecimento básico de programação C#.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Isso nos dará acesso às classes e métodos que precisamos do Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Vamos dividir o processo em etapas fáceis e digeríveis. Começaremos carregando nosso documento e terminaremos salvando o documento atualizado onde a tabela permanece unida.

## Etapa 1: carregue o documento

 Para trabalhar com um documento do Word, primeiro precisamos carregá-lo. Usaremos o`Document` aula para isso.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Passo 2: Acesse a Tabela

Em seguida, precisamos reunir a mesa que queremos manter. Assumiremos que é a primeira tabela do documento.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Etapa 3: definir KeepWithNext para parágrafos

 Para evitar que a tabela se quebre nas páginas, precisamos definir o`KeepWithNext` propriedade para cada parágrafo da tabela, exceto para os últimos parágrafos da última linha.

```csharp
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
    cell.EnsureMinimum();
    foreach (Paragraph para in cell.Paragraphs)
    {
        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }
}
```

## Etapa 4: salve o documento

Por fim, salvamos o documento atualizado. Isso aplicará nossas alterações e garantirá que a tabela permaneça unida em uma página.

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusão

aí está! Com apenas algumas linhas de código, você pode evitar que suas tabelas se dividam nas páginas de seus documentos do Word. Esta solução simples, mas eficaz, garante que as suas tabelas permaneçam organizadas e profissionais, melhorando a legibilidade dos seus documentos. Aspose.Words for .NET facilita muito o tratamento desses problemas de formatação, permitindo que você se concentre na criação de ótimo conteúdo.

## Perguntas frequentes

### Posso manter várias tabelas juntas usando este método?  
Sim, você pode aplicar a mesma lógica a várias tabelas iterando cada tabela do seu documento.

### E se minha tabela for muito grande para caber em uma página?  
Se uma tabela for muito grande para caber em uma única página, ela ainda se estenderá pelas páginas. Este método garante que tabelas menores permaneçam intactas sem divisão.

### Existe uma maneira de automatizar isso para todas as tabelas de um documento?  
 Sim, você pode percorrer todas as tabelas do seu documento e aplicar o`KeepWithNext` propriedade para cada parágrafo.

### Preciso de uma licença paga do Aspose.Words for .NET?  
Você pode começar com uma avaliação gratuita em[aqui](https://releases.aspose.com/), mas para funcionalidade completa, recomenda-se uma licença paga.

### Posso aplicar outra formatação à tabela enquanto a mantenho unida?  
Absolutamente! Você pode formatar sua tabela conforme necessário, garantindo que ela permaneça unida em uma página.