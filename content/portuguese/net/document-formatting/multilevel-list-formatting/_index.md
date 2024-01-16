---
title: Formatação de lista multinível em documento do Word
linktitle: Formatação de lista multinível em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma lista multinível e aplicar formatação personalizada em documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/document-formatting/multilevel-list-formatting/
---
Neste tutorial, mostraremos como usar o recurso de formatação de lista multinível em documentos do Word com Aspose.Words for .NET. Siga as etapas abaixo para entender o código-fonte e aplicar as alterações.

## Passo 1: Criando e configurando o documento

Para começar, crie um novo documento e um objeto DocumentBuilder associado. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passo 2: Formatando a lista multinível

Aplicaremos agora a formatação de lista multinível usando os métodos disponíveis no objeto DocumentBuilder. Veja como:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Passo 3: Salvando o documento

 Após inserir o campo do formulário de entrada de texto, salve o documento no local desejado usando o`Save` método. Certifique-se de fornecer o caminho de arquivo apropriado:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Exemplo de código-fonte para formatação de lista multinível usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso de formatação de lista multinível com Aspose.Words for .NET:


```csharp

// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Com este código você poderá criar uma lista multinível e aplicar a formatação adequada a cada nível usando Aspose.Words for .NET.


## Conclusão

Neste tutorial, exploramos o processo de utilização do recurso de formatação de lista multinível em um documento do Word com Aspose.Words for .NET. Seguindo as etapas descritas, você pode criar listas bem organizadas com vários níveis, melhorando a estrutura e a legibilidade dos seus documentos.

### Perguntas frequentes

#### P: O que é uma lista multinível em um documento do Word?

R: Uma lista multinível em um documento do Word é uma lista hierárquica que permite organizar itens em vários níveis de subitens. Ajuda a apresentar as informações de forma estruturada, facilitando a compreensão do conteúdo pelo leitor.

#### P: Posso personalizar a aparência da lista multinível?

R: Sim, você pode personalizar a aparência da lista multinível em seu documento do Word. Ao aplicar estilos diferentes, como marcadores, números ou letras, e ajustar o recuo e o espaçamento, você pode criar uma lista organizada e visualmente atraente.

#### P: O Aspose.Words for .NET oferece suporte a outras opções de formatação de lista?

R: Sim, Aspose.Words for .NET fornece um conjunto abrangente de recursos para formatação de listas. Ele oferece suporte a vários tipos de lista, incluindo listas com marcadores, listas numeradas e listas de vários níveis. Você pode manipular a formatação de listas, adicionar ou remover itens e personalizar sua aparência.

#### P: Posso usar o Aspose.Words for .NET para trabalhar com outros elementos do documento?

R: Sim, o Aspose.Words for .NET oferece amplos recursos para trabalhar com vários elementos de documentos, como parágrafos, tabelas, imagens e muito mais. Ele permite criar, modificar e converter documentos do Word de forma programática, agilizando as tarefas de processamento de documentos.