---
title: Definir configurações de substituição de fonte
linktitle: Definir configurações de substituição de fonte
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir as configurações de fallback de fonte em Aspose.Words for .NET. Este guia completo garante que todos os caracteres dos seus documentos sejam exibidos corretamente.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-font-fallback-settings/
---

Ao trabalhar com documentos que contêm diversos elementos de texto, como idiomas diferentes ou caracteres especiais, é crucial garantir que esses elementos sejam exibidos corretamente. Aspose.Words for .NET oferece um recurso poderoso chamado Font Fallback Settings, que ajuda a definir regras para substituição de fontes quando a fonte original não suporta determinados caracteres. Neste guia, exploraremos como definir as configurações de fallback de fonte usando Aspose.Words for .NET em um tutorial passo a passo.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

- Conhecimento básico de C#: Familiaridade com a linguagem de programação C# e o framework .NET.
-  Aspose.Words for .NET: Baixe e instale a partir do[Link para Download](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: uma configuração como o Visual Studio para escrever e executar seu código.
-  Documento de amostra: tenha um documento de amostra (por exemplo,`Rendering.docx`) pronto para teste.
- XML de regras de fallback de fonte: prepare um arquivo XML definindo as regras de fallback de fonte.

## Importar namespaces

Para usar Aspose.Words, você precisa importar os namespaces necessários. Isso permite o acesso a diversas classes e métodos necessários para o processamento de documentos.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Etapa 1: definir o diretório de documentos

Primeiro, defina o diretório onde seu documento está armazenado. Isso é essencial para localizar e processar seu documento.

```csharp
// O caminho para o diretório de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregue o documento

 Carregue seu documento em um Aspose.Words`Document` objeto. Esta etapa permite trabalhar com o documento de forma programática.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: definir as configurações de fonte

 Crie um novo`FontSettings` objeto e carregue as configurações de fallback de fonte de um arquivo XML. Este arquivo XML contém as regras para substituição de fontes.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Etapa 4: aplicar configurações de fonte ao documento

 Atribuir o configurado`FontSettings` ao documento. Isso garante que as regras de substituição de fonte sejam aplicadas ao renderizar o documento.

```csharp
doc.FontSettings = fontSettings;
```

## Etapa 5: salve o documento

Por fim, salve o documento. As configurações de fonte alternativa serão usadas durante a operação de salvamento para garantir a substituição adequada da fonte.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Arquivo XML: regras de substituição de fontes

Aqui está um exemplo de como deve ser a aparência do seu arquivo XML que define as regras de fallback de fonte:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Conclusão

Seguindo essas etapas, você pode configurar e usar com eficácia as configurações de fallback de fonte no Aspose.Words for .NET. Isso garante que seus documentos exibam todos os caracteres corretamente, mesmo que a fonte original não suporte determinados caracteres. A implementação dessas configurações melhorará muito a qualidade e a legibilidade dos seus documentos.

## Perguntas frequentes

### P1: O que é substituto de fonte?

Font Fallback é um recurso que permite a substituição de fontes quando a fonte original não suporta determinados caracteres, garantindo a exibição adequada de todos os elementos do texto.

### P2: Posso especificar várias fontes substitutas?

Sim, você pode especificar várias fontes substitutas nas regras XML. Aspose.Words verificará cada fonte na ordem especificada até encontrar uma que suporte o caractere.

### Q3: Onde posso baixar o Aspose.Words para .NET?

 Você pode baixá-lo no[Aspose página de download](https://releases.aspose.com/words/net/).

### P4: Como posso criar o arquivo XML para regras de substituição de fontes?

O arquivo XML pode ser criado usando qualquer editor de texto. Deve seguir a estrutura mostrada no exemplo fornecido neste tutorial.

### Q5: Existe suporte disponível para Aspose.Words?

 Sim, você pode encontrar suporte no[Fórum de suporte Aspose.Words](https://forum.aspose.com/c/words/8).