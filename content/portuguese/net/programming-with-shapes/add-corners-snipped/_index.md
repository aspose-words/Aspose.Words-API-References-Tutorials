---
title: Adicionar cantos recortados
linktitle: Adicionar cantos recortados
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar uma forma de cantos recortados aos seus documentos do Word usando Aspose.Words for .NET. Este guia passo a passo garante que você possa aprimorar seus documentos facilmente.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/add-corners-snipped/
---
## Introdução

Adicionar formas personalizadas aos seus documentos do Word pode ser uma maneira divertida e visualmente atraente de destacar informações importantes ou adicionar um toque especial ao seu conteúdo. Neste tutorial, vamos nos aprofundar em como você pode inserir formas "Corners Snipped" em seus documentos do Word usando Aspose.Words for .NET. Este guia orientará você em cada etapa, garantindo que você possa adicionar essas formas sem esforço e personalizar seus documentos como um profissional.

## Pré-requisitos

Antes de entrarmos no código, vamos ter certeza de que você tem tudo o que precisa para começar:

1.  Aspose.Words for .NET: Se ainda não o fez, baixe a versão mais recente no[Página de lançamentos do Aspose](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento. O Visual Studio é uma escolha popular, mas você pode usar qualquer IDE que suporte .NET.
3.  Licença: Se você está apenas experimentando, você pode usar um[teste gratuito](https://releases.aspose.com/) ou obter um[licença temporária](https://purchase.aspose.com/temporary-license/) para desbloquear todas as funcionalidades.
4. Compreensão básica de C#: A familiaridade com a programação C# o ajudará a acompanhar os exemplos.

## Importar namespaces

Antes de começarmos a trabalhar com Aspose.Words for .NET, precisamos importar os namespaces necessários. Adicione-os no topo do seu arquivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Agora, vamos dividir o processo de adição de uma forma "Cantos recortados" em várias etapas. Siga estas etapas atentamente para garantir que tudo funcione perfeitamente.

## Etapa 1: inicializar o documento e o DocumentBuilder

 A primeira coisa que precisamos fazer é criar um novo documento e inicializar um`DocumentBuilder` objeto. Este construtor nos ajudará a adicionar conteúdo ao nosso documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Nesta etapa, configuramos nosso documento e construtor. Pense no`DocumentBuilder` como sua caneta digital, pronta para escrever e desenhar em seu documento Word.

## Etapa 2: insira a forma recortada dos cantos

 A seguir, usaremos o`DocumentBuilder` para inserir uma forma de "Cantos Recortados". Este tipo de forma é predefinido em Aspose.Words e pode ser facilmente inserido com uma única linha de código.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

Aqui especificamos o tipo de forma e suas dimensões (50x50). Imagine que você está colocando um adesivo de canto pequeno e perfeitamente recortado em seu documento. 

## Etapa 3: Definir opções de salvamento com conformidade

Antes de salvar nosso documento, precisamos definir as opções de salvamento para garantir que nosso documento esteja em conformidade com padrões específicos. Usaremos o`OoxmlSaveOptions` aula para isso.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
```

Essas opções de salvamento garantem que nosso documento esteja em conformidade com o padrão ISO/IEC 29500:2008, o que é crucial para a compatibilidade e longevidade do documento.

## Etapa 4: salve o documento

Finalmente, salvamos nosso documento no diretório especificado usando as opções de salvamento que definimos anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

E assim, seu documento agora contém uma forma personalizada de “Cantos Recortados”, salva com as opções de conformidade necessárias.

## Conclusão

Aí está! Adicionar formas personalizadas aos seus documentos do Word usando Aspose.Words for .NET é simples e pode melhorar muito o apelo visual dos seus documentos. Seguindo essas etapas, você pode inserir facilmente uma forma de “Cantos Recortados” e garantir que seu documento atenda aos padrões exigidos. Boa codificação!

## Perguntas frequentes

### Posso personalizar o tamanho da forma "Cantos Recortados"?
Sim, você pode ajustar o tamanho alterando as dimensões no`InsertShape` método.

### É possível adicionar outros tipos de formas?
 Absolutamente! Aspose.Words suporta várias formas. Basta mudar o`ShapeType` na forma desejada.

### Preciso de uma licença para usar o Aspose.Words?
Embora você possa usar uma avaliação gratuita ou uma licença temporária, é necessária uma licença completa para uso irrestrito.

### Como posso estilizar ainda mais as formas?
Você pode usar propriedades e métodos adicionais fornecidos por Aspose.Words para personalizar a aparência e o comportamento das formas.

### O Aspose.Words é compatível com outros formatos?
Sim, Aspose.Words suporta vários formatos de documentos, incluindo DOCX, PDF, HTML e muito mais.