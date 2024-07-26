---
title: Alterar paradas de tabulação no documento do Word
linktitle: Alterar paradas de tabulação no documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como alterar as guias do índice em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e manipular documentos do Word em um aplicativo C#. Dentre as funcionalidades oferecidas pelo Aspose.Words, existe a possibilidade de modificar as abas utilizadas em um índice de um documento Word. Neste guia, mostraremos como usar o código-fonte C# do Aspose.Words for .NET para alterar as guias no índice de um documento.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca popular que torna o processamento de palavras com documentos do Word fácil e eficiente. Ele oferece uma ampla gama de recursos para criar, editar e manipular documentos do Word, incluindo a alteração das guias do índice.

## Carregando o documento que contém o índice

O primeiro passo é carregar o documento Word que contém o índice que você deseja modificar. Use a classe Document para carregar o documento do arquivo de origem. Aqui está um exemplo :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Neste exemplo, carregamos o documento "Índice.docx" localizado no diretório de documentos.

## Alterando guias no índice

Depois que o documento é carregado, percorremos cada parágrafo do documento e verificamos se ele está formatado usando os estilos de resultado do Índice (TOC). Nesse caso, modificamos as tabulações usadas para alinhar os números das páginas. Veja como:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

Neste exemplo, estamos usando um loop para percorrer cada parágrafo do documento. Em seguida, verificamos se o parágrafo está formatado usando os estilos de resultado do índice (TOC). Nesse caso, acessamos a primeira aba usada neste parágrafo e a modificamos removendo a aba antiga e adicionando uma nova aba com uma posição modificada.

## Salvar documento modificado

Depois de fazer as alterações necessárias nas guias do índice, você pode salvar o documento modificado usando o método Save da classe Document. Aqui está um exemplo :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Neste exemplo, salvamos o documento modificado como "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Exemplo de código-fonte para o recurso "Editar guias do índice" com Aspose.Words for .NET

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento que contém o índice
Document doc = new Document(dataDir + "Table of contents.docx");

// Modifique as guias do índice
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Salve o documento modificado
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Conclusão

Neste guia, abordamos como usar Aspose.Words for .NET para alterar as guias no índice de um documento do Word usando o código-fonte C# fornecido. Seguindo as etapas fornecidas, você pode personalizar facilmente as guias do índice em seus documentos do Word em seu aplicativo C#. Aspose.Words oferece enorme flexibilidade e poder para trabalhar com os estilos e formatação de seus documentos, permitindo criar documentos Word atraentes e profissionais.

### Perguntas frequentes sobre como alterar paradas de tabulação em documentos do Word

#### P: Qual é o propósito da funcionalidade "Alterar paradas de tabulação no documento do Word" no Aspose.Words for .NET?

R: A funcionalidade "Alterar paradas de tabulação no documento do Word" no Aspose.Words for .NET permite que você modifique as paradas de tabulação usadas no índice de um documento do Word. Ele permite que você personalize o alinhamento e o posicionamento dos números das páginas e dos títulos correspondentes no índice analítico.

#### P: O que é Aspose.Words para .NET?

R: Aspose.Words for .NET é uma biblioteca poderosa projetada para processamento de palavras com documentos do Word em aplicativos .NET. Ele fornece recursos abrangentes para criar, editar, manipular e converter documentos do Word programaticamente usando C# ou outras linguagens .NET.

#### P: Como carrego um documento do Word contendo um índice usando Aspose.Words for .NET?

 R: Para carregar um documento do Word contendo um índice usando Aspose.Words for .NET, você pode usar o`Document` classe e seu construtor. Ao fornecer o caminho do arquivo do documento, você pode carregá-lo em um`Document` objeto. Aqui está um exemplo:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Este trecho de código carrega o documento "Índice.docx" localizado no diretório especificado.

#### P: Como posso alterar as guias usadas no índice usando Aspose.Words for .NET?

R: Depois que o documento for carregado, você poderá percorrer cada parágrafo do documento e verificar se ele está formatado usando os estilos de resultado do Índice (TOC). Se um parágrafo estiver formatado como estilo de índice, você poderá modificar as guias usadas para alinhar os números das páginas. No Aspose.Words for .NET, você pode acessar o`ParagraphFormat` propriedade de cada parágrafo para recuperar e modificar as paradas de tabulação. Aqui está um exemplo:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

Neste código, o loop percorre cada parágrafo do documento. Se um parágrafo tiver um estilo de índice, ele acessa a primeira parada de tabulação usada naquele parágrafo, remove-a e adiciona uma nova parada de tabulação com uma posição modificada.

#### P: Posso alterar as guias de vários níveis no índice usando Aspose.Words for .NET?

R: Sim, você pode alterar as guias de vários níveis no índice usando Aspose.Words for .NET. Ao percorrer cada parágrafo e verificar o estilo do sumário, você pode modificar as guias de cada nível individualmente. Você pode acessar o nível desejado do índice e ajustar as paradas de tabulação de acordo.

#### P: Como faço para salvar o documento modificado após alterar as guias do índice usando Aspose.Words for .NET?

 R: Depois de fazer as alterações necessárias nas guias do índice, você pode salvar o documento modificado usando o`Save` método do`Document` aula. Forneça o caminho e o nome do arquivo desejado para o documento de saída como parâmetro para o`Save` método. Aqui está um exemplo:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Este código salva o documento modificado como "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### P: Posso personalizar outros aspectos do índice usando Aspose.Words for .NET?

R: Sim, com Aspose.Words for .NET, você pode personalizar vários aspectos do índice analítico. Além de alterar as guias, você pode modificar os estilos de fonte, tamanho, alinhamento e outras propriedades de formatação das entradas do índice e números de página. Além disso, você pode ajustar o recuo, o espaçamento e a formatação dos títulos correspondentes.

#### P:. Posso alterar o alinhamento das guias e os caracteres iniciais do índice usando Aspose.Words for .NET?

R: Sim, você pode alterar o alinhamento das guias e os caracteres iniciais do índice usando Aspose.Words for .NET. Ao acessar as paradas de tabulação e ajustar seu alinhamento e propriedades de linha de chamada, você pode controlar o alinhamento e a aparência visual dos números de página e títulos correspondentes no índice analítico.

#### P: O Aspose.Words for .NET oferece suporte à alteração de outros estilos e formatação em documentos do Word?

R: Sim, o Aspose.Words for .NET oferece amplo suporte para alteração de vários estilos e formatação em documentos do Word. Ele permite modificar estilos de diferentes elementos, como parágrafos, títulos, tabelas, listas e muito mais. Você pode alterar fontes, cores, alinhamento, recuo, espaçamento e outros aspectos de formatação de acordo com suas necessidades.

#### P: Posso modificar as guias do índice em um documento do Word existente usando Aspose.Words for .NET?

R: Sim, você pode modificar as guias do índice em um documento do Word existente usando Aspose.Words for .NET. Ao carregar o documento, iterar pelos parágrafos e fazer as alterações necessárias nas paradas de tabulação, você pode atualizar as guias no sumário. Por fim, salve o documento para aplicar as modificações.