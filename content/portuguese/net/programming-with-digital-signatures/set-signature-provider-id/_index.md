---
title: Definir o ID do provedor de assinatura no documento do Word
linktitle: Definir o ID do provedor de assinatura no documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir o ID do provedor de assinatura em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/set-signature-provider-id/
---
Neste tutorial, orientaremos você nas etapas para usar o recurso Definir ID do provedor de assinatura com Aspose.Words for .NET. Este recurso permite especificar o ID do provedor de assinatura para uma linha de assinatura em um documento do Word. Siga os passos abaixo:

## Passo 1: Carregando o documento e acessando a linha de assinatura

Comece enviando o documento que contém a linha de assinatura:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Etapa 2: definir opções de assinatura

Crie uma instância da classe SignOptions e defina as opções de assinatura, incluindo o ID do provedor:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Passo 3: Assinando o documento

Para assinar o documento, você deve usar a classe DigitalSignatureUtil e especificar o certificado de assinatura:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Certifique-se de especificar os caminhos corretos para o documento, certificado e documento assinado.

### Exemplo de código-fonte para definir ID do provedor de assinatura usando Aspose.Words for .NET

Aqui está o código-fonte completo para definir o ID do provedor de assinatura com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Conclua o ID do provedor de assinatura em seu documento do Word com Aspose.Words for .NET.


## Conclusão

Neste tutorial, aprendemos como definir o ID do provedor de assinatura para uma linha de assinatura em um documento do Word usando Aspose.Words for .NET. Seguindo as etapas fornecidas, você pode facilmente carregar o documento, acessar a linha de assinatura, definir o ID do provedor e assinar o documento. A capacidade de definir o ID do provedor de assinatura ajuda a estabelecer a identidade e a confiabilidade do signatário, aumentando a segurança e a integridade dos seus documentos do Word. Aspose.Words for .NET fornece uma API robusta para processamento de palavras com assinaturas digitais, permitindo personalizar e gerenciar o processo de assinatura com facilidade.

### Perguntas frequentes sobre como definir o ID do provedor de assinatura em um documento do Word

#### P: O que é um ID de provedor de assinatura em um documento do Word?

R: Um ID de provedor de assinatura em um documento do Word é um identificador exclusivo que especifica o provedor de uma assinatura digital. Ajuda a identificar a entidade ou organização responsável pela criação e gerenciamento da assinatura digital.

#### P: Como posso definir o ID do provedor de assinatura para uma linha de assinatura em um documento do Word usando Aspose.Words for .NET?

R: Para definir o ID do provedor de assinatura para uma linha de assinatura em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Carregue o documento usando o`Document` class e especifique o caminho para o arquivo do documento.
2.  Acesse a linha de assinatura usando o método ou propriedade apropriada. Por exemplo, você pode usar`GetChild` método para recuperar a forma da linha de assinatura.
3. Recupere o ID do provedor da linha de assinatura.
4.  Crie uma instância do`SignOptions` classe e definir o`ProviderId` propriedade ao ID do provedor recuperado.
5.  Use o`DigitalSignatureUtil.Sign` método para assinar o documento, fornecendo os parâmetros necessários incluindo o`SignOptions` objeto.

#### P: Como faço para acessar a linha de assinatura em um documento do Word usando Aspose.Words for .NET?

 R: Para acessar a linha de assinatura em um documento do Word usando Aspose.Words for .NET, você pode usar o método ou propriedade apropriado para recuperar o formato da linha de assinatura da estrutura do documento. Por exemplo, você pode usar o`GetChild` método com os parâmetros apropriados para obter o formato de linha de assinatura desejado.

#### P: Posso definir o ID do provedor de assinatura para várias linhas de assinatura em um documento do Word?

 R: Sim, você pode definir o ID do provedor de assinatura para várias linhas de assinatura em um documento do Word. Você pode percorrer a coleção de linhas de assinatura no documento e definir o ID do provedor para cada linha de assinatura individualmente usando o comando`SignOptions.ProviderId` propriedade.

#### P: Qual é a finalidade do ID do provedor de assinatura em um documento do Word?

R: O ID do provedor de assinatura em um documento Word serve para identificar a entidade ou organização responsável pela criação e gerenciamento da assinatura digital. Ajuda a estabelecer a autenticidade e a confiabilidade da assinatura digital, associando-a a um provedor específico.

#### P: Que tipo de certificado digital pode ser usado para definir o ID do provedor de assinatura em um documento do Word?

R: Você pode usar certificados digitais X.509 com informações de provedor apropriadas para definir o ID do provedor de assinatura em um documento do Word. O certificado digital deve ser emitido por uma autoridade de certificação (CA) confiável e conter os metadados necessários para identificar o provedor.