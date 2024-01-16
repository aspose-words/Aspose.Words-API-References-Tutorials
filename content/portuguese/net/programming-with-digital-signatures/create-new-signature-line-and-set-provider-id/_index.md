---
title: Crie uma nova linha de assinatura e defina o ID do provedor
linktitle: Crie uma nova linha de assinatura e defina o ID do provedor
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma nova linha de assinatura e definir o ID do provedor em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
Neste tutorial, orientaremos você nas etapas para usar o recurso Criar nova linha de assinatura e definir ID do provedor com Aspose.Words for .NET. Este recurso permite inserir uma linha de assinatura em um documento do Word, definir opções personalizadas e assinar o documento. Siga os passos abaixo:

## Etapa 1: Criando o Documento e o Gerador

Comece criando uma instância da classe Document e um objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: definir opções de linha de assinatura

Crie uma instância da classe SignatureLineOptions e defina as opções desejadas:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Passo 3: Inserindo a linha de assinatura

Use o método InsertSignatureLine() do objeto DocumentBuilder para inserir a linha de assinatura no documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Etapa 4: definir o ID do provedor

Defina o ID do provedor para a linha de assinatura usando a propriedade ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Certifique-se de especificar o ID do provedor correto para seu caso de uso.

## Etapa 5: salve o documento

Salve o documento modificado:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para salvar o documento.

## Passo 6: Assinando o documento

Para assinar o documento, você precisa definir as opções de assinatura e usar a classe DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Certifique-se de especificar os caminhos corretos para o documento, certificado e documento assinado.

### Exemplo de código-fonte para criar nova linha de assinatura e definir o ID do provedor usando Aspose.Words for .NET

Aqui está o código-fonte completo para criar uma nova linha de assinatura e definir o ID do provedor com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

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

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Seguindo essas etapas, você pode criar facilmente uma nova linha de assinatura e definir o ID do provedor em seu documento do Word com Aspose.Words for .NET.

## Conclusão

Neste tutorial, exploramos o recurso de criação de uma nova linha de assinatura e configuração do ID do provedor em um documento do Word usando Aspose.Words for .NET. Seguindo as etapas fornecidas, você pode inserir facilmente uma linha de assinatura com opções personalizadas e associá-la a um provedor específico usando o ID do provedor. Adicionar linhas de assinatura e personalizar as informações do fornecedor aumenta a autenticidade e a confiabilidade dos seus documentos. Aspose.Words for .NET fornece uma API poderosa para processamento de palavras com linhas de assinatura e certificados digitais em documentos Word, permitindo automatizar o processo de assinatura e garantir a validade de seus documentos.

### Perguntas frequentes

#### P: O que é um ID de provedor em uma linha de assinatura?

R: Um ID de provedor em uma linha de assinatura é um identificador exclusivo que representa o provedor da assinatura digital. Ajuda a identificar a fonte ou organização responsável pela assinatura.

#### P: Como posso criar uma nova linha de assinatura em um documento do Word usando Aspose.Words for .NET?

R: Para criar uma nova linha de assinatura em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Crie uma instância do`Document` aula e um`DocumentBuilder` objeto.
2.  Crie uma instância do`SignatureLineOptions` class e defina as opções de linha de assinatura desejadas.
3.  Use o`InsertSignatureLine` método do`DocumentBuilder` objeto para inserir a linha de assinatura no documento.

#### P: Posso personalizar as opções da linha de assinatura, como nome do signatário, cargo e instruções?

 R: Sim, você pode personalizar as opções da linha de assinatura. O`SignatureLineOptions` classe fornece propriedades para definir as opções desejadas, como`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, etc. Você pode modificar essas propriedades antes de inserir a linha de assinatura.

#### P: Qual é o propósito de definir o ID do provedor para uma linha de assinatura?

R: Definir o ID do provedor para uma linha de assinatura ajuda a identificar a fonte ou organização responsável pela assinatura digital. Permite associar a assinatura a um fornecedor ou entidade específica, fornecendo informações adicionais sobre a origem e fiabilidade da assinatura.

#### P: Como posso definir o ID do provedor para uma linha de assinatura usando Aspose.Words for .NET?

R: Para definir o ID do provedor para uma linha de assinatura usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Após inserir a linha de assinatura, acesse o`ProviderId` propriedade do`SignatureLine` objeto.
2.  Colocou o`ProviderId` propriedade para o valor de ID do provedor desejado usando o`Guid` tipo de dados.

#### P: Posso assinar o documento depois de criar uma nova linha de assinatura e definir o ID do provedor?

 R: Sim, após criar uma nova linha de assinatura e definir o ID do provedor, você poderá assinar o documento. Para assinar o documento, você precisa definir as opções de assinatura, incluindo o ID da linha de assinatura, ID do provedor, comentários e horário de assinatura. Então, use o`DigitalSignatureUtil.Sign` método para assinar o documento usando um certificado digital.

#### P: Posso especificar um ID de provedor específico para cada linha de assinatura em um documento do Word?

R: Sim, você pode especificar um ID de provedor específico para cada linha de assinatura em um documento do Word. Depois de inserir cada linha de assinatura, você pode definir o ID do provedor para aquela linha de assinatura específica acessando o`ProviderId` propriedade do respectivo`SignatureLine` objeto.

#### P: Como posso salvar o documento modificado após criar uma nova linha de assinatura e definir o ID do provedor?

 R: Para salvar o documento modificado após criar uma nova linha de assinatura e definir o ID do provedor, você pode usar o`Save` método do`Document` objeto. Especifique o caminho e o nome de arquivo corretos para salvar o documento.

#### P: Qual formato de arquivo o Aspose.Words for .NET suporta para criar e assinar linhas de assinatura?

R: Aspose.Words for .NET suporta a criação e assinatura de linhas de assinatura no formato de arquivo DOCX. Você pode criar e assinar linhas de assinatura em arquivos DOCX usando os métodos e classes fornecidos.

#### P: Posso modificar o ID do provedor ou outras opções de uma linha de assinatura depois de assinada?

R: Depois que uma linha de assinatura for assinada, ela se tornará parte do conteúdo do documento e não poderá ser modificada separadamente. Quaisquer modificações na linha de assinatura, como alterar o ID do provedor ou outras opções, exigiriam a remoção da assinatura existente e a criação de uma nova linha de assinatura.