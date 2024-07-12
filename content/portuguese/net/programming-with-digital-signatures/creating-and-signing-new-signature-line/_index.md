---
title: Criação e assinatura de nova linha de assinatura
linktitle: Criação e assinatura de nova linha de assinatura
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar e assinar digitalmente uma linha de assinatura em um documento do Word usando Aspose.Words for .NET com este tutorial passo a passo. Perfeito para automação de documentos.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Introdução

Ei! Então, você tem um documento do Word e precisa adicionar uma linha de assinatura e assiná-lo digitalmente. Parece complicado? De jeito nenhum! Graças ao Aspose.Words for .NET, você pode conseguir isso perfeitamente com apenas algumas linhas de código. Neste tutorial, orientaremos você por todo o processo, desde a configuração do seu ambiente até salvar seu documento com uma assinatura novinha em folha. Preparar? Vamos mergulhar!

## Pré-requisitos

Antes de entrarmos no código, vamos ter certeza de que você tem tudo o que precisa:
1.  Aspose.Words para .NET - Você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Um ambiente de desenvolvimento .NET – Visual Studio é altamente recomendado.
3. Um documento para assinar - Crie um documento simples do Word ou use um já existente.
4.  Um arquivo de certificado – necessário para assinaturas digitais. Você pode usar um`.pfx` arquivo.
5. Imagens para Linha de Assinatura - Opcionalmente, um arquivo de imagem para a assinatura.

## Importar namespaces

Primeiro, precisamos importar os namespaces necessários. Esta etapa é crucial, pois configura o ambiente para uso das funcionalidades do Aspose.Words.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Etapa 1: configurando o diretório de documentos

Todo projeto precisa de um bom começo. Vamos configurar o caminho para o diretório do seu documento. É aqui que seus documentos serão salvos e recuperados.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Criando um Novo Documento

Agora, vamos criar um novo documento do Word usando Aspose.Words. Esta será a nossa tela onde adicionaremos a linha de assinatura.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: Inserindo a Linha de Assinatura

 É aqui que a mágica acontece. Inserimos uma linha de assinatura em nosso documento usando o`DocumentBuilder` aula.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Passo 4: Salvando o Documento com a Linha de Assinatura

Assim que a linha de assinatura estiver instalada, precisamos salvar o documento. Esta é uma etapa intermediária antes de prosseguirmos com a assinatura.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Etapa 5: configurar opções de assinatura

Agora, vamos configurar as opções de assinatura do documento. Isso inclui a especificação do ID da linha de assinatura e da imagem a ser usada.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Etapa 6: Carregando o Certificado

As assinaturas digitais requerem um certificado. Aqui carregamos o arquivo do certificado que será utilizado para assinar o documento.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Passo 7: Assinando o Documento

 Esta é a etapa final. Nós usamos o`DigitalSignatureUtil`turma para assinar o documento. O documento assinado é salvo com um novo nome.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Conclusão

E aí está! Com essas etapas, você criou com êxito um novo documento do Word, adicionou uma linha de assinatura e o assinou digitalmente usando Aspose.Words for .NET. É uma ferramenta poderosa que facilita muito a automação de documentos. Esteja você lidando com contratos, acordos ou quaisquer documentos formais, esse método garante que eles sejam assinados e autenticados com segurança.

## Perguntas frequentes

### Posso usar outros formatos de imagem para a linha de assinatura?
Sim, você pode usar vários formatos de imagem como PNG, JPG, BMP, etc.

###  É necessário usar um`.pfx` file for the certificate?
 Sim, um`.pfx` file é um formato comum para armazenar informações criptográficas, incluindo certificados e chaves privadas.

### Posso adicionar várias linhas de assinatura em um único documento?
Absolutamente! Você pode inserir várias linhas de assinatura repetindo a etapa de inserção para cada assinatura.

### E se eu não tiver um certificado digital?
Você precisará obter um certificado digital de uma autoridade de certificação confiável ou gerar um usando ferramentas como OpenSSL.

### Como verifico a assinatura digital no documento?
Você pode abrir o documento assinado no Word e acessar os detalhes da assinatura para verificar a autenticidade e integridade da assinatura.