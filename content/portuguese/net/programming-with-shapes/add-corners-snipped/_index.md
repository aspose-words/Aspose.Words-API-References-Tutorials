---
title: Adicionar cantos cortados
linktitle: Adicionar cantos cortados
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar uma forma de cantos recortados aos seus documentos do Word usando o Aspose.Words para .NET. Este guia passo a passo garante que você possa aprimorar seus documentos facilmente.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/add-corners-snipped/
---
## Introdução

Adicionar formas personalizadas aos seus documentos do Word pode ser uma maneira divertida e visualmente atraente de destacar informações importantes ou adicionar um pouco de estilo ao seu conteúdo. Neste tutorial, vamos nos aprofundar em como você pode inserir formas "Corners Snipped" em seus documentos do Word usando o Aspose.Words para .NET. Este guia o guiará por cada etapa, garantindo que você possa adicionar essas formas sem esforço e personalizar seus documentos como um profissional.

## Pré-requisitos

Antes de começarmos o código, vamos garantir que você tenha tudo o que precisa para começar:

1.  Aspose.Words para .NET: Se ainda não o fez, baixe a versão mais recente do[Página de lançamentos da Aspose](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: Configure seu ambiente de desenvolvimento. O Visual Studio é uma escolha popular, mas você pode usar qualquer IDE que suporte .NET.
3.  Licença: Se você estiver apenas experimentando, pode usar uma[teste gratuito](https://releases.aspose.com/) ou pegue um[licença temporária](https://purchase.aspose.com/temporary-license/) para desbloquear a funcionalidade completa.
4. Noções básicas de C#: A familiaridade com a programação em C# ajudará você a acompanhar os exemplos.

## Importar namespaces

Antes de começarmos a trabalhar com Aspose.Words para .NET, precisamos importar os namespaces necessários. Adicione estes no topo do seu arquivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Agora, vamos dividir o processo de adicionar uma forma "Corners Snipped" em várias etapas. Siga estas etapas de perto para garantir que tudo funcione perfeitamente.

## Etapa 1: inicializar o documento e o DocumentBuilder

 A primeira coisa que precisamos fazer é criar um novo documento e inicializar um`DocumentBuilder` objeto. Este construtor nos ajudará a adicionar conteúdo ao nosso documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Nesta etapa, configuramos nosso documento e construtor. Pense no`DocumentBuilder` como sua caneta digital, pronta para escrever e desenhar em seu documento do Word.

## Etapa 2: Insira a forma cortada nos cantos

 A seguir, usaremos o`DocumentBuilder` para inserir uma forma "Corners Snipped". Esse tipo de forma é predefinido no Aspose.Words e pode ser facilmente inserido com uma única linha de código.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

Aqui, estamos especificando o tipo de forma e suas dimensões (50x50). Imagine que você está colocando um pequeno adesivo de canto perfeitamente cortado em seu documento. 

## Etapa 3: Defina opções de salvamento com conformidade

Antes de salvar nosso documento, precisamos definir as opções de salvamento para garantir que nosso documento esteja em conformidade com padrões específicos. Usaremos o`OoxmlSaveOptions` classe para isso.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
```

Essas opções de salvamento garantem que nosso documento esteja de acordo com o padrão ISO/IEC 29500:2008, o que é crucial para a compatibilidade e a longevidade do documento.

## Etapa 4: Salve o documento

Por fim, salvamos nosso documento no diretório especificado usando as opções de salvamento que definimos anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

E assim, seu documento agora contém um formato personalizado "Cortes Cortados", salvo com as opções de conformidade necessárias.

## Conclusão

Pronto! Adicionar formas personalizadas aos seus documentos do Word usando o Aspose.Words para .NET é simples e pode melhorar muito o apelo visual dos seus documentos. Seguindo essas etapas, você pode facilmente inserir uma forma "Corners Snipped" e garantir que seu documento atenda aos padrões exigidos. Boa codificação!

## Perguntas frequentes

### Posso personalizar o tamanho do formato "Cortes Cortados"?
Sim, você pode ajustar o tamanho alterando as dimensões no`InsertShape` método.

### É possível adicionar outros tipos de formas?
 Absolutamente! Aspose.Words suporta várias formas. Basta alterar o`ShapeType` para o formato desejado.

### Preciso de uma licença para usar o Aspose.Words?
Embora você possa usar uma avaliação gratuita ou uma licença temporária, uma licença completa é necessária para uso irrestrito.

### Como posso estilizar ainda mais as formas?
Você pode usar propriedades e métodos adicionais fornecidos pelo Aspose.Words para personalizar a aparência e o comportamento das formas.

### O Aspose.Words é compatível com outros formatos?
Sim, o Aspose.Words suporta vários formatos de documento, incluindo DOCX, PDF, HTML e muito mais.