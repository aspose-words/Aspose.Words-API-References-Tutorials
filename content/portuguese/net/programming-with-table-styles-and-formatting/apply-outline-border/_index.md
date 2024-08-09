---
title: Aplicar borda de contorno
linktitle: Aplicar borda de contorno
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como aplicar uma borda de contorno a uma tabela no Word usando Aspose.Words for .NET. Siga nosso guia passo a passo para uma formatação de tabela perfeita.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/apply-outline-border/
---
## Introdução

No tutorial de hoje, mergulharemos no mundo da manipulação de documentos usando Aspose.Words for .NET. Especificamente, aprenderemos como aplicar uma borda de contorno a uma tabela em um documento do Word. Essa é uma habilidade fantástica para ter em seu kit de ferramentas se você trabalha frequentemente com geração e formatação automatizada de documentos. Então, vamos começar esta jornada para tornar suas mesas não apenas funcionais, mas também visualmente atraentes.

## Pré-requisitos

Antes de entrarmos no código, há algumas coisas que você precisará:

1.  Aspose.Words for .NET: Você precisa ter o Aspose.Words for .NET instalado. Você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: um ambiente de desenvolvimento adequado como o Visual Studio.
3. Conhecimento básico de C#: uma compreensão fundamental de C# o ajudará a acompanhar o tutorial.

## Importar namespaces

Para começar, certifique-se de importar os namespaces necessários. Isso é crucial para acessar as funcionalidades do Aspose.Words.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

Vamos dividir o processo em etapas simples e gerenciáveis.

## Etapa 1: carregue o documento

Primeiro precisamos carregar o documento Word que contém a tabela que queremos formatar.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
```

 Nesta etapa, estamos usando o`Document` classe de Aspose.Words para carregar um documento existente. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde seu documento está armazenado.

## Passo 2: Acesse a Tabela

A seguir, precisamos acessar a tabela específica que queremos formatar. 

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

 Aqui,`GetChild` O método busca a primeira tabela do documento. Os parâmetros`NodeType.Table, 0, true` garantir que obtemos o tipo de nó correto.

## Etapa 3: Alinhe a Mesa

Agora, vamos centralizar a tabela na página.

```csharp
table.Alignment = TableAlignment.Center;
```

Esta etapa garante que a mesa fique bem centralizada, dando-lhe uma aparência profissional.

## Etapa 4: limpar as fronteiras existentes

Antes de aplicarmos novas fronteiras, precisamos de limpar quaisquer das existentes.

```csharp
table.ClearBorders();
```

Limpar as bordas garante que nossas novas bordas sejam aplicadas de forma limpa, sem interferência de estilos antigos.

## Etapa 5: definir bordas de contorno

Agora, vamos aplicar as bordas verdes à mesa.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

 Cada tipo de borda (esquerda, direita, superior, inferior) é definida individualmente. Nós usamos`LineStyle.Single` para uma linha sólida,`1.5` para a largura da linha e`Color.Green` para a cor da borda.

## Etapa 6: aplicar sombreamento celular

Para tornar a tabela mais atraente visualmente, vamos preencher as células com uma cor verde claro.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

 Aqui,`SetShading` é usado para aplicar uma cor verde clara sólida às células, destacando a tabela.

## Etapa 7: salve o documento

Finalmente, salve o documento modificado.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Esta etapa salva seu documento com a formatação aplicada. Você pode abri-lo para ver a tabela lindamente formatada.

## Conclusão

E aí está! Seguindo essas etapas, você aplicou com êxito uma borda de contorno a uma tabela em um documento do Word usando Aspose.Words for .NET. Este tutorial abordou o carregamento do documento, o acesso à tabela, o alinhamento, a limpeza das bordas existentes, a aplicação de novas bordas, a adição de sombreamento às células e, por fim, o salvamento do documento. 

Com essas habilidades, você pode aprimorar a apresentação visual de suas tabelas, tornando seus documentos mais profissionais e atraentes. Boa codificação!

## Perguntas frequentes

### Posso aplicar estilos diferentes a cada borda da tabela?  
 Sim, você pode aplicar diferentes estilos e cores a cada borda ajustando os parâmetros no`SetBorder` método.

### Como posso alterar a largura da borda?  
 Você pode alterar a largura modificando o terceiro parâmetro no`SetBorder` método. Por exemplo,`1.5` define uma largura de 1,5 pontos.

### É possível aplicar sombreamento a células individuais?  
 Sim, você pode aplicar sombreamento a células individuais acessando cada célula e usando o botão`SetShading` método.

### Posso usar outras cores para bordas e sombreamento?  
 Absolutamente! Você pode usar qualquer cor disponível no`System.Drawing.Color` aula.

### Como faço para centralizar a tabela horizontalmente?  
 O`table.Alignment = TableAlignment.Center;` linha no código centraliza a tabela horizontalmente na página.