---
title: Definir marca de ênfase da fonte
linktitle: Definir marca de ênfase da fonte
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir o estilo de ênfase da fonte em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-font-emphasis-mark/
---

Neste tutorial, mostraremos como definir o estilo de ênfase da fonte em um documento do Word usando Aspose.Words for .NET. A ênfase da fonte é usada para destacar certas palavras ou frases no texto.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto

## Passo 1: Defina o diretório do documento
 Comece definindo o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Crie e personalize o documento
 Crie uma instância do`Document` classe e um associado`DocumentBuilder` para construir o conteúdo do documento. Use o`Font.EmphasisMark` propriedade para definir o estilo de ênfase da fonte como`EmphasisMark.UnderSolidCircle` . Então use o`Write` e`Writeln` métodos do`DocumentBuilder` para adicionar texto com a ênfase de fonte especificada.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Etapa 3: salve o documento
 Salve o documento usando o`Save` método do`Document` com o caminho e nome de arquivo apropriados.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Exemplo de código-fonte para definir marca de ênfase da fonte usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusão
Neste tutorial, você aprendeu como definir o estilo de ênfase da fonte em um documento do Word usando Aspose.Words for .NET. Experimente diferentes estilos de ênfase e use esse recurso para destacar palavras ou frases em seus documentos.

### Perguntas frequentes

#### P: Como posso adicionar acentos a uma fonte específica em um documento do Word usando Aspose.Words?

R: Para adicionar acentos a uma fonte específica em um documento do Word usando Aspose.Words, você pode usar a API para navegar até a fonte desejada e aplicar os acentos apropriados. Isso adicionará acentos ao texto com a fonte selecionada.

#### P: É possível alterar o estilo dos acentos em um documento do Word com Aspose.Words?

R: Sim, com Aspose.Words você pode alterar o estilo dos acentos em um documento do Word. A API permite ajustar propriedades de estilo, como cor, tamanho, tipo de linha, etc., para personalizar a aparência dos acentos.

#### P: Como posso remover todos os acentos de um documento do Word usando Aspose.Words?

R: Para remover todos os acentos de um documento do Word usando Aspose.Words, você pode usar a API para navegar no documento, detectar os acentos existentes e removê-los usando os métodos apropriados. Isso removerá todas as marcas de ênfase do documento.

#### P: Posso adicionar acentos a uma parte específica do texto em um documento do Word?

R: Sim, você pode adicionar acentos a uma parte específica do texto em um documento do Word usando Aspose.Words. Você pode selecionar o intervalo de texto desejado usando a API e adicionar marcas de ênfase apropriadas a essa parte do texto.

#### P: Os acentos podem ser personalizados de acordo com minhas necessidades?

R: Sim, os acentos podem ser personalizados de acordo com suas necessidades usando Aspose.Words. Você pode ajustar as propriedades de estilo dos acentos, como cor, tamanho, tipo de linha e muito mais, para corresponder às suas preferências de formatação.