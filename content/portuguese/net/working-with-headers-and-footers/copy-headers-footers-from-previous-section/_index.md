---
title: Copiar cabeçalhos e rodapés da seção anterior
linktitle: Copiar cabeçalhos e rodapés da seção anterior
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como copiar cabeçalhos e rodapés da seção anterior em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como copiar cabeçalhos e rodapés da seção anterior em um documento do Word usando Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Caso ainda não tenha feito isso, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: acessando a seção anterior

 Primeiro, recupere a seção anterior acessando o`PreviousSibling` propriedade da seção atual:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Etapa 2: verificação da seção anterior

A seguir, verifique se existe uma seção anterior. Se não houver seção anterior, simplesmente retornamos:

```csharp
if (previousSection == null)
    return;
```

## Etapa 3: limpar e copiar cabeçalhos e rodapés

Para copiar os cabeçalhos e rodapés da seção anterior para a seção atual, limpamos os cabeçalhos e rodapés existentes na seção atual e, em seguida, iteramos pelos cabeçalhos e rodapés da seção anterior para adicionar cópias clonadas à seção atual:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Etapa 4: salvando o documento

Por fim, salve o documento modificado:

```csharp
doc.Save("OutputDocument.docx");
```

É isso! Você copiou com êxito cabeçalhos e rodapés da seção anterior para a seção atual em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para copiar cabeçalhos e rodapés da seção anterior usando Aspose.Words for .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso copiar os cabeçalhos e rodapés da seção anterior para o Aspose.Words?

 R: Para copiar cabeçalhos e rodapés da seção anterior para Aspose.Words, você pode usar o`CopyHeadersFootersFromPreviousSection()` método na corrente`Section`objeto. Isso copiará os cabeçalhos e rodapés da seção anterior para a seção atual.

#### P: É possível copiar apenas o cabeçalho ou rodapé da seção anterior no Aspose.Words?

 R: Sim, é possível copiar apenas o cabeçalho ou rodapé da seção anterior em Aspose.Words. Para isso, você pode usar o`CopyHeaderFromPreviousSection()` e`CopyFooterFromPreviousSection()` métodos na corrente`Section` objeto para copiar especificamente o cabeçalho ou rodapé da seção anterior para a seção atual.

#### P: A cópia de cabeçalhos e rodapés da seção anterior substitui os cabeçalhos e rodapés existentes na seção atual?

R: Sim, copiar cabeçalhos e rodapés da seção anterior substitui os cabeçalhos e rodapés existentes na seção atual. Se quiser manter os cabeçalhos e rodapés existentes e adicioná-los aos cabeçalhos e rodapés copiados, você precisará realizar uma operação adicional para mesclar o conteúdo.

#### P: Como posso verificar se uma seção tem um cabeçalho ou rodapé da seção anterior em Aspose.Words?

R: Para verificar se uma seção possui um cabeçalho ou rodapé da seção anterior no Aspose.Words, você pode usar o`HasHeader` e`HasFooter` propriedades no`Section` objeto para determinar se o cabeçalho ou rodapé do cabeçalho está presente. Se`HasHeader` ou`HasFooter` retorna`false`, significa que não há cabeçalho ou rodapé da seção anterior nesta seção.