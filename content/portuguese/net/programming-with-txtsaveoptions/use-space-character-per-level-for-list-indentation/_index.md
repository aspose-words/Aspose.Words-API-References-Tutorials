---
title: Use caractere de espaço por nível para recuo de lista
linktitle: Use caractere de espaço por nível para recuo de lista
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para usar um caractere de espaço por nível para recuo de lista em Aspose.Words for .NET. Crie documentos Word bem estruturados com facilidade.
type: docs
weight: 10
url: /pt/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e manipular documentos do Word em um aplicativo C#. Entre as funcionalidades oferecidas pelo Aspose.Words está a possibilidade de utilizar um caractere de espaço por nível para o recuo de listas. Neste guia, mostraremos como usar o código-fonte C# do Aspose.Words for .NET para implementar esta funcionalidade.

## Compreendendo a biblioteca Aspose.Words

Antes de mergulhar no código, é importante entender a biblioteca Aspose.Words para .NET. Aspose.Words é uma biblioteca popular que torna o processamento de palavras com documentos do Word fácil e eficiente. Oferece uma ampla gama de funcionalidades para criação, modificação e manipulação de documentos Word, incluindo gerenciamento de listas e recuos.

## Criando o documento e adicionando conteúdo

primeira etapa é criar um novo documento e adicionar conteúdo a ele. Use a classe Document para criar uma nova instância de documento. Em seguida, use a classe DocumentBuilder para adicionar texto e criar uma lista com vários níveis de recuo. Aqui está um exemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crie uma lista com três níveis de recuo
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Neste exemplo, criamos um novo documento e usamos o DocumentBuilder para adicionar texto e criar uma lista com três níveis de recuo. Adicionamos três itens à lista, e cada item indica um nível adicional.

## Usando um caractere de espaço por nível para recuo da lista

Uma vez adicionado o conteúdo, podemos agora configurar o recuo das listas usando um caractere de espaço por nível. Para isso utilizamos a classe TxtSaveOptions e definimos a propriedade ListIndentation.Count para o número de níveis de indentação e a propriedade ListIndentation.Character para o caractere de espaço a ser utilizado. Veja como:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

Neste exemplo, criamos uma instância de TxtSaveOptions e definimos a propriedade ListIndentation.Count como 3 para indicar que existem três níveis de recuo na lista. Também definimos a propriedade ListIndentation.Character como o caractere de espaço (' ') que queremos usar para recuo.

### Exemplo de código-fonte para o recurso "Usar um caractere de espaço por nível para recuo de lista" com Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para o recurso "Usar um caractere de espaço por nível para recuo de lista" com Aspose.Words for .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Caminho para o diretório do seu documento
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Crie o documento e adicione conteúdo
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Crie uma lista com três níveis de recuo
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Use um caractere de espaço por nível para recuo da lista
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Salve o documento com as opções especificadas
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Conclusão

Neste guia, explicamos como usar Aspose.Words for .NET para aplicar a funcionalidade "Usar um caractere de espaço por nível para recuo de lista". Seguindo as etapas fornecidas e usando o código-fonte C# fornecido, você pode configurar facilmente o recuo de listas em seus documentos do Word usando um caractere de espaço por nível. Aspose.Words oferece enorme flexibilidade e poder para processamento de palavras com formatação de texto e gerenciamento de lista, permitindo criar documentos bem estruturados em seu aplicativo C#.

### perguntas frequentes

#### P: O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e manipular documentos Word em um aplicativo C#. Ele oferece muitos recursos para processamento de palavras com documentos do Word, incluindo a capacidade de usar um espaço por nível para recuar listas.

#### P: Como posso usar um espaço por nível para recuo de lista com Aspose.Words for .NET?
Você pode usar um espaço por nível para recuo da lista seguindo estas etapas:

 Crie um novo documento usando o`Document` aula.

 Use o`DocumentBuilder`class para adicionar conteúdo ao documento e criar uma lista com vários níveis de recuo.

 Depois de adicionar o conteúdo e configurar o recuo da lista, use o comando`TxtSaveOptions` classe e definir o`ListIndentation.Count` propriedade para o número de níveis de indentação e o`ListIndentation.Character` propriedade no espaço (`' '`) usar.

 Salve o documento com as opções especificadas usando o`Save` método do`Document` aula.

#### P: O Aspose.Words oferece suporte a outros caracteres para recuo de lista?
Sim, Aspose.Words suporta outros caracteres para recuar listas. Você pode usar caracteres que não sejam espaços em branco, como tabulações (`'\t'` ) ou outros caracteres especiais, definindo o`ListIndentation.Character` propriedade para o caractere desejado.

#### P: É possível personalizar o número de espaços por nível para recuo da lista?
 Sim, você pode personalizar o número de espaços por nível para recuo da lista alterando o valor do`ListIndentation.Count` propriedade no`TxtSaveOptions` aula. Você pode especificar o número de espaços desejados para cada nível de recuo.

#### P: Que outros recursos o Aspose.Words oferece para gerenciamento de listas?
Aspose.Words oferece muitos recursos para gerenciar listas em documentos do Word. Você pode criar listas numeradas ou com marcadores, definir níveis de recuo, personalizar o estilo das listas, adicionar itens de lista e muito mais.