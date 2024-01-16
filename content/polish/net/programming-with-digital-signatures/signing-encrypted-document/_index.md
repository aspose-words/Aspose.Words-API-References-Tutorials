---
title: Podpisywanie zaszyfrowanego dokumentu Word
linktitle: Podpisywanie zaszyfrowanego dokumentu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak cyfrowo podpisać zaszyfrowany dokument tekstowy za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/signing-encrypted-document/
---
tym samouczku przeprowadzimy Cię przez kolejne kroki korzystania z funkcji podpisywania zaszyfrowanego dokumentu tekstowego za pomocą Aspose.Words dla .NET. Ta funkcja umożliwia cyfrowe podpisanie dokumentu programu Word zaszyfrowanego przy użyciu hasła deszyfrującego. Wykonaj poniższe kroki:

## Krok 1: Ustawianie opcji podpisu

Utwórz instancję klasy SignOptions i ustaw hasło deszyfrujące:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Pamiętaj, aby podać prawidłowe hasło deszyfrujące dla zaszyfrowanego dokumentu.

## Krok 2: Ładowanie certyfikatu

Zacznij od załadowania certyfikatu podpisującego przy użyciu klasy CertyfikatHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Pamiętaj, aby podać poprawną ścieżkę do certyfikatu i powiązanego hasła.

## Krok 3: Podpisanie zaszyfrowanego dokumentu

Do podpisania zaszyfrowanego dokumentu użyj klasy DigitalSignatureUtil:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Pamiętaj, aby określić prawidłowe ścieżki zaszyfrowanego dokumentu, podpisanego dokumentu i certyfikatu.

### Przykładowy kod źródłowy do podpisywania zaszyfrowanego dokumentu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do podpisania zaszyfrowanego dokumentu za pomocą Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Wykonując poniższe kroki, możesz łatwo podpisać zaszyfrowany dokument Word za pomocą Aspose.Words dla .NET.

## Wniosek

W tym samouczku zbadaliśmy proces podpisywania zaszyfrowanego dokumentu programu Word przy użyciu Aspose.Words dla .NET. Podając hasło do odszyfrowania i certyfikat podpisu, możemy dodać podpis cyfrowy do zaszyfrowanego dokumentu. Podpisywanie zaszyfrowanych dokumentów zapewnia ich autentyczność i integralność, zapewniając dodatkową warstwę bezpieczeństwa. Aspose.Words dla .NET umożliwia podpisywanie zaszyfrowanych dokumentów oraz utrzymanie bezpieczeństwa i wiarygodności plików Word.

### Często zadawane pytania

#### P: Co to jest podpisywanie dokumentów w Aspose.Words dla .NET?

Odp.: Podpisywanie dokumentów w Aspose.Words dla .NET odnosi się do procesu cyfrowego podpisywania dokumentu programu Word w celu zapewnienia jego autentyczności, integralności i niezaprzeczalności. Polega na dodaniu podpisu cyfrowego do dokumentu za pomocą certyfikatu.

#### P: Co to jest zaszyfrowany dokument programu Word?

Odp.: Zaszyfrowany dokument programu Word to dokument zaszyfrowany przy użyciu hasła. Szyfrowanie to środek bezpieczeństwa, który chroni zawartość dokumentu poprzez zaszyfrowanie go i uczynienie go nieczytelnym bez prawidłowego hasła deszyfrującego.

#### P: Jak mogę podpisać zaszyfrowany dokument Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby podpisać zaszyfrowany dokument Word przy użyciu Aspose.Words dla .NET, musisz podać hasło deszyfrujące wraz z certyfikatem podpisu. Wykonaj następujące kroki:
1.  Ustaw hasło deszyfrujące w pliku`SignOptions` obiekt.
2.  Załaduj certyfikat podpisywania za pomocą pliku`CertificateHolder` klasa.
3.  Użyj`DigitalSignatureUtil.Sign` metodę podpisania zaszyfrowanego dokumentu, podając niezbędne parametry.

#### P: Jaki jest cel podpisywania zaszyfrowanego dokumentu?

Odp.: Podpisywanie zaszyfrowanego dokumentu za pomocą Aspose.Words dla .NET umożliwia dodanie podpisu cyfrowego do dokumentu, nawet jeśli jest on zaszyfrowany. Zapewnia to dodatkową warstwę bezpieczeństwa oraz zapewnia autentyczność i integralność zaszyfrowanej treści. Pozwala odbiorcom zweryfikować pochodzenie dokumentu i wykryć wszelkie manipulacje.

#### P: Czy mogę podpisać zaszyfrowany dokument bez podawania hasła do odszyfrowania?

O: Nie, aby podpisać zaszyfrowany dokument, musisz podać prawidłowe hasło deszyfrujące. Hasło deszyfrujące jest wymagane, aby uzyskać dostęp do zaszyfrowanej zawartości dokumentu i zmodyfikować go przed złożeniem podpisu cyfrowego.

#### P: Czy mogę podpisać zaszyfrowany dokument programu Word przy użyciu dowolnego certyfikatu?

Odp.: Aby podpisać zaszyfrowany dokument Word przy użyciu Aspose.Words dla .NET, potrzebujesz ważnego certyfikatu X.509. Certyfikat można uzyskać od zaufanego urzędu certyfikacji (CA) lub do celów testowych można użyć certyfikatu z podpisem własnym.

#### P: Czy mogę podpisywać wiele zaszyfrowanych dokumentów programu Word przy użyciu tego samego certyfikatu?

 Odp.: Tak, możesz podpisywać wiele zaszyfrowanych dokumentów programu Word przy użyciu tego samego certyfikatu. Po załadowaniu certyfikatu za pomocą pliku`CertificateHolder` class, możesz go ponownie użyć do podpisania wielu zaszyfrowanych dokumentów.

#### P: Czy mogę zweryfikować podpis cyfrowy podpisanego zaszyfrowanego dokumentu?

 Odp.: Tak, Aspose.Words dla .NET zapewnia funkcję weryfikacji podpisu cyfrowego podpisanego zaszyfrowanego dokumentu. Możesz skorzystać z`DigitalSignatureUtil.Verify` metoda sprawdzania ważności i autentyczności podpisu cyfrowego.

#### P: Jaki format pliku obsługuje Aspose.Words dla .NET do podpisywania zaszyfrowanych dokumentów?

 Odp.: Aspose.Words dla .NET obsługuje podpisywanie zaszyfrowanych dokumentów Word w formacie pliku DOCX. Możesz podpisywać zaszyfrowane pliki DOCX za pomocą`DigitalSignatureUtil.Sign` metodę wraz z niezbędnym hasłem deszyfrującym i certyfikatem.

#### P: W jaki sposób podpisanie zaszyfrowanego dokumentu wpływa na szyfrowanie?

Odp.: Podpisanie zaszyfrowanego dokumentu za pomocą Aspose.Words dla .NET nie ma wpływu na szyfrowanie dokumentu. Szyfrowanie pozostaje nienaruszone, a podpis cyfrowy jest dodawany do zaszyfrowanej treści. Podpis cyfrowy zapewnia dodatkowe bezpieczeństwo i weryfikację bez naruszania szyfrowania zastosowanego w dokumencie.