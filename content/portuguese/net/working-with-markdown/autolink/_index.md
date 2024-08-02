---
title: Vinculação automática
linktitle: Vinculação automática
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir link automático com Aspose.Words for .NET Guia passo a passo.
type: docs
weight: 10
url: /pt/net/working-with-markdown/autolink/
---

Neste exemplo, explicaremos como usar o recurso "Autolink" com Aspose.Words for .NET. Este recurso permite inserir hiperlinks em seu documento automaticamente.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passo 2: Inserindo um hiperlink

 Podemos inserir um hiperlink usando o`InsertHyperlink` método do gerador de documentos. Especificamos o URL e o texto a ser exibido para o link.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
```

## Etapa 3: inserir um endereço de e-mail como link

Também podemos inserir um endereço de e-mail como link usando o prefixo “mailto:”. Isso permitirá que os usuários cliquem no link para abrir seu cliente de e-mail padrão.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Passo 4: Salvando o documento

Finalmente, podemos salvar o documento no formato desejado.

### Exemplo de código-fonte para Autolink usando Aspose.Words para .NET


```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Insira o hyperlink.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", falso);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Parabéns! Agora você aprendeu como usar o recurso "Autolink" com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como posso criar um link automático para um endereço URL no Aspose.Words?

 R: Para criar um link automático para um endereço URL no Aspose.Words, você pode usar o`<a>` marque com o`href` atributo que contém o endereço URL. Por exemplo, você pode usar`<a href="https://www.aspose.com">https://www.aspose.com</a>` para vincular automaticamente ao "https: //www.aspose.com".

#### P: É possível personalizar o texto de exibição de um link automático no Aspose.Words?

 R: Sim, você pode personalizar o texto de exibição de um link automático no Aspose.Words. Em vez de usar o endereço URL como texto de exibição, você pode usar qualquer outro texto substituindo o conteúdo entre os`<a>` Tag. Por exemplo, você pode usar`<a href="https://www.aspose.com">Click here</a>`para exibir o texto "Clique aqui" como um link automático.

#### P: Como posso adicionar atributos adicionais a um link automático no Aspose.Words?

 R: Para adicionar atributos adicionais a um link automático no Aspose.Words, você pode usar atributos HTML adicionais dentro do`<a>` marcação. Por exemplo, você pode usar`<a href="https://www.aspose.com" target="_blank">Link</a>` para abrir o link em uma nova janela ou guia usando o` attribute target="_blank"`.