---
title: Adicionar prefixo de nome de classe CSS
linktitle: Adicionar prefixo de nome de classe CSS
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar um prefixo de nome de classe CSS ao salvar documentos do Word como HTML usando Aspose.Words for .NET. Guia passo a passo, trechos de código e perguntas frequentes incluídas.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## Introdução

Bem-vindo! Se você está mergulhando no mundo do Aspose.Words for .NET, você terá uma surpresa. Hoje, exploraremos como adicionar um prefixo de nome de classe CSS ao salvar um documento do Word como HTML usando Aspose.Words for .NET. Este recurso é muito útil quando você deseja evitar conflitos de nomes de classes em seus arquivos HTML.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Aspose.Words for .NET: Se você ainda não o instalou,[baixe aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: Visual Studio ou qualquer outro IDE C#.
-  Um documento do Word: usaremos um documento chamado`Rendering.docx`. Coloque-o no diretório do seu projeto.

## Importar namespaces

Primeiro, certifique-se de ter os namespaces necessários importados para seu projeto C#. Adicione-os no topo do seu arquivo de código:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Agora, vamos mergulhar no guia passo a passo!

## Etapa 1: configure seu projeto

Antes de começarmos a adicionar um prefixo de nome de classe CSS, vamos configurar nosso projeto.

### Etapa 1.1: Crie um novo projeto

 Abra seu Visual Studio e crie um novo projeto de aplicativo de console. Dê um nome cativante como`AsposeCssPrefixExample`.

### Etapa 1.2: Adicionar Aspose.Words para .NET

Se ainda não o fez, adicione Aspose.Words for .NET ao seu projeto via NuGet. Basta abrir o Console do Gerenciador de Pacotes NuGet e executar:

```bash
Install-Package Aspose.Words
```

Ótimo! Agora estamos prontos para começar a codificar.

## Etapa 2: carregue seu documento

A primeira coisa que precisamos fazer é carregar o documento Word que queremos converter para HTML.

### Etapa 2.1: Definir o caminho do documento

 Configure o caminho para o diretório do seu documento. Para este tutorial, vamos supor que seu documento esteja em uma pasta chamada`Documents` dentro do diretório do seu projeto.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Passo 2.2: Carregar o Documento

Agora, vamos carregar o documento usando Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: configurar opções de salvamento de HTML

A seguir, precisamos configurar as opções de salvamento de HTML para incluir um prefixo de nome de classe CSS.

### Etapa 3.1: Criar opções para salvar HTML

 Instancie o`HtmlSaveOptions` objeto e defina o tipo de folha de estilo CSS como`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Etapa 3.2: Definir o prefixo do nome da classe CSS

 Agora, vamos definir o`CssClassNamePrefix` propriedade para o prefixo desejado. Para este exemplo, usaremos`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Etapa 4: salve o documento como HTML

Por fim, vamos salvar o documento como um arquivo HTML com nossas opções configuradas.


Especifique o caminho do arquivo HTML de saída e salve o documento.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Etapa 5: verifique a saída

 Depois de executar seu projeto, navegue até seu`Documents` pasta. Você deve encontrar um arquivo HTML chamado`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . Abra este arquivo em um editor de texto ou navegador para verificar se as classes CSS possuem o prefixo`pfx_`.

## Conclusão

E aí está! Seguindo essas etapas, você adicionou com êxito um prefixo de nome de classe CSS à sua saída HTML usando Aspose.Words for .NET. Este recurso simples, mas poderoso, pode ajudá-lo a manter estilos limpos e sem conflitos em seus documentos HTML.

## Perguntas frequentes

### Posso usar um prefixo diferente para cada operação de salvamento?
 Sim, você pode personalizar o prefixo sempre que salvar um documento, alterando o`CssClassNamePrefix` propriedade.

### Este método oferece suporte a CSS embutido?
 O`CssClassNamePrefix`propriedade funciona com CSS externo. Para CSS in-line, você precisará de uma abordagem diferente.

### Como posso incluir outras opções de salvamento de HTML?
 Você pode configurar diversas propriedades de`HtmlSaveOptions` para personalizar sua saída HTML. Verifique o[documentação](https://reference.aspose.com/words/net/) para mais detalhes.

### É possível salvar o HTML em um stream?
 Absolutamente! Você pode salvar o documento em um stream passando o objeto stream para o`Save` método.

### Como posso obter suporte se tiver problemas?
 Você pode obter suporte do[Aspor fórum](https://forum.aspose.com/c/words/8).