---
title: Converter Docx em Mhtml e enviar e-mail
linktitle: Converter Docx em Mhtml e enviar e-mail
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter documentos do Word de Docx para MHTML e enviá-los como e-mails usando Aspose.Words e Aspose.Email. Tutorial passo a passo.
type: docs
weight: 10
url: /pt/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

Neste tutorial passo a passo, iremos orientá-lo sobre como usar Aspose.Words for .NET para converter um documento Word no formato Docx para MHTML e enviá-lo como um e-mail usando Aspose.Email. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter as bibliotecas Aspose.Words for .NET e Aspose.Email instaladas e configuradas em seu ambiente de desenvolvimento. Caso ainda não tenha feito isso, baixe e instale as bibliotecas de[Aspose.Lançamentos](https://releases.aspose.com/words/net/).

## Etapa 1: inicializando o objeto Documento

 Primeiro, inicialize o`Document`objeto com o caminho para o seu documento de origem no formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Etapa 2: Salvar o documento no formato MHTML

 Em seguida, salve o documento em um`Stream` objeto em formato MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Etapa 3: retrocedendo o fluxo

Como Aspose.Email precisa ler o stream desde o início, retroceda o stream até o início:

```csharp
stream.Position = 0;
```

## Etapa 4: Criando uma mensagem MIME Aspose.Email

 Criar uma`MailMessage` objeto do fluxo usando`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Sinta-se à vontade para personalizar as propriedades da mensagem, como remetente, destinatário e assunto.

## Etapa 5: Enviando o e-mail

 Use Aspose.Email`SmtpClient` para enviar o e-mail:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Certifique-se de fornecer o endereço de host do servidor SMTP correto.

É isso! Você converteu com sucesso um documento do Word no formato Docx para MHTML e o enviou como um e-mail usando Aspose.Words for .NET e Aspose.Email.

### Exemplo de código-fonte para Docx To Mhtml e envio de e-mail usando Aspose.Words for .NET

```csharp

	// Documento doc = novo Documento(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Retroceda o fluxo até o início para que Aspose.Email possa lê-lo.
	stream.Position = 0;

	// Crie uma mensagem de email MIME Aspose.Email do stream.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Envie a mensagem usando Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo de acordo com suas necessidades específicas.

### Perguntas frequentes

#### Como converter um arquivo DOCX para MHTML?

Para converter um arquivo DOCX em MHTML, você pode usar ferramentas de software ou bibliotecas que fornecem essa funcionalidade. Aspose.Words for .NET é uma opção confiável para esta conversão. Você pode usar a API da biblioteca para carregar o arquivo DOCX e salvá-lo no formato MHTML.

#### Como envio um e-mail com um anexo de arquivo MHTML?

Para enviar um e-mail com um arquivo MHTML como anexo, você pode usar bibliotecas ou ferramentas específicas para envio de e-mail, como System.Net.Mail em .NET. Você deve criar uma mensagem de e-mail, especificar o destinatário, o assunto e o conteúdo e, em seguida, adicionar o arquivo MHTML como anexo à mensagem antes de enviá-la.

#### Quais são as limitações do processo de conversão e envio de e-mail?

As limitações do processo de conversão e envio de e-mail dependem das ferramentas específicas que você está usando. Algumas ferramentas podem ter restrições relacionadas ao tamanho do arquivo, configurações de segurança ou protocolos de e-mail suportados. É importante escolher ferramentas que atendam às suas necessidades e considerar essas limitações durante a implementação.

#### O Aspose é uma ferramenta confiável para conversão de DOCX em MHTML e envio de e-mail?

Sim, Aspose.Words for .NET é uma ferramenta confiável para conversão de DOCX em MHTML e envio de e-mail. É amplamente utilizado por desenvolvedores e profissionais por seu desempenho e qualidade. A ferramenta oferece documentação abrangente, recursos avançados e suporte técnico dedicado, tornando-a uma escolha recomendada para essas tarefas.