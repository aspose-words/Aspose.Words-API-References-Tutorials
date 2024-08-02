---
title: Adicionar forma de grupo
linktitle: Adicionar forma de grupo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar formas de grupo a documentos do Word usando Aspose.Words for .NET com este tutorial passo a passo abrangente.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/add-group-shape/
---
## Introdução

Criar documentos complexos com elementos visuais ricos às vezes pode ser uma tarefa difícil, especialmente quando se trata de formas de grupo. Mas não tema! Aspose.Words for .NET simplifica esse processo, tornando-o muito fácil. Neste tutorial, orientaremos você nas etapas para adicionar formas de grupo aos seus documentos do Word. Pronto para mergulhar? Vamos começar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Aspose.Words for .NET: Você pode baixá-lo no[Página de lançamentos do Aspose](https://releases.aspose.com/words/net/).
2. Ambiente de Desenvolvimento: Visual Studio ou qualquer outro IDE compatível com .NET.
3. Compreensão básica de C#: Familiaridade com programação C# é uma vantagem.

## Importar namespaces

Para começar, precisamos importar os namespaces necessários em nosso projeto. Esses namespaces fornecem acesso às classes e métodos necessários para manipular documentos do Word com Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Etapa 1: inicializar o documento

Primeiramente, vamos inicializar um novo documento do Word. Pense nisso como criar uma tela em branco onde adicionaremos nossas formas de grupo.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Aqui,`EnsureMinimum()` adiciona um conjunto mínimo de nós necessários para o documento.

## Etapa 2: Crie o objeto GroupShape

 A seguir, precisamos criar um`GroupShape`objeto. Este objeto servirá de recipiente para outras formas, permitindo-nos agrupá-las.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Etapa 3: adicionar formas ao GroupShape

 Agora, vamos adicionar formas individuais ao nosso`GroupShape` recipiente. Começaremos com uma forma de borda acentuada e, em seguida, adicionaremos uma forma de botão de ação.

### Adicionando uma forma de borda acentuada

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Este trecho de código cria uma forma de borda acentuada com largura e altura de 100 unidades e a adiciona ao`GroupShape`.

### Adicionando um formato de botão de ação

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Aqui, criamos um formato de botão de ação, posicionamo-lo e adicionamos ao nosso`GroupShape`.

## Etapa 4: definir as dimensões do GroupShape

 Para garantir que nossas formas se encaixem bem no grupo, precisamos definir as dimensões do`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Isso define a largura e a altura do`GroupShape` como 200 unidades e define o tamanho da coordenada de acordo.

## Etapa 5: insira o GroupShape no documento

 Agora, vamos inserir nosso`GroupShape` no documento usando`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` fornece uma maneira fácil de adicionar nós, incluindo formas, ao documento.

## Etapa 6: salve o documento

Finalmente, salve o documento no diretório especificado.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

aí está! Seu documento com formas de grupo está pronto.

## Conclusão

Adicionar formas de grupo aos seus documentos do Word não precisa ser um processo complicado. Com Aspose.Words for .NET, você pode criar e manipular formas com facilidade, tornando seus documentos mais atraentes visualmente e funcionais. Siga as etapas descritas neste tutorial e você se tornará um profissional rapidamente!

## Perguntas frequentes

### Posso adicionar mais de duas formas a um GroupShape?
 Sim, você pode adicionar quantas formas precisar em um`GroupShape` . Basta usar o`AppendChild` método para cada forma.

### É possível estilizar as formas dentro de um GroupShape?
 Absolutamente! Cada forma pode ser estilizada individualmente usando as propriedades disponíveis no`Shape` aula.

### Como posiciono o GroupShape dentro do documento?
 Você pode posicionar o`GroupShape` definindo seu`Left`e`Top` propriedades.

### Posso adicionar texto às formas dentro do GroupShape?
 Sim, você pode adicionar texto a formas usando o`AppendChild` método para adicionar um`Paragraph` contendo`Run` nós com texto.

### É possível agrupar formas dinamicamente com base na entrada do usuário?
Sim, você pode criar e agrupar formas dinamicamente com base na entrada do usuário, ajustando as propriedades e os métodos de acordo.