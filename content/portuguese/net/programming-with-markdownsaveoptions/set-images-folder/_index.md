---
title: Definir pasta de imagens
linktitle: Definir pasta de imagens
second_title: API de processamento de documentos Aspose.Words
description: Converta documentos do Word em Markdown com alinhamento de tabela adequado usando Aspose.Words for .NET. Siga nosso guia detalhado para resultados perfeitos.
type: docs
weight: 10
url: /pt/net/programming-with-markdownsaveoptions/set-images-folder/
---
## Introdução

Você já quis exportar seu documento do Word para o formato Markdown e garantir que as tabelas e o conteúdo estejam perfeitamente alinhados? Aspose.Words for .NET é a solução ideal para esta tarefa. Neste artigo, orientaremos você no processo de configuração do Aspose.Words, preparação do seu documento e exportação para Markdown com alinhamento adequado do conteúdo da tabela. Descreveremos cada etapa para facilitar o acompanhamento e a compreensão. Então, vamos mergulhar e transformar seus documentos do Word em arquivos Markdown lindamente alinhados!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Aspose.Words para .NET: você pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
-  Uma licença válida: obtenha uma avaliação gratuita[aqui](https://releases.aspose.com/) ou uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
- Visual Studio: ou qualquer outro IDE que suporte desenvolvimento .NET.
- Conhecimento básico de C#: Compreensão da linguagem de programação C#.

## Importar namespaces

Para começar, você precisará importar os namespaces necessários em seu projeto C#. Esses namespaces permitirão que você acesse a funcionalidade Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.IO;
```

## Etapa 1: configure seu projeto

Primeiramente, configure seu projeto .NET em seu IDE. Crie um novo aplicativo de console e adicione uma referência ao Aspose.Words for .NET.

### 1.1 Crie um novo projeto

Abra o Visual Studio e crie um novo projeto de aplicativo de console. Nomeie-o como "MarkdownExporter" ou algo semelhante.

### 1.2 Adicionar referência Aspose.Words

 Para adicionar Aspose.Words ao seu projeto, você pode baixar a DLL do[Aspor site](https://releases.aspose.com/words/net/) e adicione-o manualmente ou use o NuGet Package Manager:

```bash
Install-Package Aspose.Words
```

## Etapa 2: Escreva o código para exportar como Markdown

Agora, vamos escrever o código para ler o documento Word e salvá-lo como um arquivo Markdown com alinhamento de tabela adequado.

### 2.1 Defina o caminho para o seu documento

Defina o caminho para o seu documento do Word e a pasta onde deseja salvar as imagens.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

### 2.2 Carregar o documento

Carregue seu documento do Word usando Aspose.Words.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

### 2.3 Configurar opções de salvamento de Markdown

 Configurar o`MarkdownSaveOptions` para especificar onde as imagens devem ser armazenadas.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    ImagesFolder = dataDir + "Images"
};
```

### 2.4 Salvar o documento como Markdown

 Use um`MemoryStream` para salvar o documento no formato Markdown.

```csharp
using (MemoryStream stream = new MemoryStream())
{
    doc.Save(stream, saveOptions);
}
```

## Conclusão

Exportar um documento do Word para Markdown com alinhamento de conteúdo de tabela usando Aspose.Words for .NET é simples quando você segue estas etapas. Com algumas linhas de código, você pode automatizar o processo de conversão e garantir que seu conteúdo esteja bem formatado. Agora você pode compartilhar facilmente seus documentos no formato Markdown, sabendo que eles terão uma ótima aparência e manterão sua estrutura.

## Perguntas frequentes

### Posso usar Aspose.Words for .NET com outras linguagens de programação?

Sim, Aspose.Words for .NET pode ser usado com qualquer linguagem compatível com .NET, como VB.NET, F# e muito mais.

### Como obtenho uma licença temporária do Aspose.Words?

 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Que tipos de documentos posso converter para Markdown?

Você pode converter vários documentos do Word, incluindo .doc, .docx, .rtf e muito mais.

### Há alguma limitação na versão de teste do Aspose.Words?

 versão de teste possui algumas limitações, como marcas d'água nos arquivos de saída. Você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Onde posso encontrar mais exemplos e documentação para Aspose.Words?

 Você pode encontrar documentação detalhada e exemplos no[Aspor site](https://reference.aspose.com/words/net/).
