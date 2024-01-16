---
title: Tachado
linktitle: Tachado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como aplicar o estilo de texto tachado com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/strikethrough/
---


Neste exemplo, orientaremos você sobre como aplicar o estilo de texto tachado usando Aspose.Words for .NET. O texto tachado é usado para indicar que o texto foi excluído ou não é mais válido.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: aplicar estilo de texto tachado

Habilitaremos o estilo de texto tachado definindo o`StrikeThrough` propriedade do`Font` opor-se a`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Etapa 3: adicionar texto tachado

 Agora podemos adicionar texto tachado usando o gerador de documentos`Writeln` método.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Exemplo de código-fonte para texto tachado com Aspose.Words for .NET

```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Faça o texto tachado.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Parabéns! Agora você aprendeu como aplicar o estilo de texto tachado com Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como posso adicionar texto tachado em Aspose.Words?

 R: Para adicionar texto tachado em Aspose.Words, você pode usar o`Font.StrikeThrough` propriedade do`Run` objeto. Você pode definir esta propriedade como`true` para adicionar texto tachado a um texto específico. Por exemplo, você pode usar`run.Font.StrikeThrough=true` para adicionar o texto tachado ao`Run` objeto.

#### P: É possível adicionar texto tachado a vários trechos de texto no mesmo parágrafo?

 R: Sim, você pode adicionar texto tachado a várias partes do texto em um único parágrafo usando vários`Run` objetos. Você pode criar vários`Run` objetos e definir o`Font.StrikeThrough`propriedade para`true` para cada objeto para adicionar o texto tachado às partes de texto desejadas. Então você pode adicioná-los ao parágrafo usando o`Paragraph.AppendChild(run)` método.

#### P: Posso adicionar texto tachado ao texto que está em uma tabela ou célula no Aspose.Words?

 R: Sim, você pode adicionar texto tachado ao texto que está em uma tabela ou célula no Aspose.Words. Você pode pular para a célula ou parágrafo desejado usando os métodos apropriados e, em seguida, aplicar a formatação de texto tachado usando o`Font.StrikeThrough` propriedade do`Run` ou`Paragraph` objeto.