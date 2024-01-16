---
title: Verifique o efeito de texto do DrawingML
linktitle: Verifique o efeito de texto do DrawingML
second_title: API de processamento de documentos Aspose.Words
description: Neste tutorial, aprenda como verificar os efeitos de texto do DrawingML em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/check-drawingml-text-effect/
---

Neste tutorial, orientaremos você sobre como verificar os efeitos de texto do DrawingML em um documento do Word usando a Biblioteca Aspose.Words para .NET. A verificação dos efeitos de texto do DrawingML permite determinar se um efeito específico é aplicado a parte do texto. Iremos guiá-lo passo a passo para ajudá-lo a entender e implementar o código em seu projeto .NET.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto
- Um documento do Word contendo efeitos de texto do DrawingML

## Passo 1: Defina o diretório do documento
 Primeiro, você precisa definir o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento e verifique os efeitos do texto
A seguir, carregaremos o documento Word e acessaremos a coleção de execuções (sequências de caracteres) no primeiro parágrafo do corpo do documento. A seguir, verificaremos se algum efeito de texto específico do DrawingML foi aplicado à fonte da primeira execução.

```csharp
// Carregue o documento
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Verifique os efeitos de texto do DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Exemplo de código-fonte para Check DMLText Effect usando Aspose.Words for .NET 

```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Uma execução pode ter vários efeitos de texto Dml aplicados.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Conclusão
Neste tutorial, vimos como verificar os efeitos de texto do DrawingML em um documento do Word usando Aspose.Words for .NET. A verificação dos efeitos de texto do DrawingML permite identificar partes do texto que possuem efeitos específicos aplicados. Sinta-se à vontade para usar este recurso para manipular e analisar efeitos de texto em seus documentos do Word.

### Perguntas frequentes

#### P: Como posso acessar os efeitos de texto do DrawingML em um documento do Word usando Aspose.Words?

R: Com Aspose.Words, você pode acessar efeitos de texto DrawingML em um documento do Word usando a API fornecida. Você pode navegar pelos elementos do texto e verificar propriedades específicas dos efeitos do texto, como cor, tamanho, etc.

#### P: Que tipos de efeitos de texto do DrawingML são comumente usados em documentos do Word?

R: Os tipos de efeitos de texto do DrawingML comumente usados em documentos do Word incluem sombras, reflexos, brilhos, gradientes, etc. Esses efeitos podem ser aplicados para melhorar a aparência e a formatação do texto.

#### P: Como posso verificar a cor de um efeito de texto do DrawingML em um documento do Word?

R: Para verificar a cor de um efeito de texto DrawingML em um documento do Word, você pode usar os métodos fornecidos por Aspose.Words para acessar as propriedades de cor do efeito de texto. Desta forma você pode obter a cor usada para o efeito de texto específico.

#### P: É possível verificar efeitos de texto em documentos Word contendo múltiplas seções?

R: Sim, Aspose.Words permite verificar efeitos de texto em documentos Word contendo múltiplas seções. Você pode navegar por cada seção do documento e acessar os efeitos de texto de cada seção individualmente.

#### P: Como posso verificar a opacidade de um efeito de texto do DrawingML em um documento do Word?

R: Para verificar a opacidade de um efeito de texto DrawingML em um documento do Word, você pode usar os métodos fornecidos por Aspose.Words para acessar as propriedades de opacidade do efeito de texto. Isso permitirá que você obtenha o valor de opacidade aplicado ao efeito de texto específico.