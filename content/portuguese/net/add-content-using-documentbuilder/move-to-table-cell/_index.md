---
title: Mover para a célula da tabela no documento do Word
linktitle: Mover para a célula da tabela no documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para usar o recurso Mover para célula da tabela no documento Word do Aspose.Words for .NET
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/move-to-table-cell/
---
Neste exemplo, orientaremos você sobre como usar o recurso Mover para célula da tabela em documento do Word do Aspose.Words for .NET usando o código-fonte C# fornecido, passo a passo. Este recurso permite navegar e manipular células específicas dentro de uma tabela em um documento do Word. Siga as etapas abaixo para integrar essa funcionalidade ao seu aplicativo.

## Passo 1: Carregue o documento que contém a tabela

Primeiro, precisamos carregar o documento que contém a tabela para a qual queremos mover a célula. Use o seguinte código para realizar esta etapa:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Este código carrega o documento especificado (substitua "MyDir +" Tables.docx"" com o caminho real do seu documento que contém a tabela).

## Etapa 2: mover o DocumentBuilder para uma célula específica da tabela

A seguir, moveremos o DocumentBuilder para uma célula específica da tabela. Use o seguinte código para executar esta etapa:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Este código cria um DocumentBuilder a partir do documento existente e, em seguida, move o cursor do DocumentBuilder para a célula da tabela especificada. Finalmente, ele adiciona conteúdo a essa célula usando o DocumentBuilder`Write()` método.

## Etapa 3: verifique o resultado

Agora você pode verificar se a mudança para a célula da tabela foi bem-sucedida. Use o seguinte código para realizar esta etapa:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Este código verifica se a célula especificada é de fato a célula atual do DocumentBuilder. Também verifica se o conteúdo adicionado pelo DocumentBuilder foi salvo corretamente na célula da tabela.

Isso é tudo ! Agora você entendeu como usar a funcionalidade de mudança para célula da tabela do Aspose.Words for .NET usando o código-fonte fornecido. Agora você pode integrar essa funcionalidade em seu próprio aplicativo e manipular células específicas de tabelas em documentos do Word.


### Exemplo de código-fonte para mover para uma célula da tabela usando Aspose.Words for .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Mova o construtor para a linha 3, célula 4 da primeira tabela.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## Conclusão

Neste exemplo, exploramos o recurso Move To Table Cell do Aspose.Words for .NET. Aprendemos como carregar um documento contendo uma tabela, mover o DocumentBuilder para uma célula específica da tabela e adicionar conteúdo a essa célula. Este recurso fornece aos desenvolvedores ferramentas poderosas para navegar e manipular células específicas em tabelas de documentos do Word programaticamente usando Aspose.Words for .NET. Pode ser uma adição valiosa ao seu aplicativo para processamento dinâmico de documentos do Word e gerenciamento de conteúdo de tabela.

### Perguntas frequentes sobre como mover para a célula da tabela em um documento do Word

#### P: Qual é o propósito do recurso Mover para célula da tabela no Aspose.Words for .NET?

R: O recurso Mover para célula da tabela no Aspose.Words for .NET permite que os desenvolvedores naveguem e manipulem células específicas dentro de uma tabela em um documento do Word programaticamente. Ele fornece a capacidade de inserir, modificar ou excluir conteúdo de uma célula específica.

#### P: Como movo o DocumentBuilder para uma célula específica da tabela em um documento do Word?

R: Para mover o DocumentBuilder para uma célula específica da tabela em um documento do Word, você pode usar o método MoveToCell da classe DocumentBuilder. Este método usa os índices da linha e célula de destino da tabela como parâmetros e coloca o cursor no início dessa célula.

#### P: Posso adicionar ou modificar conteúdo depois de passar para uma célula específica da tabela usando o recurso Mover para célula da tabela?

R: Sim, depois que o DocumentBuilder estiver posicionado na célula desejada da tabela usando MoveToCell, você poderá usar vários métodos da classe DocumentBuilder, como Write, Writeln ou InsertHtml, para adicionar ou modificar o conteúdo dessa célula.

#### P: Como posso verificar se a mudança para a célula da tabela foi bem-sucedida?

R: Você pode verificar a movimentação bem-sucedida para a célula da tabela verificando a posição do cursor do DocumentBuilder. Por exemplo, você pode comparar o nó atual do DocumentBuilder com a célula para a qual você pretendia mover e verificar se o conteúdo adicionado pelo DocumentBuilder foi salvo corretamente na célula da tabela.