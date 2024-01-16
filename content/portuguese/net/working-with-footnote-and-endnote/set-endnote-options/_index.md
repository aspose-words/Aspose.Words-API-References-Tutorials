---
title: Definir opções de nota final
linktitle: Definir opções de nota final
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir opções de notas finais em documentos do Word usando Aspose.Words for .NET. Tutorial passo a passo com exemplo de código-fonte.
type: docs
weight: 10
url: /pt/net/working-with-footnote-and-endnote/set-endnote-options/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como usar Aspose.Words for .NET para definir opções de notas finais em um documento do Word. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Caso ainda não tenha feito isso, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: inicializando o objeto Documento

 Primeiro, inicialize o`Document` objeto fornecendo o caminho para seu documento de origem:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Etapa 2: inicializando o objeto DocumentBuilder

 A seguir, inicialize o`DocumentBuilder` objeto para realizar operações no documento:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: adicionar texto e nota final

 Use o`Write` método do`DocumentBuilder` objeto para adicionar texto ao documento e o`InsertFootnote` método para inserir uma nota final:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Etapa 4: definir opções de notas finais

 Acesse o`EndnoteOptions` propriedade do documento para modificar as opções de nota final. Neste exemplo, definimos a regra de reinicialização para reiniciar em cada página e a posição no final da seção:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Etapa 5: salvando o documento

Por fim, salve o documento modificado:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

É isso! Você definiu com êxito as opções de nota final em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para definir opções de nota final usando Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso estilizar notas finais no Aspose.Words?

 R: Para estilizar notas finais em Aspose.Words, você pode usar o`EndnoteOptions` classe e o`SeparatorNoteTextStyle` propriedade. Você pode especificar o estilo da fonte, tamanho, cor, etc. para notas finais usando esta propriedade.

#### P: É possível personalizar a numeração das notas finais de um documento?

 R: Sim, é possível personalizar a numeração das notas finais de um documento. Você pode usar o`RestartRule` e`NumberStyle` propriedades do`EndnoteOptions` classe para definir regras de reinicialização e estilos de numeração específicos.

#### P: Como posso posicionar notas finais em um documento?

 R: Para posicionar notas finais em um documento, você pode usar o`Position` propriedade do`EndnoteOptions` aula. Você pode especificar se as notas finais devem ser colocadas na parte inferior de cada página, no final de cada seção ou no final do documento.

#### P: Posso personalizar o formato de numeração das notas finais?

 R: Sim, você pode personalizar o formato da numeração das notas finais no Aspose.Words. Use o`NumberFormat` propriedade do`EndnoteOptions` class para definir o formato desejado, como algarismos arábicos, algarismos romanos, letras, etc.

#### P: É possível continuar a numeração das notas finais entre as seções de um documento?

 R: Sim, é possível continuar a numeração das notas finais entre as seções de um documento. Use o`RestartRule` propriedade do`EndnoteOptions` classe e configurá-lo para`RestartContinuous` para permitir que a numeração continue entre as seções.