---
title: Use o caractere de espaço por nível para recuo de lista
linktitle: Use o caractere de espaço por nível para recuo de lista
second_title: API de processamento de documentos Aspose.Words
description: Aprenda a criar listas multinível com recuo de caractere de espaço no Aspose.Words para .NET. Guia passo a passo para formatação precisa de documentos.
type: docs
weight: 10
url: /pt/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
## Introdução

Quando se trata de formatação de documentos, especialmente ao trabalhar com listas, a precisão é fundamental. Em cenários onde você precisa criar documentos com vários níveis de recuo, o Aspose.Words for .NET oferece ferramentas poderosas para lidar com essa tarefa. Um recurso específico que pode ser útil é configurar o recuo de lista em arquivos de texto. Este guia mostrará como usar caracteres de espaço para recuo de lista, garantindo que seu documento mantenha a estrutura e a legibilidade desejadas.

## Pré-requisitos

Antes de começar o tutorial, aqui está o que você precisa:

-  Aspose.Words para .NET: Certifique-se de ter a biblioteca Aspose.Words instalada. Se você ainda não a tem, você pode baixá-la do[Site Aspose](https://releases.aspose.com/words/net/).
- Visual Studio: um ambiente de desenvolvimento para escrever e testar seu código.
- Noções básicas de C#: A familiaridade com C# e o framework .NET ajudará você a acompanhar sem problemas.

## Importar namespaces

Para começar a trabalhar com o Aspose.Words, você precisará importar os namespaces necessários. Veja como você pode incluí-los no seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Vamos detalhar o processo de criação de um documento com uma lista de vários níveis e especificar caracteres de espaço para recuo. 

## Etapa 1: configure seu documento

 Primeiro, você precisará criar um novo documento e inicializá-lo`DocumentBuilder` objeto. Este objeto permitirá que você adicione conteúdo facilmente e o formate conforme necessário.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e adicione conteúdo
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Neste trecho, substitua`"YOUR DOCUMENTS DIRECTORY"` com o caminho real onde você deseja salvar seu documento.

## Etapa 2: Crie uma lista com vários níveis de recuo

 Com o`DocumentBuilder` por exemplo, agora você pode criar uma lista com diferentes níveis de recuo. Use o`ListFormat` propriedade para aplicar numeração e recuar os itens da lista conforme necessário.

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

## Etapa 3: Configurar caractere de espaço para recuo

Agora que você configurou sua lista, o próximo passo é configurar como o recuo da lista é tratado ao salvar o documento em um arquivo de texto. Você usará`TxtSaveOptions` para especificar que caracteres de espaço devem ser usados para recuo.

```csharp
// Use um caractere de espaço por nível para recuo de lista
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';
```

 Aqui,`ListIndentation.Count` especifica o número de caracteres de espaço por nível de recuo e`ListIndentation.Character` define o caractere real usado para recuo.

## Etapa 4: Salve o documento com as opções especificadas

Por fim, salve seu documento usando as opções configuradas. Isso aplicará as configurações de recuo e salvará seu arquivo no formato desejado.

```csharp
// Salve o documento com as opções especificadas
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

 Este trecho de código salva o documento no caminho especificado em`dataDir` com o nome do arquivo`"WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt"`. O arquivo salvo terá a lista formatada de acordo com suas configurações de recuo.

## Conclusão

Ao seguir essas etapas, você criou com sucesso um documento com recuo de lista multinível usando caracteres de espaço para formatação. Essa abordagem garante que suas listas sejam bem estruturadas e fáceis de ler, mesmo quando salvas como arquivos de texto. O Aspose.Words para .NET fornece ferramentas robustas para manipulação de documentos, e dominar esses recursos pode melhorar significativamente seus fluxos de trabalho de processamento de documentos.

## Perguntas frequentes

### Posso usar caracteres diferentes para recuo de lista além de espaços?
 Sim, você pode especificar caracteres diferentes para recuo de lista definindo o`Character` propriedade em`TxtSaveOptions`.

### Como posso aplicar marcadores em vez de números em listas?
 Usar`ListFormat.ApplyBulletDefault()` em vez de`ApplyNumberDefault()` para criar uma lista com marcadores.

### Posso ajustar o número de espaços para recuo dinamicamente?
 Sim, você pode ajustar o`ListIndentation.Count` propriedade para definir o número de espaços com base em suas necessidades.

### É possível alterar o recuo da lista depois que o documento é criado?
Sim, você pode modificar a formatação da lista e as configurações de recuo a qualquer momento antes de salvar o documento.

### Quais outros formatos de documento suportam configurações de recuo de lista?
Além de arquivos de texto, as configurações de recuo de lista podem ser aplicadas a outros formatos, como DOCX, PDF e HTML, ao usar o Aspose.Words.