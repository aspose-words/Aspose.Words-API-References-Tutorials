---
title: Konwertuj Docx na Mhtml i wysyłaj wiadomości e-mail
linktitle: Konwertuj Docx na Mhtml i wysyłaj wiadomości e-mail
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak konwertować DOCX na MHTML i wysyłać e-maile za pomocą Aspose.Words dla .NET w tym przewodniku krok po kroku. Zwiększ swoją produktywność dzięki łatwej automatyzacji.
type: docs
weight: 10
url: /pl/net/basic-conversions/docx-to-mhtml-and-sending-email/
---
## Wstęp

W dzisiejszej erze cyfrowej konwertowanie dokumentów z jednego formatu na inny i wysyłanie ich pocztą elektroniczną jest częstym zadaniem. Ten artykuł przeprowadzi Cię przez proces konwertowania pliku DOCX do formatu MHTML, a następnie wysyłania go jako wiadomości e-mail za pomocą Aspose.Words dla .NET. Każdy krok omówimy w szczegółowym, łatwym do zrozumienia przewodniku, dzięki któremu zrozumiesz proces od początku do końca. Zanurzmy się!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Aspose.Words dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Words dla .NET z[Strona z wydaniami Aspose](https://releases.aspose.com/words/net/).
2.  Aspose.Email dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Email dla .NET z[Strona z wydaniami Aspose](https://releases.aspose.com/email/net/).
3. .NET Framework: Upewnij się, że na komputerze jest zainstalowana platforma .NET Framework.
4. Serwer SMTP: Aby wysyłać e-maile, potrzebujesz dostępu do serwera SMTP.

## Importuj przestrzenie nazw

Aby używać Aspose.Words i Aspose.Email w swoim projekcie, musisz zaimportować niezbędne przestrzenie nazw. Dodaj następujące dyrektywy using na górze pliku C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Email;
using Aspose.Email.Mime;
using Aspose.Email.Clients.Smtp;
```

Podzielmy proces na wiele etapów, aby mieć pewność, że dobrze zrozumiesz każdą część.

## Krok 1: Załaduj dokument DOCX

 Najpierw musisz załadować dokument DOCX, który chcesz przekonwertować. Użyj`Document` class z Aspose.Words, aby załadować plik DOCX.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Krok 2: Zapisz dokument jako MHTML

 Następnie zapisz załadowany dokument jako plik MHTML. Odbywa się to za pomocą`Save` metoda`Document` klasa.

```csharp
Stream stream = new MemoryStream();
doc.Save(stream, SaveFormat.Mhtml);

// Przewiń strumień na początek, aby Aspose.Email mógł go przeczytać.
stream.Position = 0;
```

## Krok 3: Utwórz wiadomość e-mail

Teraz utwórz wiadomość e-mail ze strumienia MHTML za pomocą Aspose.Email. Będziesz korzystać z`MailMessage` klasę w tym celu.

```csharp
// Utwórz wiadomość e-mail MIME Aspose.Email ze strumienia.
MailMessage message = MailMessage.Load(stream, new MhtmlLoadOptions());
message.From = "your_from@email.com";
message.To = "your_to@email.com";
message.Subject = "Aspose.Words + Aspose.Email MHTML Test Message";
```

## Krok 4: Wyślij e-mail

 Na koniec wyślij wiadomość e-mail za pomocą klienta SMTP. Skonfiguruj klienta SMTP, podając szczegóły serwera SMTP i użyj pliku`Send` sposób wysłania wiadomości.

```csharp
// Wyślij wiadomość za pomocą Aspose.Email.
SmtpClient client = new SmtpClient();
client.Host = "your_smtp.com";
client.Send(message);
```

## Wniosek

Gratulacje! Pomyślnie przekonwertowałeś dokument DOCX na MHTML i wysłałeś go e-mailem za pomocą Aspose.Words dla .NET. Proces ten obejmuje załadowanie dokumentu, konwersję do formatu MHTML, utworzenie wiadomości e-mail i wysłanie jej za pomocą klienta SMTP. Wykonując te czynności, możesz łatwo zautomatyzować konwersję i wysyłanie dokumentów pocztą elektroniczną w swoich aplikacjach.

## Często zadawane pytania

### Czy mogę użyć tej metody do konwersji innych formatów dokumentów?
Tak, Aspose.Words obsługuje różne formaty i możesz konwertować dokumenty takie jak DOC, DOCX, RTF i inne do MHTML.

### Jak mogę dodać załączniki do wiadomości e-mail?
 Możesz skorzystać z`Attachments` własność`MailMessage`class, aby dodać załączniki do wiadomości e-mail.

### Czy Aspose.Words jest kompatybilny z .NET Core?
Tak, Aspose.Words jest kompatybilny z .NET Core. Można go również używać w aplikacjach .NET Core.

### Czy potrzebuję licencji na Aspose.Words i Aspose.Email?
 Tak, obie biblioteki wymagają licencji. Możesz uzyskać tymczasową licencję od[Strona zakupu Aspose](https://purchase.aspose.com/temporary-license/) w celach ewaluacyjnych.

### Gdzie mogę znaleźć więcej dokumentacji?
 Możesz znaleźć szczegółową dokumentację dla Aspose.Words[Tutaj](https://reference.aspose.com/words/net/) i dla Aspose.Email[Tutaj](https://reference.aspose.com/email/net/).
