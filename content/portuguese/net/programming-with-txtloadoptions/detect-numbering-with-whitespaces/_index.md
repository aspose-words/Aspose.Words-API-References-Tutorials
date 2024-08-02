---
title: Detectar numeração com espaços em branco
linktitle: Detectar numeração com espaços em branco
second_title: API de processamento de documentos Aspose.Words
description: Descubra como usar Aspose.Words for .NET para detectar numeração com espaços em branco em documentos de texto simples e garantir que suas listas sejam reconhecidas corretamente.
type: docs
weight: 10
url: /pt/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
## Introdução

Aspose.Words para entusiastas do .NET! Hoje, estamos mergulhando em um recurso fascinante que pode facilitar muito o manuseio de listas em documentos de texto simples. Você já lidou com arquivos de texto onde algumas linhas deveriam ser listas, mas elas simplesmente não parecem corretas quando carregadas em um documento do Word? Bem, temos um truque bacana na manga: detectar numeração com espaços em branco. Este tutorial irá orientá-lo sobre como usar o`DetectNumberingWithWhitespaces` opção no Aspose.Words for .NET para garantir que suas listas sejam reconhecidas corretamente, mesmo quando há espaços em branco entre os números e o texto.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Aspose.Words for .NET: Você pode baixá-lo no[Aspose Lançamentos](https://releases.aspose.com/words/net/) página.
- Ambiente de desenvolvimento: Visual Studio ou qualquer outro IDE C#.
- .NET Framework instalado em sua máquina.
- Conhecimento básico de C#: Compreender o básico o ajudará a acompanhar os exemplos.

## Importar namespaces

Antes de pular para o código, certifique-se de ter os namespaces necessários importados em seu projeto. Aqui está um trecho rápido para você começar:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Loading;
```

Vamos dividir o processo em etapas simples e gerenciáveis. Cada etapa guiará você pelo código necessário e explicará o que está acontecendo.

## Etapa 1: Defina seu diretório de documentos

Primeiramente, vamos configurar o caminho para o diretório do seu documento. É aqui que seus arquivos de entrada e saída serão armazenados.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um documento de texto simples

A seguir, criaremos um documento de texto simples como uma string. Este documento conterá partes que podem ser interpretadas como listas.

```csharp
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";
```

## Etapa 3: configurar LoadOptions

 Para detectar numeração com espaços em branco, precisamos definir o`DetectNumberingWithWhitespaces` opção para`true` em um`TxtLoadOptions` objeto.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

## Etapa 4: carregue o documento

 Agora, vamos carregar o documento usando o`TxtLoadOptions` como parâmetro. Isto garante que a quarta lista (com espaços em branco) seja detectada corretamente.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

## Etapa 5: salve o documento

Finalmente, salve o documento no diretório especificado. Isso gerará um documento do Word com listas detectadas corretamente.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

## Conclusão

aí está! Com apenas algumas linhas de código, você dominou a arte de detectar numeração com espaços em branco em documentos de texto simples usando Aspose.Words for .NET. Esse recurso pode ser extremamente útil ao lidar com vários formatos de texto e garantir que suas listas sejam representadas com precisão em seus documentos do Word. Então, da próxima vez que você encontrar essas listas complicadas, saberá exatamente o que fazer.

## Perguntas frequentes

###  O que é`DetectNumberingWithWhitespaces` in Aspose.Words for .NET?
`DetectNumberingWithWhitespaces` é uma opção em`TxtLoadOptions` isso permite que Aspose.Words reconheça listas mesmo quando há espaços em branco entre a numeração e o texto do item da lista.

### Posso usar esse recurso para outros delimitadores, como marcadores e colchetes?
 Sim, o Aspose.Words detecta automaticamente listas com delimitadores comuns, como marcadores e colchetes. O`DetectNumberingWithWhitespaces` ajuda especificamente com listas que possuem espaços em branco.

###  O que acontece se eu não usar`DetectNumberingWithWhitespaces`?
Sem esta opção, as listas com espaços em branco entre a numeração e o texto poderão não ser reconhecidas como listas e os itens poderão aparecer como parágrafos simples.

### Este recurso está disponível em outros produtos Aspose?
Este recurso específico é adaptado para Aspose.Words for .NET, projetado para lidar com o processamento de documentos Word.

### Como posso obter uma licença temporária do Aspose.Words for .NET?
 Você pode obter uma licença temporária do[Aspose Licença Temporária](https://purchase.aspose.com/temporary-license/) página.

