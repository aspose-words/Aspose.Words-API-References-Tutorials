---
title: Use caractere de espaço por nível para recuo de lista
linktitle: Use caractere de espaço por nível para recuo de lista
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar listas de vários níveis com recuo de caracteres de espaço em Aspose.Words for .NET. Guia passo a passo para formatação precisa de documentos.
type: docs
weight: 10
url: /pt/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
## Introdução

Quando se trata de formatação de documentos, especialmente ao trabalhar com listas, a precisão é fundamental. Em cenários onde você precisa criar documentos com vários níveis de recuo, Aspose.Words for .NET oferece ferramentas poderosas para realizar essa tarefa. Um recurso específico que pode ser útil é configurar o recuo da lista em arquivos de texto. Este guia orientará você sobre como usar caracteres de espaço para recuo de lista, garantindo que seu documento mantenha a estrutura e a legibilidade desejadas.

## Pré-requisitos

Antes de mergulhar no tutorial, aqui está o que você precisa:

-  Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words instalada. Se você ainda não o possui, pode baixá-lo no site[Aspor site](https://releases.aspose.com/words/net/).
- Visual Studio: um ambiente de desenvolvimento para escrever e testar seu código.
- Compreensão básica de C#: A familiaridade com C# e .NET framework o ajudará a seguir em frente sem problemas.

## Importar namespaces

Para começar a trabalhar com Aspose.Words, você precisará importar os namespaces necessários. Veja como você pode incluí-los em seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Vamos detalhar o processo de criação de um documento com uma lista de vários níveis e a especificação de caracteres de espaço para recuo. 

## Etapa 1: configure seu documento

 Primeiro, você precisará criar um novo documento e inicializar o`DocumentBuilder` objeto. Este objeto permitirá que você adicione facilmente conteúdo e formate-o conforme necessário.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e adicione conteúdo
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Neste trecho, substitua`"YOUR DOCUMENTS DIRECTORY"` com o caminho real onde você deseja salvar seu documento.

## Etapa 2: crie uma lista com vários níveis de recuo

 Com o`DocumentBuilder` Por exemplo, agora você pode criar uma lista com diferentes níveis de recuo. Use o`ListFormat` propriedade para aplicar numeração e recuar os itens da lista conforme necessário.

```csharp
// Crie uma lista com três níveis de recuo
builder.ListFormat.ApplyNumberDefault();
builder.Write("Element 1");
builder.ListFormat.ListIndent();
builder.Write("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 Nesta etapa,`ApplyNumberDefault` configura o formato da lista e`ListIndent` é usado para aumentar o nível de recuo para cada item de lista subsequente.

## Etapa 3: configurar o caractere de espaço para recuo

Agora que você configurou sua lista, a próxima etapa é configurar como o recuo da lista é tratado ao salvar o documento em um arquivo de texto. Você usará`TxtSaveOptions` para especificar que caracteres de espaço devem ser usados para recuo.

```csharp
// Use um caractere de espaço por nível para recuo da lista
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';
```

 Aqui,`ListIndentation.Count` especifica o número de caracteres de espaço por nível de recuo e`ListIndentation.Character` define o caractere real usado para recuo.

## Etapa 4: salve o documento com as opções especificadas

Por fim, salve seu documento usando as opções configuradas. Isso aplicará as configurações de recuo e salvará seu arquivo no formato desejado.

```csharp
// Salve o documento com as opções especificadas
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

 Este trecho de código salva o documento no caminho especificado em`dataDir` com o nome do arquivo`"WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt"`. O arquivo salvo terá a lista formatada de acordo com suas configurações de recuo.

## Conclusão

Seguindo essas etapas, você criou com êxito um documento com recuo de lista de vários níveis usando caracteres de espaço para formatação. Essa abordagem garante que suas listas sejam bem estruturadas e fáceis de ler, mesmo quando salvas como arquivos de texto. Aspose.Words for .NET fornece ferramentas robustas para manipulação de documentos, e dominar esses recursos pode melhorar significativamente seus fluxos de trabalho de processamento de documentos.

## Perguntas frequentes

### Posso usar caracteres diferentes para recuo de lista além de espaços?
 Sim, você pode especificar caracteres diferentes para recuo da lista definindo a opção`Character` propriedade em`TxtSaveOptions`.

### Como aplico marcadores em vez de números nas listas?
 Usar`ListFormat.ApplyBulletDefault()` em vez de`ApplyNumberDefault()` para criar uma lista com marcadores.

### Posso ajustar dinamicamente o número de espaços para recuo?
 Sim, você pode ajustar o`ListIndentation.Count` propriedade para definir o número de espaços com base em seus requisitos.

### É possível alterar o recuo da lista após a criação do documento?
Sim, você pode modificar as configurações de formatação e recuo da lista a qualquer momento antes de salvar o documento.

### Que outros formatos de documento suportam configurações de recuo de lista?
Além dos arquivos de texto, as configurações de recuo da lista podem ser aplicadas a outros formatos, como DOCX, PDF e HTML ao usar Aspose.Words.