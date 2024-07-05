---
title: Converter Docx em Mhtml e enviar e-mail
linktitle: Converter Docx em Mhtml e enviar e-mail
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter DOCX em MHTML e enviar e-mails usando Aspose.Words for .NET neste guia passo a passo. Aumente sua produtividade com automação fácil.
type: docs
weight: 10
url: /pt/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Introdução

Na era digital de hoje, converter documentos de um formato para outro e enviá-los por e-mail é uma tarefa comum. Este artigo orientará você no processo de conversão de um arquivo DOCX para o formato MHTML e, em seguida, enviá-lo por e-mail usando Aspose.Words for .NET. Descreveremos cada etapa em um guia detalhado e fácil de seguir, garantindo que você entenda o processo do início ao fim. Vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:

1. Aspose.Words for .NET: Baixe e instale a biblioteca Aspose.Words for .NET do[Página de lançamentos do Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email for .NET: Baixe e instale a biblioteca Aspose.Email for .NET do[Página de lançamentos do Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: certifique-se de ter o .NET Framework instalado em sua máquina.
4. Servidor SMTP: Você precisa de acesso a um servidor SMTP para enviar e-mails.

## Importar namespaces

Para usar Aspose.Words e Aspose.Email em seu projeto, você precisa importar os namespaces necessários. Adicione o seguinte usando diretivas na parte superior do seu arquivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Vamos dividir o processo em várias etapas para garantir que você entenda cada parte claramente.

## Etapa 1: carregue o documento DOCX

 Primeiro, você precisa carregar o documento DOCX que deseja converter. Use o`Document` class de Aspose.Words para carregar seu arquivo DOCX.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Etapa 2: salve o documento como MHTML

 A seguir, salve o documento carregado como um arquivo MHTML. Isto é feito usando o`Save` método do`Document` aula.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Retroceda o fluxo até o início para que Aspose.Email possa lê-lo.
stream.Position = 0;
```

## Etapa 3: crie uma mensagem de e-mail

Agora, crie uma mensagem de email a partir do fluxo MHTML usando Aspose.Email. Você usará o`MailMessage` aula para esse fim.

```csharp
// Crie uma mensagem de email MIME Aspose.Email do stream.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Etapa 4: envie o e-mail

 Por fim, envie o email usando um cliente SMTP. Configure o cliente SMTP com os detalhes do seu servidor SMTP e use o`Send` método para enviar a mensagem.

```csharp
// Envie a mensagem usando Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Conclusão

Parabéns! Você converteu com sucesso um documento DOCX para MHTML e o enviou por e-mail usando Aspose.Words for .NET. Este processo envolve carregar o documento, convertê-lo para MHTML, criar uma mensagem de email e enviá-la usando um cliente SMTP. Com essas etapas, você pode automatizar facilmente a conversão e o envio de documentos por e-mail em seus aplicativos.

## Perguntas frequentes

### Posso usar este método para converter outros formatos de documentos?
Sim, Aspose.Words suporta vários formatos e você pode converter documentos como DOC, DOCX, RTF e muito mais para MHTML.

### Como posso adicionar anexos ao e-mail?
 Você pode usar o`Attachments` propriedade do`MailMessage`class para adicionar anexos ao seu e-mail.

### O Aspose.Words é compatível com o .NET Core?
Sim, Aspose.Words é compatível com .NET Core. Você também pode usá-lo em aplicativos .NET Core.

### Preciso de uma licença para Aspose.Words e Aspose.Email?
 Sim, ambas as bibliotecas exigem licenças. Você pode obter uma licença temporária do[Aspose página de compra](https://purchase.aspose.com/temporary-license/) para fins de avaliação.

### Onde posso encontrar mais documentação?
 Você pode encontrar documentação detalhada para Aspose.Words[aqui](https://reference.aspose.com/words/net/) e para Aspose.Email[aqui](https://reference.aspose.com/email/net/).
