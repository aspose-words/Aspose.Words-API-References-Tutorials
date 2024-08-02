---
title: Adicionar marcas Bidi em documento do Word
linktitle: Adicionar marcas Bidi em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar marcas bidirecionais (Bidi) em documentos do Word usando Aspose.Words for .NET com este guia. Garanta a direção adequada do texto para conteúdo multilíngue.
type: docs
weight: 10
url: /pt/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## Introdução

No mundo do processamento de documentos, o texto bidirecional (Bidi) muitas vezes pode ser um pouco complicado de gerenciar. Isto é especialmente verdadeiro quando se trata de idiomas que possuem diferentes direções de texto, como árabe ou hebraico. Felizmente, o Aspose.Words for .NET facilita o tratamento de tais cenários. Neste tutorial, veremos como adicionar marcas Bidi a um documento do Word usando Aspose.Words for .NET.

## Pré-requisitos

Antes de mergulharmos no código, certifique-se de ter o seguinte:

1.  Aspose.Words for .NET: Você precisa ter o Aspose.Words for .NET instalado. Você pode baixá-lo no[Página de downloads do Aspose](https://releases.aspose.com/words/net/).
2. .NET Framework ou .NET Core: certifique-se de ter um ambiente .NET compatível configurado para executar os exemplos.
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# e operações básicas em .NET.

## Importar namespaces

Para começar, você precisa importar os namespaces necessários. Veja como você pode incluí-los em seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Vamos dividir o processo de adição de marcas Bidi em um documento do Word em etapas claras. Cada etapa irá guiá-lo através do código e sua finalidade.

## Etapa 1: configure seu documento

 Comece criando uma nova instância do`Document` aula e um`DocumentBuilder` para adicionar conteúdo ao documento.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e adicione conteúdo
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Nesta etapa, você inicializa um novo documento do Word e configura um`DocumentBuilder` para facilitar a inserção de conteúdo.

## Etapa 2: adicione conteúdo ao seu documento

Em seguida, adicione algum texto ao seu documento. Aqui, adicionaremos texto em diferentes idiomas para ilustrar o tratamento de texto Bidi.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Aqui, primeiro adicionamos uma frase padrão em inglês. Em seguida, habilitamos a formatação de texto Bidi para o texto subsequente, que é escrito em hebraico e árabe. Isso demonstra como incorporar texto bidirecional.

## Etapa 3: configurar opções de salvamento para marcas Bidi

 Para garantir que as marcas Bidi sejam salvas corretamente no documento, é necessário configurar o`TxtSaveOptions` e habilitar o`AddBidiMarks` opção.

```csharp
// Adicionar marcas Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 Nesta etapa, criamos uma instância de`TxtSaveOptions` e definir o`AddBidiMarks`propriedade para`true`. Isto garante que as marcas Bidi sejam incluídas ao salvar o documento como um arquivo de texto.

## Conclusão

Adicionar marcas Bidi aos seus documentos do Word pode ser uma etapa crucial ao lidar com conteúdo multilíngue que inclui idiomas com diferentes direções de texto. Com Aspose.Words for .NET, esse processo é direto e eficiente. Seguindo as etapas descritas acima, você pode garantir que seus documentos representem corretamente o texto Bidi, melhorando a legibilidade e a precisão.

## Perguntas frequentes

### O que são marcas Bidi e por que são importantes?
Marcas Bidi são caracteres especiais usados para controlar a direção do texto em documentos. Eles são essenciais para exibir corretamente idiomas lidos da direita para a esquerda, como árabe e hebraico.

### Posso usar o Aspose.Words for .NET para lidar com outros tipos de problemas de direção de texto?
Sim, Aspose.Words for .NET fornece suporte abrangente para várias necessidades de direção e formatação de texto, incluindo idiomas da direita para a esquerda e da esquerda para a direita.

### É possível aplicar a formatação Bidi apenas a partes específicas de um documento?
Sim, você pode aplicar a formatação Bidi a parágrafos ou seções específicas do seu documento, conforme necessário.

### Em quais formatos posso salvar o documento com marcas Bidi?
No exemplo fornecido, o documento é salvo como um arquivo de texto. No entanto, Aspose.Words também suporta salvar documentos em vários formatos, preservando as marcas Bidi.

### Onde posso encontrar mais informações sobre o Aspose.Words for .NET?
 Você pode explorar mais sobre o Aspose.Words for .NET através do[Aspor Documentação](https://reference.aspose.com/words/net/) e acesse o[Fórum de suporte](https://forum.aspose.com/c/words/8) para obter ajuda adicional.