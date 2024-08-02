---
title: Exportar fontes como base 64
linktitle: Exportar fontes como base 64
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exportar fontes como Base64 usando Aspose.Words for .NET neste tutorial detalhado. Certifique-se de que as fontes estejam incorporadas e exibidas corretamente nos arquivos HTML.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---
## Introdução

Quando se trata de manipular documentos do Word programaticamente, o Aspose.Words for .NET é uma potência. Um de seus recursos interessantes é exportar fontes como Base64 em arquivos HTML, garantindo que as fontes sejam incorporadas e exibidas corretamente em diferentes navegadores e sistemas. Neste tutorial, veremos como você pode conseguir isso. Pronto para tornar as fontes de seus documentos do Word compatíveis com a web? Vamos começar!

## Pré-requisitos

Antes de começarmos a codificação, vamos ter certeza de que você tem tudo o que precisa:

-  Biblioteca Aspose.Words for .NET: você pode baixá-lo do[Aspose Lançamentos](https://releases.aspose.com/words/net/) página.
- Ambiente de desenvolvimento .NET: Qualquer IDE como o Visual Studio funcionará perfeitamente.
- Conhecimento básico de C#: você não precisa ser um profissional, mas um conhecimento básico ajudará.

## Importar namespaces

Para usar o Aspose.Words for .NET, você precisará importar os namespaces necessários em seu código C#. Isso disponibiliza todas as classes e métodos para uso.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: configure seu projeto

Primeiramente, vamos configurar seu projeto e instalar a biblioteca Aspose.Words.

### 1.1 Crie um novo projeto

Abra o Visual Studio e crie um novo projeto de aplicativo de console. Nomeie-o com algo significativo como "ExportFontsBase64".

### 1.2 Instale Aspose.Words

Você pode instalar o Aspose.Words for .NET por meio do NuGet Package Manager:

1. Clique com o botão direito em seu projeto no Solution Explorer.
2. Selecione "Gerenciar pacotes NuGet".
3. Procure por "Aspose.Words" e instale-o.

Alternativamente, você pode executar o seguinte comando no Console do Gerenciador de Pacotes:

```sh
Install-Package Aspose.Words
```

## Etapa 2: carregue seu documento do Word

Agora que seu projeto está configurado, vamos carregar o documento do Word do qual deseja exportar as fontes.

### 2.1 Definir o diretório de documentos

Primeiro, defina o diretório onde seu documento Word está localizado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

### 2.2 Carregar o documento

 Em seguida, carregue seu documento usando o`Document` aula:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Certifique-se de que "Rendering.docx" esteja no diretório especificado.

## Etapa 3: configurar opções de salvamento de HTML

 Para exportar fontes como Base64, precisamos configurar o`HtmlSaveOptions`.


 Crie uma instância de`HtmlSaveOptions` e definir o`ExportFontsAsBase64`propriedade para`true`:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

## Etapa 4: salve o documento como HTML

Por fim, vamos salvar o documento com as opções configuradas.


 Use o`Save` método do`Document` class para salvar seu documento:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Esta linha salvará seu documento como um arquivo HTML com fontes exportadas como Base64, garantindo que sejam incorporadas ao HTML.

## Conclusão

Parabéns! Você exportou com sucesso fontes como Base64 de um documento do Word usando Aspose.Words for .NET. Isso garante que suas fontes sejam preservadas e exibidas corretamente em diferentes plataformas. Esteja você preparando documentos para exibição na web ou simplesmente garantindo a compatibilidade, esse recurso é extremamente útil.

## Perguntas frequentes

### O que é codificação Base64?
Base64 é um método de codificação de dados binários (como fontes) em formato de texto. Isso garante compatibilidade com formatos baseados em texto como HTML.

### Por que devo usar Base64 para fontes em HTML?
O uso de Base64 garante que as fontes sejam incorporadas diretamente no HTML, evitando problemas com arquivos de fontes ausentes e garantindo uma exibição consistente.

### Posso usar este método para outros recursos como imagens?
Absolutamente! Aspose.Words for .NET permite incorporar vários recursos, incluindo imagens, como Base64 em seus arquivos HTML.

### E se meu documento tiver várias fontes?
Sem problemas! Aspose.Words for .NET incorporará todas as fontes usadas em seu documento como Base64 no arquivo HTML resultante.

### O uso do Aspose.Words for .NET é gratuito?
 Aspose.Words for .NET é uma biblioteca comercial. No entanto, você pode baixar uma versão de avaliação gratuita no site[Aspose Lançamentos](https://releases.aspose.com/) página.
