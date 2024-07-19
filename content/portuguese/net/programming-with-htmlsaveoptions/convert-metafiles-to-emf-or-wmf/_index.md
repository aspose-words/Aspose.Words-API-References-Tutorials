---
title: Converter metarquivos em Emf ou Wmf
linktitle: Converter metarquivos em Emf ou Wmf
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para converter metarquivos para formatos EMF ou WMF ao converter um documento para HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---
## Introdução

Bem-vindo a outro mergulho profundo no mundo do Aspose.Words for .NET. Hoje, estamos abordando um truque interessante: converter imagens SVG em formatos EMF ou WMF em seus documentos do Word. Isso pode parecer um pouco técnico, mas não se preocupe. Ao final deste tutorial, você será um profissional nisso. Quer você seja um desenvolvedor experiente ou esteja apenas começando com o Aspose.Words for .NET, este guia irá guiá-lo por tudo o que você precisa saber, passo a passo.

## Pré-requisitos

Antes de mergulharmos no código, vamos ter certeza de que temos tudo configurado. Aqui está o que você precisa:

1. Biblioteca Aspose.Words for .NET: Certifique-se de ter a versão mais recente. Se você não tiver, você pode baixá-lo em[aqui](https://releases.aspose.com/words/net/).
2. .NET Framework: certifique-se de ter o .NET Framework instalado em sua máquina.
3. Ambiente de Desenvolvimento: Um IDE como o Visual Studio facilitará sua vida.
4. Conhecimento básico de C#: você não precisa ser um especialista, mas um conhecimento básico ajudará.

Tem tudo? Ótimo! Vamos começar.

## Importar namespaces

Em primeiro lugar, precisamos importar os namespaces necessários. Isto é crucial porque informa ao nosso programa onde encontrar as classes e métodos que usaremos.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Esses namespaces cobrem tudo, desde funções básicas do sistema até a funcionalidade específica do Aspose.Words que precisamos para este tutorial.

## Etapa 1: configure seu diretório de documentos

Vamos começar definindo o caminho para o diretório de documentos. É aqui que o seu documento do Word será salvo após convertermos os metarquivos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real onde você deseja salvar seu documento.

## Etapa 2: crie a string HTML com SVG

A seguir, precisamos de uma string HTML que contenha a imagem SVG que queremos converter. Aqui está um exemplo simples:

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' width='500' height='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";
```

Este trecho de HTML inclui um SVG básico que diz "Olá, mundo!".

## Etapa 3: carregar HTML com a opção ConvertSvgToEmf

 Agora, usamos o`HtmlLoadOptions` para especificar como queremos lidar com as imagens SVG no HTML. Contexto`ConvertSvgToEmf` para`true` garante que as imagens SVG sejam convertidas para o formato EMF.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

 Este trecho de código cria um novo`Document` objeto carregando a string HTML nele com as opções de carregamento especificadas.

## Etapa 4: definir HtmlSaveOptions para formato de metarquivo

 Para salvar o documento com o formato de metarquivo correto, usamos`HtmlSaveOptions` . Aqui, definimos`MetafileFormat` para`HtmlMetafileFormat.Png` , mas você pode alterar isso para`Emf` ou`Wmf` dependendo de suas necessidades.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Png };
```

## Etapa 5: salve o documento

Finalmente, salvamos o documento usando as opções de salvamento especificadas.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToPng.html", saveOptions);
```

Isso salva o documento no diretório especificado com o formato de metarquivo convertido conforme definido.

## Conclusão

aí está! Seguindo essas etapas, você converteu com êxito imagens SVG em formatos EMF ou WMF em seus documentos do Word usando Aspose.Words for .NET. Este método é útil para garantir a compatibilidade e manter a integridade visual dos seus documentos em diferentes plataformas. Boa codificação!

## Perguntas frequentes

### Posso converter outros formatos de imagem usando este método?
Sim, você pode converter vários formatos de imagem ajustando as opções de carregamento e salvamento de acordo.

### É necessário utilizar uma versão específica do .NET Framework?
Aspose.Words for .NET oferece suporte a várias versões do .NET Framework, mas é sempre uma boa ideia usar a versão mais recente para obter melhor compatibilidade e recursos.

### Qual é a vantagem de converter SVG em EMF ou WMF?
A conversão de SVG em EMF ou WMF garante que os gráficos vetoriais sejam preservados e renderizados corretamente em ambientes que podem não oferecer suporte total a SVG.

### Posso automatizar esse processo para vários documentos?
Absolutamente! Você pode percorrer vários arquivos HTML, aplicando o mesmo processo para automatizar a conversão para processamento em lote.

### Onde posso encontrar mais recursos e suporte para Aspose.Words for .NET?
 Você pode encontrar documentação abrangente[aqui](https://reference.aspose.com/words/net/) e obtenha suporte da comunidade Aspose[aqui](https://forum.aspose.com/c/words/8).