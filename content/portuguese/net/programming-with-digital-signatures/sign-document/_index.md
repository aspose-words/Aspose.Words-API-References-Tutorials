---
title: Assinar documento do Word
linktitle: Assinar documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como assinar digitalmente um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/sign-document/
---
Neste tutorial, orientaremos você nas etapas para usar o recurso de assinatura de documentos com Aspose.Words for .NET. Este recurso permite assinar digitalmente um documento do Word usando um certificado. Siga os passos abaixo:

## Passo 1: Carregando o certificado

Comece carregando o certificado de assinatura usando a classe CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Certifique-se de especificar o caminho correto para o seu certificado e a senha associada.

## Passo 2: Assinando o documento

Use a classe DigitalSignatureUtil para assinar o documento:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Certifique-se de especificar os caminhos corretos para o documento de origem e o documento assinado.

### Exemplo de código-fonte para assinar documento usando Aspose.Words for .NET

Aqui está o código-fonte completo para assinar um documento com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Seguindo estas etapas, você pode assinar facilmente um documento do Word com Aspose.Words for .NET.

## Conclusão

 Neste tutorial, exploramos o recurso de assinatura de documentos no Aspose.Words for .NET. Ao carregar um certificado de assinatura e usar o`DigitalSignatureUtil.Sign` método, podemos assinar digitalmente um documento do Word. A assinatura de documentos fornece autenticação e garante a integridade do conteúdo do documento, tornando-se um recurso valioso para um gerenciamento de documentos seguro e confiável.

### Perguntas frequentes para assinar documentos do Word

#### P: O que é assinatura de documentos no Aspose.Words for .NET?

R: A assinatura de documentos no Aspose.Words for .NET refere-se ao processo de assinatura digital de um documento do Word usando um certificado. Este recurso adiciona uma assinatura digital ao documento, proporcionando autenticidade, integridade e não repúdio ao conteúdo do documento.

#### P: Como posso carregar o certificado de assinatura no Aspose.Words for .NET?

 R: Para carregar o certificado de assinatura no Aspose.Words for .NET, você pode usar o`CertificateHolder` aula. Crie uma instância de`CertificateHolder` fornecendo o caminho para o arquivo de certificado e a senha associada. Aqui está um exemplo:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Certifique-se de fornecer o caminho correto para o seu certificado e a senha associada.

#### P: Como assino um documento do Word usando Aspose.Words for .NET?

 R: Para assinar um documento do Word usando Aspose.Words for .NET, você pode usar o`DigitalSignatureUtil` aula. Ligar para`Sign` método, fornecendo o caminho para o documento de origem, o caminho para o documento assinado (saída) e o`CertificateHolder` objeto. Aqui está um exemplo:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Certifique-se de fornecer os caminhos corretos para o documento de origem e o documento assinado (saída).

#### P: Qual é o propósito da assinatura de documentos?

R: A assinatura de documentos serve como um método para garantir a autenticidade e integridade de um documento. Ao assinar digitalmente um documento, você pode comprovar sua origem, verificar se seu conteúdo não foi alterado e estabelecer o não repúdio. A assinatura de documentos é comumente usada para documentos jurídicos, financeiros e confidenciais.

#### P: Posso usar qualquer certificado para assinatura de documentos no Aspose.Words for .NET?

R: Para assinatura de documentos no Aspose.Words for .NET, você precisa usar um certificado X.509 válido. Este certificado pode ser obtido de uma autoridade de certificação (CA) confiável ou um certificado autoassinado pode ser usado para fins de teste.

#### P: Qual formato de arquivo o Aspose.Words for .NET suporta para assinatura de documentos?

 R: Aspose.Words for .NET oferece suporte à assinatura de documentos do Word no formato de arquivo DOCX. Você pode assinar arquivos DOCX usando o`DigitalSignatureUtil` classe e o certificado apropriado.

#### P: Posso assinar vários documentos do Word usando o mesmo certificado?

R: Sim, você pode assinar vários documentos do Word usando o mesmo certificado. Depois de carregar o certificado usando o`CertificateHolder` classe, você pode reutilizá-lo para assinar vários documentos chamando o método`DigitalSignatureUtil.Sign` método com diferentes caminhos de documentos de origem e assinados.

#### P: A assinatura do documento modifica o documento original?

R: A assinatura de documentos com Aspose.Words for .NET não modifica o documento original. Em vez disso, cria uma cópia assinada digitalmente do documento, deixando o documento original intacto. A cópia assinada digitalmente contém a assinatura digital adicionada, garantindo a integridade do conteúdo do documento.

#### P: Posso verificar a assinatura digital de um documento assinado usando Aspose.Words for .NET?

 R: Sim, Aspose.Words for .NET fornece funcionalidade para verificar a assinatura digital de um documento assinado. Você pode usar o`DigitalSignatureUtil.Verify` método para verificar a validade e autenticidade da assinatura digital.