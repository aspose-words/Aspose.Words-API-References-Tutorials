---
title: Crie uma nova linha de assinatura e defina o ID do provedor
linktitle: Crie uma nova linha de assinatura e defina o ID do provedor
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma nova linha de assinatura e definir o ID do provedor em documentos do Word usando Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Introdução

Olá, entusiastas da tecnologia! Já se perguntou como adicionar uma linha de assinatura em seus documentos do Word de forma programática? Bem, hoje estamos mergulhando exatamente nisso usando Aspose.Words for .NET. Este guia orientará você em cada etapa, tornando muito fácil criar uma nova linha de assinatura e definir o ID do provedor em seus documentos do Word. Esteja você automatizando o processamento de documentos ou apenas procurando agilizar seu fluxo de trabalho, este tutorial tem o que você precisa.

## Pré-requisitos

Antes de sujarmos as mãos, vamos ter certeza de que temos tudo o que precisamos:

1.  Aspose.Words for .NET: Se ainda não o fez, faça o download[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: Visual Studio ou qualquer outro ambiente de desenvolvimento C#.
3. .NET Framework: certifique-se de ter o .NET Framework instalado.
4. Certificado PFX: Para assinar documentos, você precisará de um certificado PFX. Você pode obter um de uma autoridade de certificação confiável.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários em seu projeto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Tudo bem, vamos ao que interessa. Aqui está uma análise detalhada de cada etapa para criar uma nova linha de assinatura e definir o ID do provedor.

## Etapa 1: crie um novo documento

Para começar, precisamos criar um novo documento Word. Esta será a tela da nossa linha de assinatura.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Neste trecho, estamos inicializando um novo`Document` e um`DocumentBuilder` . O`DocumentBuilder` nos ajuda a adicionar elementos ao nosso documento.

## Etapa 2: definir opções de linha de assinatura

A seguir, definimos as opções para nossa linha de assinatura. Isso inclui o nome, cargo, e-mail do signatário e outros detalhes.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Essas opções personalizam a linha de assinatura, tornando-a clara e profissional.

## Etapa 3: insira a linha de assinatura

Com nossas opções definidas, agora podemos inserir a linha de assinatura no documento.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Aqui o`InsertSignatureLine` adiciona a linha de assinatura e atribuímos um ID de provedor exclusivo a ela.

## Etapa 4: salve o documento

Após inserir a linha de assinatura, vamos salvar o documento.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Isso salva seu documento com a linha de assinatura recém-adicionada.

## Etapa 5: configurar opções de assinatura

Agora precisamos configurar as opções de assinatura do documento. Isso inclui o ID da linha de assinatura, o ID do provedor, os comentários e o horário de assinatura.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Essas opções garantem que o documento seja assinado com os detalhes corretos.

## Etapa 6: Criar titular do certificado

Para assinar o documento, usaremos um certificado PFX. Vamos criar um detentor de certificado para isso.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Certifique-se de substituir`"morzal.pfx"` com seu arquivo de certificado real e`"aw"` com a senha do seu certificado.

## Etapa 7: Assine o Documento

Por fim, assinamos o documento usando o utilitário de assinatura digital.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Isso assina o documento e o salva como um novo arquivo.

## Conclusão

E aí está! Você criou com sucesso uma nova linha de assinatura e definiu o ID do provedor em um documento do Word usando Aspose.Words for .NET. Esta poderosa biblioteca torna incrivelmente fácil gerenciar e automatizar tarefas de processamento de documentos. Experimente e veja como ele pode agilizar seu fluxo de trabalho.

## Perguntas frequentes

### Posso personalizar a aparência da linha de assinatura?
Absolutamente! Você pode ajustar várias opções no`SignatureLineOptions` para atender às suas necessidades.

### E se eu não tiver um certificado PFX?
Você precisará obter um de uma autoridade de certificação confiável. É essencial para assinar documentos digitalmente.

### Posso adicionar várias linhas de assinatura a um documento?
Sim, você pode adicionar quantas linhas de assinatura forem necessárias, repetindo o processo de inserção com diferentes opções.

### O Aspose.Words for .NET é compatível com o .NET Core?
Sim, o Aspose.Words for .NET oferece suporte ao .NET Core, tornando-o versátil para diferentes ambientes de desenvolvimento.

### Quão seguras são as assinaturas digitais?
Assinaturas digitais criadas com Aspose.Words são altamente seguras, desde que você use um certificado válido e confiável.