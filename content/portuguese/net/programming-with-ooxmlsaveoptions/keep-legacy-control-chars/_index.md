---
title: Manter caracteres de controle legados
linktitle: Manter caracteres de controle legados
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como preservar caracteres de controle herdados em documentos do Word usando Aspose.Words for .NET com este guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---
## Introdução

Você já ficou intrigado com aqueles caracteres de controle estranhos e invisíveis em seus documentos do Word? Eles são como pequenos gremlins ocultos que podem atrapalhar a formatação e a funcionalidade. Felizmente, Aspose.Words for .NET oferece um recurso útil para manter intactos esses caracteres de controle herdados ao salvar documentos. Neste tutorial, nos aprofundaremos em como gerenciar esses caracteres de controle usando Aspose.Words for .NET. Iremos dividi-lo passo a passo, garantindo que você entenda todos os detalhes ao longo do caminho. Pronto para começar? Vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

1.  Aspose.Words para .NET: Baixe e instale em[aqui](https://releases.aspose.com/words/net/).
2.  Uma licença Aspose válida: você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
3. Ambiente de desenvolvimento: Visual Studio ou qualquer outro IDE que suporte .NET.
4. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será útil.

## Importar namespaces

Antes de escrever seu código, você precisa importar os namespaces necessários. Adicione as seguintes linhas ao topo do seu arquivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: configurando seu projeto

Primeiro, você precisará configurar seu projeto no Visual Studio (ou no seu IDE preferido). 

1. Crie um novo projeto C#: abra o Visual Studio e crie um novo projeto de aplicativo de console C#.
2. Instale o Aspose.Words para .NET: Use o NuGet Package Manager para instalar o Aspose.Words para .NET. Clique com o botão direito do mouse em seu projeto no Solution Explorer, selecione “Gerenciar pacotes NuGet”, pesquise “Aspose.Words” e instale-o.

## Etapa 2: carregue seu documento

A seguir, você carregará o documento do Word que contém os caracteres de controle herdados.

1. Especifique o caminho do documento: Defina o caminho para o diretório do seu documento.
   
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```

2.  Carregue o documento: Use o`Document` class para carregar seu documento.

   ```csharp
   Document doc = new Document(dataDir + "Legacy control character.doc");
   ```

## Etapa 3: configurar opções de salvamento

Agora, vamos configurar as opções de salvamento para manter intactos os caracteres de controle legados.

1.  Criar opções de salvamento: Inicialize uma instância de`OoxmlSaveOptions` e definir o`KeepLegacyControlChars`propriedade para`true`.

   ```csharp
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc)
   {
       KeepLegacyControlChars = true
   };
   ```

## Etapa 4: salve o documento

Por fim, salve o documento com as opções de salvamento configuradas.

1.  Salve o documento: use o`Save` método do`Document` class para salvar o documento com as opções de salvamento especificadas.

   ```csharp
   doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
   ```

## Conclusão

aí está! Seguindo essas etapas, você pode garantir que seus caracteres de controle herdados sejam preservados ao trabalhar com documentos do Word no Aspose.Words for .NET. Esse recurso pode salvar vidas, especialmente ao lidar com documentos complexos onde os personagens de controle desempenham um papel crucial. 

## Perguntas frequentes

### O que são caracteres de controle legados?

Caracteres de controle legados são caracteres não imprimíveis usados em documentos mais antigos para controlar a formatação e o layout.

### Posso remover esses caracteres de controle em vez de mantê-los?

Sim, você pode usar Aspose.Words for .NET para remover ou substituir esses caracteres, se necessário.

### Este recurso está disponível em todas as versões do Aspose.Words for .NET?

Este recurso está disponível em versões recentes. Certifique-se de usar a versão mais recente para acessar todas as funcionalidades.

### Preciso de uma licença para usar o Aspose.Words for .NET?

 Sim, você precisa de uma licença válida. Você pode obter uma licença temporária para fins de avaliação[aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso encontrar mais documentação sobre Aspose.Words for .NET?

 Você pode encontrar documentação detalhada[aqui](https://reference.aspose.com/words/net/).
 