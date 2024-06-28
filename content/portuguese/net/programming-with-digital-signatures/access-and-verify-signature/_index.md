---
title: Acesse e verifique a assinatura em um documento do Word
linktitle: Acesse e verifique a assinatura em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como acessar e verificar assinaturas digitais em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/access-and-verify-signature/
---
Neste tutorial, iremos guiá-lo pelas etapas para usar o recurso de verificação de acesso e assinatura do Aspose.Words for .NET. Este recurso permite acessar assinaturas digitais em um documento Word e verificar sua validade. Siga os passos abaixo:

## Passo 1: Carregando o documento e acessando as assinaturas

Comece enviando o documento que contém as assinaturas digitais:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Etapa 2: navegar pelas assinaturas digitais

Use um loop para percorrer todas as assinaturas digitais do documento:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Acessar informações de assinatura
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Esta propriedade está disponível somente em documentos do MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Certifique-se de personalizar as mensagens de exibição de acordo com suas necessidades.

### Exemplo de código-fonte para Access And Verify Signature usando Aspose.Words for .NET

Aqui está o código-fonte completo para acesso e verificação de assinatura usando Aspose.Words for .NET:

```csharp
	
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Esta propriedade está disponível somente em documentos do MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Seguindo essas etapas, você poderá acessar e verificar facilmente as assinaturas digitais em seu documento Word com Aspose.Words for .NET.

## Conclusão

Neste tutorial, exploramos o recurso de acesso e verificação de assinaturas digitais em um documento Word usando Aspose.Words for .NET. Seguindo as etapas fornecidas, você pode facilmente carregar um documento, acessar suas assinaturas digitais e verificar sua validade. A capacidade de acessar e verificar assinaturas digitais fornece uma maneira de garantir a integridade e a autenticidade dos seus documentos do Word. Aspose.Words for .NET oferece uma API poderosa para processamento de palavras com assinaturas digitais, permitindo automatizar o processo de verificação e aumentar a segurança de seus documentos.

### Perguntas frequentes

#### P: O que são assinaturas digitais em um documento do Word?

R: As assinaturas digitais em um documento Word são assinaturas eletrônicas que fornecem uma forma de autenticar a integridade e a origem do documento. Eles são criados por meio de certificados digitais e algoritmos criptográficos, permitindo aos destinatários verificar se o documento não foi alterado e se provém de uma fonte confiável.

#### P: Como posso acessar assinaturas digitais em um documento do Word usando Aspose.Words for .NET?

R: Para acessar assinaturas digitais em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Carregue o documento usando o`Document` class e especifique o caminho para o arquivo do documento.
2.  Use um loop para iterar pelo`DigitalSignatures` coleta dos documentos. Cada iteração representa uma assinatura digital.

#### P: Que informações posso acessar a partir de uma assinatura digital em um documento do Word?

R: A partir de uma assinatura digital em um documento Word, você pode acessar diversas informações, como:
- Validade: Verifique se a assinatura é válida.
- Comentários: Obtenha o motivo da assinatura especificado pelo signatário.
- Hora de Assinatura: Obtenha a hora em que o documento foi assinado.
- Nome do assunto: recupere o nome do signatário ou do assunto do certificado.
- Nome do Emissor: Obtenha o nome do emissor do certificado.

#### P: Posso verificar a validade de uma assinatura digital em um documento do Word usando Aspose.Words for .NET?

 R: Sim, você pode verificar a validade de uma assinatura digital em um documento do Word usando Aspose.Words for .NET. Ao acessar o`IsValid` propriedade do`DigitalSignature` objeto, você pode determinar se a assinatura é válida ou não.

#### P: Como posso verificar a validade das assinaturas digitais em um documento do Word usando Aspose.Words for .NET?

R: Para verificar a validade das assinaturas digitais em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Acesse o`DigitalSignatures` coleta dos documentos.
2.  Iterar através de cada`DigitalSignature` objeto na coleção.
3.  Use o`IsValid` propriedade do`DigitalSignature` objeto para verificar se a assinatura é válida.

#### P: Posso recuperar os comentários do signatário ou o motivo da assinatura a partir de uma assinatura digital em um documento do Word?

R: Sim, você pode recuperar os comentários do signatário ou o motivo da assinatura a partir de uma assinatura digital em um documento do Word. O`Comments` propriedade do`DigitalSignature` O objeto fornece acesso aos comentários especificados pelo signatário durante o processo de assinatura.

#### P: Que tipo de documentos o recurso de verificação de assinatura suporta no Aspose.Words for .NET?

R: O recurso de verificação de assinatura do Aspose.Words for .NET oferece suporte à verificação de assinaturas digitais em documentos do Word com o formato de arquivo DOCX. Você pode usar este recurso para verificar assinaturas em arquivos DOCX.

#### P: Como posso acessar os detalhes do certificado de uma assinatura digital em um documento do Word usando Aspose.Words for .NET?

 R: Para acessar os detalhes do certificado de uma assinatura digital em um documento do Word usando Aspose.Words for .NET, você pode acessar o`CertificateHolder` propriedade do`DigitalSignature` objeto. De`CertificateHolder` objeto, você pode recuperar vários detalhes do certificado, como o nome da entidade e o nome do emissor.

#### P: Posso personalizar a exibição ou processamento de assinaturas digitais em um documento do Word usando Aspose.Words for .NET?

 R: Sim, você pode personalizar a exibição ou processamento de assinaturas digitais em um documento do Word usando Aspose.Words for .NET. Acessando as propriedades e métodos do`DigitalSignature` objeto, você pode extrair as informações desejadas, realizar validações adicionais ou integrar o processo de verificação de assinatura ao fluxo de trabalho do seu aplicativo.

#### P: É possível verificar múltiplas assinaturas digitais em um documento do Word usando Aspose.Words for .NET?

 R: Sim, é possível verificar múltiplas assinaturas digitais em um documento Word usando Aspose.Words for .NET. Ao iterar através do`DigitalSignatures` coleta do documento, você pode acessar e verificar cada assinatura digital individualmente.

