---
title: Docx en Mhtml et envoi d'e-mail
linktitle: Docx en Mhtml et envoi d'e-mail
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à convertir des documents Word de Docx en MHTML et à les envoyer sous forme d'e-mails à l'aide d'Aspose.Words et d'Aspose.Email. Tutoriel étape par étape.
type: docs
weight: 10
url: /fr/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

Dans ce didacticiel étape par étape, nous vous expliquerons comment utiliser Aspose.Words pour .NET pour convertir un document Word au format Docx en MHTML et l'envoyer par e-mail à l'aide d'Aspose.Email. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets.

Pour commencer, assurez-vous que les bibliothèques Aspose.Words pour .NET et Aspose.Email sont installées et configurées dans votre environnement de développement. Si vous ne l'avez pas encore fait, téléchargez et installez les bibliothèques à partir de leurs sites Web officiels.

## Étape 1 : Initialisation de l'objet Document

 Tout d'abord, initialisez le`Document` object avec le chemin vers votre document source au format Docx :

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Étape 2 : Enregistrer le document au format MHTML

 Ensuite, enregistrez le document dans un`Stream` objet au format MHTML :

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Étape 3 : Rembobiner le flux

Comme Aspose.Email doit lire le flux depuis le début, rembobinez le flux jusqu'au début :

```csharp
stream.Position = 0;
```

## Étape 4 : Création d'un message MIME Aspose.Email

 Créer un`MailMessage` objet du flux en utilisant`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

N'hésitez pas à personnaliser les propriétés du message telles que l'expéditeur, le destinataire et l'objet.

## Étape 5 : Envoi de l'e-mail

 Utilisez Aspose.Email`SmtpClient` pour envoyer le mail :

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Assurez-vous de fournir l'adresse hôte du serveur SMTP correcte.

C'est ça! Vous avez converti avec succès un document Word au format Docx en MHTML et l'avez envoyé par e-mail à l'aide de Aspose.Words pour .NET et Aspose.Email.

### Exemple de code source pour Docx To Mhtml And Sending Email using Aspose.Words for .NET

```csharp

	// Document doc = new Document(MyDir + "Document.docx");

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	// Rembobinez le flux jusqu'au début pour qu'Aspose.Email puisse le lire.
	stream.Position = 0;

	// Créez un message électronique Aspose.Email MIME à partir du flux.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Envoyez le message en utilisant Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

N'hésitez pas à utiliser ce code dans vos propres projets et à le modifier en fonction de vos besoins spécifiques.