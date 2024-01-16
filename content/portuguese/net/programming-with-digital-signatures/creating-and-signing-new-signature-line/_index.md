---
title: Criação e assinatura de nova linha de assinatura
linktitle: Criação e assinatura de nova linha de assinatura
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar e assinar uma nova linha de assinatura em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
Neste tutorial, orientaremos você nas etapas para usar o recurso de criação e assinatura de uma nova linha de assinatura com Aspose.Words for .NET. Este recurso permite inserir uma linha de assinatura em um documento do Word, definir opções personalizadas e assinar o documento. Siga os passos abaixo:

## Etapa 1: Criando o Documento e o Gerador

Comece criando uma instância da classe Document e um objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passo 2: Inserindo a linha de assinatura

Use o método InsertSignatureLine() do objeto DocumentBuilder para inserir uma nova linha de assinatura no documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Etapa 3: salve o documento

Salve o documento modificado:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para salvar o documento.

## Passo 4: Assinando o documento

Para assinar o documento, você precisa definir as opções de assinatura e usar a classe DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Certifique-se de especificar os caminhos corretos para o documento, a imagem da linha de assinatura e o documento assinado.

### Exemplo de código-fonte para criação e assinatura de nova linha de assinatura usando Aspose.Words for .NET

Aqui está o código-fonte completo para criar e assinar uma nova linha de assinatura com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Seguindo estas etapas, você poderá criar e assinar facilmente uma nova linha de assinatura em seu documento Word com Aspose.Words for .NET.

## Conclusão

Neste tutorial, aprendemos como criar e assinar uma nova linha de assinatura em um documento Word usando Aspose.Words for .NET. Seguindo as etapas fornecidas, você pode inserir facilmente uma linha de assinatura em seu documento, personalizar suas opções e assinar o documento usando um certificado digital. Adicionar linhas de assinatura e assinaturas digitais aos seus documentos aumenta sua autenticidade e integridade, tornando-os mais seguros e confiáveis. Aspose.Words for .NET fornece uma API poderosa para processamento de palavras com assinaturas e certificados digitais em documentos Word, permitindo automatizar o processo de assinatura e garantir a validade de seus documentos.

### Perguntas frequentes

#### P: O que é uma linha de assinatura em um documento do Word?

R: Uma linha de assinatura em um documento do Word é um espaço reservado que indica onde a assinatura deve ser colocada. Normalmente inclui o nome, título e data e fornece espaço para uma assinatura manuscrita ou digital.

#### P: Como posso criar uma linha de assinatura em um documento do Word usando Aspose.Words for .NET?

R: Para criar uma linha de assinatura em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Crie uma instância do`Document` aula e um`DocumentBuilder` objeto.
2.  Use o`InsertSignatureLine` método do`DocumentBuilder` objeto para inserir uma nova linha de assinatura no documento.
3. Salve o documento modificado.

#### P: Posso personalizar as opções da linha de assinatura, como nome, título e data?

 R: Sim, você pode personalizar as opções de linha de assinatura. O`SignatureLineOptions` classe fornece propriedades para definir as opções desejadas, como`Signer`, `SignerTitle`, `ShowDate`, etc. Você pode modificar essas propriedades antes de inserir a linha de assinatura.

#### P: Como posso assinar o documento depois de criar uma linha de assinatura?

 R: Para assinar o documento após criar uma linha de assinatura, você precisa definir as opções de assinatura e usar o`DigitalSignatureUtil` aula. Aqui estão as etapas:
1.  Colocou o`SignatureLineId` propriedade no`SignOptions` objeto ao ID da linha de assinatura.
2.  Colocou o`SignatureLineImage` propriedade no`SignOptions` objeto à imagem da assinatura que você deseja usar.
3.  Carregue o certificado de assinatura usando o`CertificateHolder` aula.
4.  Use o`DigitalSignatureUtil.Sign` método para assinar o documento, fornecendo os parâmetros necessários.

#### P: Posso usar uma imagem de assinatura digital para assinar o documento?

 R: Sim, você pode usar uma imagem de assinatura digital para assinar o documento. Para fazer isso, você precisa fornecer o arquivo de imagem no`SignOptions` objeto usando o`SignatureLineImage`propriedade. A imagem pode estar em qualquer formato de imagem compatível, como JPEG, PNG ou EMF.

#### P: Qual é o propósito de criar e assinar uma nova linha de assinatura em um documento do Word?

R: Criar e assinar uma nova linha de assinatura em um documento do Word usando Aspose.Words for .NET permite adicionar um espaço reservado para uma assinatura e depois assinar o documento usando um certificado digital. Este processo garante a autenticidade e integridade do documento, fornecendo evidências de aprovação ou concordância.

#### P: Posso criar e assinar várias linhas de assinatura em um documento do Word usando Aspose.Words for .NET?

R: Sim, você pode criar e assinar várias linhas de assinatura em um documento do Word usando Aspose.Words for .NET. Cada linha de assinatura pode ter seu próprio ID e opções exclusivas. Você pode repetir as etapas para criar e assinar linhas de assinatura adicionais no documento.

#### P: Posso modificar a linha de assinatura ou adicionar informações adicionais depois de assinada?

R: Depois que uma linha de assinatura for assinada, ela se tornará parte do conteúdo do documento e não poderá ser modificada separadamente. No entanto, você pode adicionar informações ou conteúdo adicional após a linha de assinatura assinada.

#### P: Posso verificar a assinatura digital de um documento que contém uma linha de assinatura?

 R: Sim, Aspose.Words for .NET fornece funcionalidade para verificar a assinatura digital de um documento que contém uma linha de assinatura. Você pode usar o`DigitalSignatureUtil.Verify` método para verificar a validade e autenticidade da assinatura digital.

#### P: Qual formato de arquivo o Aspose.Words for .NET suporta para criar e assinar linhas de assinatura?

R: Aspose.Words for .NET suporta a criação e assinatura de linhas de assinatura no formato de arquivo DOCX. Você pode criar e assinar linhas de assinatura em arquivos DOCX usando os métodos e classes fornecidos.