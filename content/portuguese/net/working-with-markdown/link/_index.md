---
title: Link
linktitle: Link
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir links com Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/working-with-markdown/link/
---

Neste exemplo, orientaremos você sobre como usar o recurso de links com Aspose.Words for .NET. Os links são usados para criar referências clicáveis a sites ou outros documentos.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passo 2: Inserindo um link

 Podemos inserir um link usando o`InsertHyperlink` método do gerador de documentos. Precisamos especificar o texto do link, aqui “Apose”, bem como a URL de destino.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", falso);
```

### Exemplo de código-fonte para links com Aspose.Words for .NET


```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Inserir link.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", falso);
```
Parabéns! Agora você aprendeu como usar o recurso de links com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como posso vincular a um URL no Aspose.Words?

 R: Para vincular a um endereço URL no Aspose.Words, você pode usar o`<a>` marque com o`href` atributo que contém o endereço URL. Por exemplo, você pode usar`<a href="https://www.aspose.com">Click Here</a>` para criar um hiperlink para o URL "https://www.example.com" com o texto de exibição "Clique aqui".

#### P: É possível vincular a um marcador interno no Aspose.Words?

 R: Sim, é possível vincular a um marcador interno no Aspose.Words. Você pode usar o`<a>` marque com o`href` atributo contendo o nome do marcador precedido por um hash (#). Por exemplo,`<a href="#bookmark1">Go to bookmark 1</a>` irá vincular ao marcador chamado "bookmark1" no documento.

#### P: Como posso personalizar o texto de exibição de um link no Aspose.Words?

R: Para personalizar o texto de exibição de um link no Aspose.Words, você pode modificar o conteúdo entre o`<a>` Tag. Por exemplo,`<a href="https://www.aspose.com">Click here</a>` exibirá o texto "Clique aqui" como um hiperlink.

#### P: Posso especificar um destino para um link no Aspose.Words?

 R: Sim, você pode especificar um destino para um link no Aspose.Words usando o`target` atributo do`<a>` marcação. Por exemplo,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` abrirá o link em uma nova janela ou guia.