---
title: Assinando linha de assinatura existente em documento do Word
linktitle: Assinando linha de assinatura existente em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como assinar uma linha de assinatura existente em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Neste tutorial, orientaremos você nas etapas para usar o recurso de assinatura de uma linha de assinatura existente com Aspose.Words for .NET. Este recurso permite assinar digitalmente uma linha de assinatura já presente em um documento Word. Siga os passos abaixo:

## Passo 1: Carregando o documento e acessando a linha de assinatura

Comece enviando o documento que contém a linha de assinatura existente:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Etapa 2: definir opções de assinatura

Crie uma instância da classe SignOptions e defina as opções de assinatura, incluindo o ID da linha de assinatura e a imagem da linha de assinatura:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Certifique-se de especificar o caminho correto para a imagem da linha de assinatura.

## Etapa 3: Carregando o certificado

Comece carregando o certificado de assinatura usando a classe CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Certifique-se de especificar o caminho correto para o seu certificado e a senha associada.

## Passo 4: Assinando a linha de assinatura existente

Use a classe DigitalSignatureUtil para assinar a linha de assinatura existente:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Certifique-se de especificar os caminhos corretos para o documento de origem, o documento assinado e o certificado.

### Exemplo de código-fonte para assinar linha de assinatura existente usando Aspose.Words for .NET

Aqui está o código-fonte completo para assinar uma linha de assinatura existente com Aspose.Words for .NET:


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Seguindo essas etapas, você pode assinar facilmente uma linha de assinatura existente em um documento do Word com Aspose.Words for .NET.

## Conclusão

Neste tutorial, aprendemos como assinar uma linha de assinatura existente em um documento do Word usando Aspose.Words for .NET. Seguindo as etapas fornecidas, você pode carregar facilmente o documento, acessar a linha de assinatura existente, definir as opções de assinatura e assinar o documento. A capacidade de assinar uma linha de assinatura existente oferece uma maneira conveniente de adicionar assinaturas digitais a áreas predefinidas em seus documentos do Word, garantindo a integridade e a autenticação do documento. Aspose.Words for .NET oferece uma API poderosa para processamento de palavras com assinaturas digitais, permitindo personalizar o processo de assinatura e aumentar a segurança de seus documentos Word.

### Perguntas frequentes

#### P: O que é uma linha de assinatura existente em um documento do Word?

R: Uma linha de assinatura existente em um documento do Word é uma área predefinida onde uma assinatura pode ser colocada. Normalmente é representado por uma forma ou objeto no documento e serve como um espaço designado para o signatário adicionar sua assinatura digital.

#### P: Como posso assinar uma linha de assinatura existente em um documento do Word usando Aspose.Words for .NET?

R: Para assinar uma linha de assinatura existente em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:
1.  Carregue o documento usando o`Document` class e especifique o caminho para o arquivo do documento.
2.  Acesse a linha de assinatura existente usando o método ou propriedade apropriada. Por exemplo, você pode usar`GetChild` método para recuperar a forma da linha de assinatura.
3.  Crie uma instância do`SignOptions` classe e definir o`SignatureLineId` propriedade ao ID da linha de assinatura existente.
4.  Colocou o`SignatureLineImage` propriedade do`SignOptions` class para a imagem que representa a assinatura digital.
5.  Carregue o certificado de assinatura usando o`CertificateHolder` class e forneça o certificado e a senha necessários.
6.  Use o`DigitalSignatureUtil.Sign` método para assinar o documento, fornecendo os parâmetros necessários incluindo o`SignOptions` objeto.

#### P: Como faço para acessar a linha de assinatura existente em um documento do Word usando Aspose.Words for .NET?

 R: Para acessar a linha de assinatura existente em um documento do Word usando Aspose.Words for .NET, você pode usar o método ou propriedade apropriado para recuperar o formato da linha de assinatura da estrutura do documento. Por exemplo, você pode usar o`GetChild` método com os parâmetros apropriados para obter o formato de linha de assinatura desejado.

#### P: Posso personalizar a aparência da assinatura digital em uma linha de assinatura existente?

R: Sim, você pode personalizar a aparência da assinatura digital em uma linha de assinatura existente fornecendo um arquivo de imagem representando a assinatura. A imagem pode ser um logotipo, uma assinatura manuscrita ou qualquer outra representação gráfica da assinatura. Você pode definir o`SignatureLineImage` propriedade do`SignOptions` class para os bytes do arquivo de imagem.

#### P: Posso assinar várias linhas de assinatura existentes em um documento do Word?
 R: Sim, você pode assinar várias linhas de assinatura existentes em um documento do Word. Você precisa seguir as etapas para cada linha de assinatura individualmente, definindo o apropriado`SignatureLineId` e`SignatureLineImage` valores no`SignOptions` objeto para cada linha de assinatura.

#### P: Qual deve ser o formato do arquivo de imagem para a assinatura digital em uma linha de assinatura existente?

 R: O arquivo de imagem para a assinatura digital em uma linha de assinatura existente pode estar em vários formatos, como PNG, JPEG, BMP ou GIF. Você pode especificar o caminho do arquivo ou ler os bytes do arquivo de imagem e atribuí-lo ao`SignatureLineImage` propriedade do`SignOptions` aula.
