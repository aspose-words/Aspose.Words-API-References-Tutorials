---
title: Assinando documento Word criptografado
linktitle: Assinando documento Word criptografado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como assinar digitalmente um documento do Word criptografado com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/signing-encrypted-document/
---
Neste tutorial, iremos guiá-lo pelas etapas para usar o recurso de assinatura de um documento do Word criptografado com Aspose.Words for .NET. Este recurso permite assinar digitalmente um documento do Word criptografado usando uma senha de descriptografia. Siga os passos abaixo:

## Etapa 1: definir opções de assinatura

Crie uma instância da classe SignOptions e defina a senha de descriptografia:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Certifique-se de especificar a senha de descriptografia correta para o seu documento criptografado.

## Passo 2: Carregando o certificado

Comece carregando o certificado de assinatura usando a classe CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Certifique-se de especificar o caminho correto para o seu certificado e a senha associada.

## Passo 3: Assinando o documento criptografado

Use a classe DigitalSignatureUtil para assinar o documento criptografado:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Certifique-se de especificar os caminhos corretos para o documento criptografado, o documento assinado e o certificado.

### Exemplo de código-fonte para assinatura de documento criptografado usando Aspose.Words for .NET

Aqui está o código-fonte completo para assinar um documento criptografado com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Seguindo essas etapas, você pode assinar facilmente um documento do Word criptografado com Aspose.Words for .NET.

## Conclusão

Neste tutorial, exploramos o processo de assinatura de um documento criptografado do Word usando Aspose.Words for .NET. Ao fornecer a senha de descriptografia e o certificado de assinatura, podemos adicionar uma assinatura digital a um documento criptografado. A assinatura de documentos criptografados garante sua autenticidade e integridade, proporcionando uma camada extra de segurança. Aspose.Words for .NET permite que você assine documentos criptografados e mantenha a segurança e a confiabilidade de seus arquivos do Word.

### Perguntas frequentes

#### P: O que é assinatura de documentos no Aspose.Words for .NET?

R: A assinatura de documentos no Aspose.Words for .NET refere-se ao processo de assinatura digital de um documento do Word para garantir sua autenticidade, integridade e não repúdio. Envolve adicionar uma assinatura digital ao documento usando um certificado.

#### P: O que é um documento Word criptografado?

R: Um documento Word criptografado é aquele que foi criptografado usando uma senha. A criptografia é uma medida de segurança que protege o conteúdo do documento, embaralhando-o e tornando-o ilegível sem a senha de descriptografia correta.

#### P: Como posso assinar um documento criptografado do Word usando Aspose.Words for .NET?

R: Para assinar um documento Word criptografado usando Aspose.Words for .NET, você precisa fornecer a senha de descriptografia junto com o certificado de assinatura. Siga esses passos:
1.  Defina a senha de descriptografia no`SignOptions` objeto.
2.  Carregue o certificado de assinatura usando o`CertificateHolder` aula.
3.  Use o`DigitalSignatureUtil.Sign` método para assinar o documento criptografado, fornecendo os parâmetros necessários.

#### P: Qual é o propósito de assinar um documento criptografado?

R: Assinar um documento criptografado com Aspose.Words for .NET permite adicionar uma assinatura digital ao documento mesmo quando ele está criptografado. Isto fornece uma camada adicional de segurança e garante a autenticidade e integridade do conteúdo criptografado. Permite que os destinatários verifiquem a origem do documento e detectem qualquer adulteração.

#### P: Posso assinar um documento criptografado sem fornecer a senha de descriptografia?

R: Não, para assinar um documento criptografado, você deve fornecer a senha de descriptografia correta. A senha de descriptografia é necessária para acessar e modificar o conteúdo criptografado do documento antes de aplicar a assinatura digital.

#### P: Posso assinar um documento Word criptografado usando qualquer certificado?

R: Para assinar um documento Word criptografado usando Aspose.Words for .NET, você precisa de um certificado X.509 válido. O certificado pode ser obtido de uma autoridade de certificação (CA) confiável ou um certificado autoassinado pode ser usado para fins de teste.

#### P: Posso assinar vários documentos criptografados do Word usando o mesmo certificado?

 R: Sim, você pode assinar vários documentos criptografados do Word usando o mesmo certificado. Depois de carregar o certificado usando o`CertificateHolder` class, você pode reutilizá-lo para assinar vários documentos criptografados.

#### P: Posso verificar a assinatura digital de um documento criptografado assinado?

 R: Sim, Aspose.Words for .NET fornece funcionalidade para verificar a assinatura digital de um documento criptografado assinado. Você pode usar o`DigitalSignatureUtil.Verify` método para verificar a validade e autenticidade da assinatura digital.

#### P: Qual formato de arquivo o Aspose.Words for .NET suporta para assinar documentos criptografados?

 R: Aspose.Words for .NET suporta assinatura de documentos Word criptografados no formato de arquivo DOCX. Você pode assinar arquivos DOCX criptografados usando o`DigitalSignatureUtil.Sign` método junto com a senha e o certificado de descriptografia necessários.

#### P: Como a assinatura de um documento criptografado afeta a criptografia?

R: Assinar um documento criptografado com Aspose.Words for .NET não afeta a criptografia do documento. A criptografia permanece intacta e a assinatura digital é adicionada ao conteúdo criptografado. A assinatura digital fornece segurança e verificação adicionais sem comprometer a criptografia aplicada ao documento.