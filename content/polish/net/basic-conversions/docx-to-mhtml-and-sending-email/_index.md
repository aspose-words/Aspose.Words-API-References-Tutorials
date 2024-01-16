---
title: Konwertuj Docx na Mhtml i wysyłaj wiadomości e-mail
linktitle: Konwertuj Docx na Mhtml i wysyłaj wiadomości e-mail
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak konwertować dokumenty programu Word z Docx na MHTML i wysyłać je jako wiadomości e-mail za pomocą Aspose.Words i Aspose.Email. Samouczek krok po kroku.
type: docs
weight: 10
url: /pl/net/basic-conversions/docx-to-mhtml-and-sending-email/
---

W tym samouczku krok po kroku poprowadzimy Cię, jak używać Aspose.Words dla .NET do konwersji dokumentu Word w formacie Docx na MHTML i wysłać go jako wiadomość e-mail za pomocą Aspose.Email. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowane i skonfigurowane biblioteki Aspose.Words dla .NET i Aspose.Email w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj biblioteki z[Aspose.Wydaje](https://releases.aspose.com/words/net/).

## Krok 1: Inicjowanie obiektu dokumentu

 Najpierw zainicjuj`Document`obiekt ze ścieżką do dokumentu źródłowego w formacie Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Krok 2: Zapisywanie dokumentu w formacie MHTML

 Następnie zapisz dokument w formacie`Stream` obiekt w formacie MHTML:

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);
```

## Krok 3: Przewijanie strumienia

Ponieważ Aspose.Email musi przeczytać strumień od początku, przewiń strumień do początku:

```csharp
stream.Position = 0;
```

## Krok 4: Tworzenie wiadomości MIME Aspose.Email

 Stwórz`MailMessage` obiekt ze strumienia za pomocą`MhtmlLoadOptions`:

```csharp
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

Możesz dostosować właściwości wiadomości, takie jak nadawca, odbiorca i temat.

## Krok 5: Wysyłanie wiadomości e-mail

 Użyj Aspose.Email`SmtpClient` aby wysłać e-mail:

```csharp
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

Upewnij się, że podałeś poprawny adres hosta serwera SMTP.

Otóż to! Pomyślnie przekonwertowałeś dokument programu Word w formacie Docx na MHTML i wysłałeś go jako wiadomość e-mail przy użyciu Aspose.Words dla .NET i Aspose.Email.

### Przykładowy kod źródłowy dla Docx do Mhtml i wysyłania wiadomości e-mail przy użyciu Aspose.Words dla .NET

```csharp

	// Dokument doc = nowy dokument (Mój katalog + „Dokument.docx”);

	Stream stream = new MemoryStream();
	doc.Save(stream, SaveFormat.Mhtml);

	//Przewiń strumień na początek, aby Aspose.Email mógł go przeczytać.
	stream.Position = 0;

	// Utwórz wiadomość e-mail MIME Aspose.Email ze strumienia.
	MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
	message.From = "your_from@email.com";
	message.To = "your_to@email.com";
	message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";

	// Wyślij wiadomość za pomocą Aspose.Email.
	SmtpClient client = new SmtpClient();
	client.Host = "your_smtp.com";
	client.Send(message);
	
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go zgodnie ze swoimi specyficznymi wymaganiami.

### Często zadawane pytania

#### Jak przekonwertować plik DOCX na MHTML?

Aby przekonwertować plik DOCX na MHTML, można skorzystać z narzędzi programowych lub bibliotek zapewniających tę funkcję. Aspose.Words dla .NET jest niezawodną opcją dla tej konwersji. Możesz użyć API biblioteki, aby załadować plik DOCX i zapisać go w formacie MHTML.

#### Jak wysłać wiadomość e-mail z załącznikiem w postaci pliku MHTML?

Aby wysłać wiadomość e-mail zawierającą plik MHTML jako załącznik, można skorzystać z bibliotek lub narzędzi specyficznych dla wysyłania wiadomości e-mail, takich jak System.Net.Mail w środowisku .NET. Musisz utworzyć wiadomość e-mail, określić odbiorcę, temat i treść, a następnie dodać plik MHTML jako załącznik do wiadomości przed jej wysłaniem.

#### Jakie są ograniczenia procesu konwersji i wysyłania wiadomości e-mail?

Ograniczenia procesu konwersji i wysyłania wiadomości e-mail zależą od konkretnych narzędzi, z których korzystasz. Niektóre narzędzia mogą mieć ograniczenia związane z rozmiarem pliku, ustawieniami zabezpieczeń lub obsługiwanymi protokołami poczty e-mail. Ważne jest, aby wybrać narzędzia odpowiadające swoim potrzebom i uwzględnić te ograniczenia podczas wdrażania.

#### Czy Aspose to niezawodne narzędzie do konwersji DOCX na MHTML i wysyłania wiadomości e-mail?

Tak, Aspose.Words dla .NET to niezawodne narzędzie do konwersji DOCX na MHTML i wysyłania wiadomości e-mail. Jest szeroko stosowany przez programistów i profesjonalistów ze względu na jego wydajność i jakość. Narzędzie oferuje obszerną dokumentację, zaawansowane funkcje i dedykowaną pomoc techniczną, dzięki czemu jest rekomendowanym wyborem do tego typu zadań.