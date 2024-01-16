---
title: Uzyskaj dostęp i zweryfikuj podpis w dokumencie programu Word
linktitle: Uzyskaj dostęp i zweryfikuj podpis w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak uzyskać dostęp i zweryfikować podpisy cyfrowe w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/access-and-verify-signature/
---
W tym samouczku przeprowadzimy Cię przez kolejne kroki korzystania z funkcji weryfikacji dostępu i podpisu w Aspose.Words dla .NET. Ta funkcja umożliwia dostęp do podpisów cyfrowych w dokumencie programu Word i sprawdzanie ich ważności. Wykonaj poniższe kroki:

## Krok 1: Ładowanie dokumentu i uzyskiwanie dostępu do podpisów

Zacznij od przesłania dokumentu zawierającego podpisy cyfrowe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Krok 2: Przeglądaj podpisy cyfrowe

Użyj pętli, aby przejść przez wszystkie podpisy cyfrowe w dokumencie:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Uzyskaj dostęp do informacji o podpisie
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Ta właściwość jest dostępna tylko w dokumentach MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Pamiętaj, aby dostosować wyświetlane komunikaty do swoich potrzeb.

### Przykładowy kod źródłowy dostępu i weryfikacji podpisu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do weryfikacji dostępu i podpisu przy użyciu Aspose.Words dla .NET:

```csharp
	
	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Ta właściwość jest dostępna tylko w dokumentach MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Wykonując te kroki, będziesz mógł łatwo uzyskać dostęp do podpisów cyfrowych w dokumencie Word i zweryfikować je za pomocą Aspose.Words dla .NET.

## Wniosek

W tym samouczku zbadaliśmy funkcję uzyskiwania dostępu i weryfikowania podpisów cyfrowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Wykonując podane kroki, możesz łatwo załadować dokument, uzyskać dostęp do jego podpisów cyfrowych i zweryfikować ich ważność. Możliwość dostępu do podpisów cyfrowych i ich weryfikacji umożliwia zapewnienie integralności i autentyczności dokumentów programu Word. Aspose.Words dla .NET oferuje potężny interfejs API do przetwarzania tekstu z podpisami cyfrowymi, pozwalający zautomatyzować proces weryfikacji i zwiększyć bezpieczeństwo dokumentów.

### Często zadawane pytania

#### P: Czym są podpisy cyfrowe w dokumencie programu Word?

Odp.: Podpisy cyfrowe w dokumencie programu Word to podpisy elektroniczne umożliwiające uwierzytelnienie integralności i pochodzenia dokumentu. Tworzone są przy użyciu cyfrowych certyfikatów i algorytmów kryptograficznych, dzięki czemu odbiorcy mogą zweryfikować, czy dokument nie został zmieniony i czy pochodzi z zaufanego źródła.

#### P: Jak mogę uzyskać dostęp do podpisów cyfrowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby uzyskać dostęp do podpisów cyfrowych w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Załaduj dokument za pomocą`Document` class i określ ścieżkę do pliku dokumentu.
2.  Użyj pętli, aby iterować po`DigitalSignatures` zebranie dokumentu. Każda iteracja reprezentuje podpis cyfrowy.

#### P: Do jakich informacji mogę uzyskać dostęp dzięki podpisowi cyfrowemu w dokumencie programu Word?

Odp.: Za pomocą podpisu cyfrowego w dokumencie programu Word można uzyskać dostęp do różnych informacji, takich jak:
- Ważność: Sprawdź, czy podpis jest ważny.
- Uwagi: Uzyskaj powód podpisania podany przez osobę podpisującą.
- Czas podpisania: Uzyskaj czas podpisania dokumentu.
- Nazwa podmiotu: Pobierz nazwę osoby podpisującej lub podmiotu certyfikatu.
- Nazwa wystawcy: Pobierz nazwę wystawcy certyfikatu.

#### P: Czy mogę zweryfikować ważność podpisu cyfrowego w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Tak, możesz zweryfikować ważność podpisu cyfrowego w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Uzyskując dostęp do`IsValid` własność`DigitalSignature` obiektu, możesz określić, czy podpis jest ważny, czy nie.

#### P: Jak mogę zweryfikować ważność podpisów cyfrowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby zweryfikować ważność podpisów cyfrowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Uzyskać dostęp do`DigitalSignatures` zebranie dokumentu.
2.  Iteruj po każdym`DigitalSignature` obiekt w kolekcji.
3.  Użyj`IsValid` własność`DigitalSignature` obiekt, aby sprawdzić, czy podpis jest ważny.

#### P: Czy mogę odzyskać komentarze osoby podpisującej lub powód podpisania z podpisu cyfrowego w dokumencie programu Word?

Odpowiedź: Tak, możesz pobrać komentarze osoby podpisującej lub powód podpisania z podpisu cyfrowego w dokumencie programu Word. The`Comments` własność`DigitalSignature` obiekt zapewnia dostęp do komentarzy określonych przez osobę podpisującą w procesie podpisywania.

#### P: Jakiego rodzaju dokumenty obsługuje funkcja weryfikacji podpisu w Aspose.Words dla .NET?

Odp.: Funkcja weryfikacji podpisów w Aspose.Words dla .NET obsługuje weryfikację podpisów cyfrowych w dokumentach Word w formacie pliku DOCX. Możesz użyć tej funkcji do weryfikacji podpisów w plikach DOCX.

#### P: Jak mogę uzyskać dostęp do szczegółów certyfikatu podpisu cyfrowego w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby uzyskać dostęp do szczegółów certyfikatu podpisu cyfrowego w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz uzyskać dostęp do`CertificateHolder` własność`DigitalSignature` obiekt. Z`CertificateHolder` obiektu, możesz pobrać różne szczegóły certyfikatu, takie jak nazwa podmiotu i nazwa wystawcy.

#### P: Czy mogę dostosować wyświetlanie lub przetwarzanie podpisów cyfrowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Tak, możesz dostosować wyświetlanie lub przetwarzanie podpisów cyfrowych w dokumencie programu Word za pomocą Aspose.Words dla .NET. Uzyskując dostęp do właściwości i metod`DigitalSignature` obiekt, możesz wyodrębnić żądane informacje, przeprowadzić dodatkowe weryfikacje lub zintegrować proces weryfikacji podpisu z przepływem pracy aplikacji.

#### P: Czy można zweryfikować wiele podpisów cyfrowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

 Odp.: Tak, możliwa jest weryfikacja wielu podpisów cyfrowych w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Iterując przez`DigitalSignatures` odbioru dokumentu, możesz uzyskać dostęp i zweryfikować każdy podpis cyfrowy indywidualnie.

