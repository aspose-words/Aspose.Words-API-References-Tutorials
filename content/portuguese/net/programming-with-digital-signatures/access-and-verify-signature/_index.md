---
title: Acesse e verifique a assinatura em um documento do Word
linktitle: Acesse e verifique a assinatura em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Acesse e verifique assinaturas digitais em documentos do Word usando Aspose.Words for .NET com este guia passo a passo abrangente. Garanta a autenticidade do documento sem esforço.
type: docs
weight: 10
url: /pt/net/programming-with-digital-signatures/access-and-verify-signature/
---
## Introdução

Olá, colegas entusiastas da tecnologia! Você já se viu em uma situação em que precisava acessar e verificar assinaturas digitais em um documento do Word, mas não sabia por onde começar? Bem, você está com sorte! Hoje, estamos mergulhando no maravilhoso mundo do Aspose.Words for .NET, uma biblioteca poderosa que facilita muito o manuseio de documentos do Word. Iremos orientá-lo passo a passo no processo, portanto, ao final deste guia, você será um profissional na verificação de assinaturas digitais em documentos do Word. Vamos começar!

## Pré-requisitos

Antes de mergulharmos nos detalhes essenciais, há algumas coisas que você precisa ter em mente:

1. Visual Studio: certifique-se de ter o Visual Studio instalado em sua máquina. É aqui que você escreverá e executará seu código.
2.  Aspose.Words for .NET: Você precisará ter o Aspose.Words for .NET instalado. Você pode baixá-lo[aqui](https://releases.aspose.com/words/net/) . Não se esqueça de fazer seu teste gratuito[aqui](https://releases.aspose.com/) se você ainda não o fez!
3. Um documento Word assinado digitalmente: Tenha um documento Word que já esteja assinado digitalmente. Este é o arquivo com o qual você trabalhará para verificar as assinaturas.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Esses namespaces permitirão que você use os recursos Aspose.Words em seu projeto.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.DigitalSignatures;
```

Tudo bem, vamos dividir isso em etapas gerenciáveis. Cada etapa o guiará por uma parte específica do processo. Preparar? Vamos!

## Etapa 1: configure seu projeto

Antes de verificar uma assinatura digital, você precisa configurar seu projeto no Visual Studio. Veja como:

### Crie um novo projeto

1. Abra o Visual Studio.
2. Clique em Criar um novo projeto.
3. Selecione Aplicativo de console (.NET Core) ou Aplicativo de console (.NET Framework), dependendo de sua preferência.
4. Clique em Avançar, dê um nome ao seu projeto e clique em Criar.

### Instale Aspose.Words para .NET

1. No Solution Explorer, clique com o botão direito no nome do seu projeto e selecione Gerenciar pacotes NuGet.
2. No Gerenciador de pacotes NuGet, pesquise Aspose.Words.
3. Clique em Instalar para adicioná-lo ao seu projeto.

## Etapa 2: carregar o documento Word assinado digitalmente

Agora que seu projeto está configurado, vamos carregar o documento Word assinado digitalmente.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento. Este trecho de código inicializa um novo`Document` objeto e carrega seu documento do Word assinado.

## Passo 3: Acesse as Assinaturas Digitais

Com o seu documento carregado, é hora de acessar as assinaturas digitais.

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine("* Signature Found *");
    Console.WriteLine("Is valid: " + signature.IsValid);
    Console.WriteLine("Reason for signing: " + signature.Comments); 
    Console.WriteLine("Time of signing: " + signature.SignTime);
    Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
    Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
    Console.WriteLine();
}
```

Este código percorre cada assinatura digital do documento e imprime vários detalhes sobre a assinatura. Vamos detalhar o que cada parte faz:

1. Assinatura encontrada: indica que uma assinatura foi encontrada.
2. É válido: verifica se a assinatura é válida.
3. Motivo da assinatura: Exibe o motivo da assinatura, se disponível.
4. Hora da assinatura: Mostra a hora em que o documento foi assinado.
5. Nome do assunto: recupera o nome do assunto do certificado.
6. Nome do emissor: recupera o nome do emissor do certificado.

## Etapa 4: execute seu código

Com tudo configurado, é hora de executar seu código e ver os resultados.


1. Pressione F5 ou clique no botão Iniciar no Visual Studio para executar seu programa.
2. Se o seu documento estiver assinado digitalmente, você verá os detalhes da assinatura impressos no console.

## Etapa 5: lidar com erros potenciais

É sempre uma boa ideia lidar com quaisquer erros potenciais que possam ocorrer. Vamos adicionar algum tratamento básico de erros ao nosso código.

```csharp
try
{
    // O caminho para o diretório de documentos.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
    Document doc = new Document(dataDir + "Digitally signed.docx");

    foreach (DigitalSignature signature in doc.DigitalSignatures)
    {
        Console.WriteLine("* Signature Found *");
        Console.WriteLine("Is valid: " + signature.IsValid);
        Console.WriteLine("Reason for signing: " + signature.Comments); 
        Console.WriteLine("Time of signing: " + signature.SignTime);
        Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
        Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
        Console.WriteLine();
    }
}
catch (Exception ex)
{
    Console.WriteLine("An error occurred: " + ex.Message);
}
```

Isso capturará quaisquer exceções que possam ocorrer e imprimirá uma mensagem de erro.

## Conclusão

E aí está! Você acessou e verificou assinaturas digitais em um documento do Word usando Aspose.Words for .NET. Não é tão assustador quanto parece, certo? Com essas etapas, você pode lidar com assinaturas digitais em seus documentos do Word com segurança, garantindo sua autenticidade e integridade. Boa codificação!

## Perguntas frequentes

### Posso usar Aspose.Words for .NET para adicionar assinaturas digitais a um documento do Word?

Sim, você pode usar Aspose.Words for .NET para adicionar assinaturas digitais a documentos do Word. A biblioteca oferece recursos abrangentes para adicionar e verificar assinaturas digitais.

### Que tipos de assinaturas digitais o Aspose.Words for .NET pode verificar?

Aspose.Words for .NET pode verificar assinaturas digitais em arquivos DOCX que usam certificados X.509.

### O Aspose.Words for .NET é compatível com todas as versões do Microsoft Word?

Aspose.Words for .NET oferece suporte a todas as versões de documentos do Microsoft Word, incluindo DOC, DOCX, RTF e muito mais.

### Como obtenho uma licença temporária do Aspose.Words for .NET?

 Você pode obter uma licença temporária para Aspose.Words for .NET em[aqui](https://purchase.aspose.com/temporary-license/). Isso permite que você experimente todos os recursos da biblioteca sem quaisquer limitações.

### Onde posso encontrar mais documentação sobre Aspose.Words for .NET?

 Você pode encontrar documentação detalhada para Aspose.Words for .NET[aqui](https://reference.aspose.com/words/net/).