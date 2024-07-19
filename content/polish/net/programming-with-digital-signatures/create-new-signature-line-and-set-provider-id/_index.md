---
title: Utwórz nową linię podpisu i ustaw identyfikator dostawcy
linktitle: Utwórz nową linię podpisu i ustaw identyfikator dostawcy
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć nową linię podpisu i ustawić identyfikator dostawcy w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Przewodnik krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Wstęp

Hej, miłośnicy technologii! Czy zastanawiałeś się kiedyś, jak programowo dodać linię podpisu do dokumentów programu Word? Cóż, dzisiaj zajmiemy się właśnie tym, używając Aspose.Words dla .NET. Ten przewodnik przeprowadzi Cię przez każdy krok, dzięki czemu utworzenie nowej linii podpisu i ustawienie identyfikatora dostawcy w dokumentach programu Word będzie niezwykle proste. Niezależnie od tego, czy automatyzujesz przetwarzanie dokumentów, czy po prostu chcesz usprawnić przepływ pracy, ten samouczek pomoże Ci.

## Warunki wstępne

Zanim ubrudzimy sobie ręce, upewnijmy się, że mamy wszystko, czego potrzebujemy:

1.  Aspose.Words dla .NET: Jeśli jeszcze tego nie zrobiłeś, pobierz go[Tutaj](https://releases.aspose.com/words/net/).
2. Środowisko programistyczne: Visual Studio lub dowolne inne środowisko programistyczne C#.
3. .NET Framework: Upewnij się, że masz zainstalowaną platformę .NET Framework.
4. Certyfikat PFX: Do podpisywania dokumentów potrzebny będzie certyfikat PFX. Można go uzyskać od zaufanego urzędu certyfikacji.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw do Twojego projektu C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

No dobrze, przejdźmy do konkretów. Oto szczegółowy opis każdego kroku tworzenia nowej linii podpisu i ustawiania identyfikatora dostawcy.

## Krok 1: Utwórz nowy dokument

Na początek musimy utworzyć nowy dokument Word. To będzie płótno dla naszej linii podpisu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 W tym fragmencie inicjujemy nowy plik`Document` i a`DocumentBuilder` . The`DocumentBuilder` pomaga nam dodawać elementy do naszego dokumentu.

## Krok 2: Zdefiniuj opcje linii podpisu

Następnie definiujemy opcje naszej linii podpisu. Obejmuje to imię i nazwisko osoby podpisującej, stanowisko, adres e-mail i inne szczegóły.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Opcje te personalizują linię podpisu, czyniąc ją przejrzystą i profesjonalną.

## Krok 3: Wstaw linię podpisu

Po ustawieniu opcji możemy teraz wstawić linię podpisu do dokumentu.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Tutaj`InsertSignatureLine` metoda dodaje linię podpisu i przypisujemy do niej unikalny identyfikator dostawcy.

## Krok 4: Zapisz dokument

Po wstawieniu linii podpisu zapiszmy dokument.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Spowoduje to zapisanie dokumentu z nowo dodaną linią podpisu.

## Krok 5: Skonfiguruj opcje podpisywania

Teraz musimy skonfigurować opcje podpisywania dokumentu. Obejmuje to identyfikator linii podpisu, identyfikator dostawcy, komentarze i czas podpisania.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Opcje te zapewniają, że dokument zostanie podpisany przy użyciu prawidłowych szczegółów.

## Krok 6: Utwórz posiadacza certyfikatu

Do podpisania dokumentu użyjemy certyfikatu PFX. Stwórzmy dla niego posiadacza certyfikatu.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Pamiętaj o wymianie`"morzal.pfx"` z rzeczywistym plikiem certyfikatu i`"aw"` za pomocą hasła do certyfikatu.

## Krok 7: Podpisz dokument

Na koniec podpisujemy dokument za pomocą narzędzia do podpisu cyfrowego.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Spowoduje to podpisanie dokumentu i zapisanie go jako nowego pliku.

## Wniosek

I masz to! Pomyślnie utworzyłeś nową linię podpisu i ustawiłeś identyfikator dostawcy w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Ta potężna biblioteka niezwykle ułatwia zarządzanie zadaniami przetwarzania dokumentów i ich automatyzację. Wypróbuj i przekonaj się, jak może usprawnić Twój przepływ pracy.

## Często zadawane pytania

### Czy mogę dostosować wygląd linii podpisu?
Absolutnie! Możesz dostosować różne opcje w pliku`SignatureLineOptions` do Twoich potrzeb.

### Co się stanie, jeśli nie mam certyfikatu PFX?
Musisz go uzyskać od zaufanego urzędu certyfikacji. Jest to niezbędne do cyfrowego podpisywania dokumentów.

### Czy mogę dodać wiele linii podpisu do dokumentu?
Tak, możesz dodać dowolną liczbę wierszy podpisu, powtarzając proces wstawiania z różnymi opcjami.

### Czy Aspose.Words dla .NET jest kompatybilny z .NET Core?
Tak, Aspose.Words dla .NET obsługuje .NET Core, dzięki czemu jest wszechstronny w różnych środowiskach programistycznych.

### Jak bezpieczne są podpisy cyfrowe?
Podpisy cyfrowe utworzone za pomocą Aspose.Words są bardzo bezpieczne, pod warunkiem, że użyjesz ważnego i zaufanego certyfikatu.