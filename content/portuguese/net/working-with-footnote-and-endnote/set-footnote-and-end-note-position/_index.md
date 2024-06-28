---
title: Definir a posição da nota de rodapé e da nota final
linktitle: Definir a posição da nota de rodapé e da nota final
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir a posição das notas de rodapé e notas finais em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como usar Aspose.Words for .NET para definir a posição das notas de rodapé e notas finais em um documento do Word. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Caso ainda não tenha feito isso, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: inicializando o objeto Documento

 Primeiro, inicialize o`Document` objeto fornecendo o caminho para seu documento de origem:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Etapa 2: definir a posição da nota de rodapé e da nota final

 A seguir, acesse o`FootnoteOptions` e`EndnoteOptions`propriedades do documento para definir a posição das notas de rodapé e notas finais. Neste exemplo, definimos a posição das notas de rodapé abaixo do texto e a posição das notas finais no final da seção:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Etapa 3: salvando o documento

Por fim, salve o documento modificado:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

É isso! Você definiu com sucesso a posição das notas de rodapé e notas finais em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para definir posição de nota de rodapé e nota final usando Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso posicionar notas de rodapé e notas finais no Aspose.Words?

 R: Para posicionar notas de rodapé e notas finais no Aspose.Words, você precisa usar o`FootnoteOptions` classe e o`Position` propriedade. Você pode definir esta propriedade para qualquer valor desejado, como`BottomOfPage` (no final da página) ou`EndOfSection` (no final da seção).

#### P: É possível personalizar a posição das notas de rodapé e de fim de cada página ou seção do documento?

R: Sim, é possível personalizar a posição das notas de rodapé e de fim de cada página ou seção do documento. Você pode usar a seção Aspose.Words e métodos de manipulação de página para definir posições específicas para notas de rodapé e notas finais.

#### P: Como removo notas de rodapé ou finais de um documento?

 R: Para remover notas de rodapé ou finais de um documento no Aspose.Words, você pode usar métodos apropriados, como`RemoveAllFootnotes` para remover todas as notas de rodapé ou`RemoveAllEndnotes` para remover todas as notas finais. Certifique-se de salvar o documento após realizar essas operações.

#### P: As notas de rodapé e de fim podem ser posicionadas fora das margens da página?

Não, por padrão, notas de rodapé e notas finais não podem ser posicionadas fora das margens da página no Aspose.Words. No entanto, você pode ajustar as margens do documento para permitir mais espaço para notas de rodapé e finais, se necessário.

#### P: As notas de rodapé e de fim podem ser personalizadas com fontes específicas ou estilos de formatação?

R: Sim, você pode personalizar notas de rodapé e notas finais com fontes específicas ou estilos de formatação no Aspose.Words. Você pode usar os métodos e propriedades disponíveis para aplicar estilos de fonte, cores, tamanhos de fonte, etc., notas de rodapé e notas finais.