---
title: Podpisz dokument programu Word
linktitle: Podpisz dokument programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak cyfrowo podpisać dokument programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/sign-document/
---
W tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji podpisywania dokumentów w Aspose.Words dla .NET. Ta funkcja umożliwia cyfrowe podpisanie dokumentu programu Word przy użyciu certyfikatu. Wykonaj poniższe kroki:

## Krok 1: Ładowanie certyfikatu

Zacznij od załadowania certyfikatu podpisującego przy użyciu klasy CertyfikatHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Pamiętaj, aby podać poprawną ścieżkę do certyfikatu i powiązanego hasła.

## Krok 2: Podpisanie dokumentu

Do podpisania dokumentu użyj klasy DigitalSignatureUtil:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Pamiętaj, aby określić prawidłowe ścieżki dokumentu źródłowego i podpisanego dokumentu.

### Przykładowy kod źródłowy podpisania dokumentu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy do podpisania dokumentu za pomocą Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Wykonując poniższe kroki, możesz łatwo podpisać dokument Word za pomocą Aspose.Words dla .NET.

## Wniosek

 W tym samouczku zbadaliśmy funkcję podpisywania dokumentów w Aspose.Words dla .NET. Ładując certyfikat podpisywania i używając pliku`DigitalSignatureUtil.Sign` metodą możemy podpisać cyfrowo dokument Word. Podpisywanie dokumentów zapewnia uwierzytelnianie i zapewnia integralność zawartości dokumentu, co czyni go cenną funkcją bezpiecznego i godnego zaufania zarządzania dokumentami.

### Często zadawane pytania dotyczące dokumentu ze słowem migowym

#### P: Co to jest podpisywanie dokumentów w Aspose.Words dla .NET?

Odp.: Podpisywanie dokumentów w Aspose.Words dla .NET odnosi się do procesu cyfrowego podpisywania dokumentu Word przy użyciu certyfikatu. Ta funkcja dodaje podpis cyfrowy do dokumentu, zapewniając autentyczność, integralność i niezaprzeczalność zawartości dokumentu.

#### P: Jak mogę załadować certyfikat podpisywania w Aspose.Words dla .NET?

 Odp.: Aby załadować certyfikat podpisywania w Aspose.Words dla .NET, możesz użyć`CertificateHolder` klasa. Utwórz instancję`CertificateHolder` podając ścieżkę do pliku certyfikatu i powiązane hasło. Oto przykład:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Upewnij się, że podałeś poprawną ścieżkę do certyfikatu i powiązanego hasła.

#### P: Jak podpisać dokument Word przy użyciu Aspose.Words dla .NET?

 Odp.: Aby podpisać dokument Word przy użyciu Aspose.Words dla .NET, możesz użyć`DigitalSignatureUtil` klasa. Zadzwoń do`Sign` metodę, podając ścieżkę do dokumentu źródłowego, ścieżkę do podpisanego dokumentu (wyjście) oraz`CertificateHolder` obiekt. Oto przykład:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Upewnij się, że podałeś poprawne ścieżki do dokumentu źródłowego i podpisanego dokumentu (wyjścia).

#### P: Jaki jest cel podpisywania dokumentów?

Odp.: Podpisywanie dokumentów służy jako metoda zapewnienia autentyczności i integralności dokumentu. Podpisując cyfrowo dokument, możesz udowodnić jego pochodzenie, sprawdzić, czy jego zawartość nie została zmieniona i zapewnić niezaprzeczalność. Podpisywanie dokumentów jest powszechnie stosowane w przypadku dokumentów prawnych, finansowych i wrażliwych.

#### P: Czy mogę używać dowolnego certyfikatu do podpisywania dokumentów w Aspose.Words dla .NET?

Odp.: Do podpisywania dokumentów w Aspose.Words dla .NET musisz użyć ważnego certyfikatu X.509. Certyfikat ten można uzyskać od zaufanego urzędu certyfikacji (CA) lub do celów testowych można użyć certyfikatu z podpisem własnym.

#### P: Jaki format pliku obsługuje Aspose.Words dla .NET do podpisywania dokumentów?

 Odp.: Aspose.Words dla .NET obsługuje podpisywanie dokumentów programu Word w formacie pliku DOCX. Możesz podpisywać pliki DOCX za pomocą`DigitalSignatureUtil` klasę i odpowiedni certyfikat.

#### P: Czy mogę podpisać wiele dokumentów programu Word przy użyciu tego samego certyfikatu?

Odp.: Tak, możesz podpisywać wiele dokumentów programu Word przy użyciu tego samego certyfikatu. Po załadowaniu certyfikatu za pomocą pliku`CertificateHolder` class, możesz użyć jej ponownie do podpisania wielu dokumentów, wywołując metodę`DigitalSignatureUtil.Sign` metoda z różnymi ścieżkami źródłowymi i podpisanymi dokumentami.

#### P: Czy podpisanie dokumentu modyfikuje oryginalny dokument?

Odp.: Podpisanie dokumentu za pomocą Aspose.Words dla .NET nie modyfikuje oryginalnego dokumentu. Zamiast tego tworzy podpisaną cyfrowo kopię dokumentu, pozostawiając oryginalny dokument nienaruszony. Kopia podpisana cyfrowo zawiera dodany podpis cyfrowy, zapewniający integralność treści dokumentu.

#### P: Czy mogę zweryfikować podpis cyfrowy podpisanego dokumentu za pomocą Aspose.Words dla .NET?

 Odp.: Tak, Aspose.Words dla .NET zapewnia funkcję weryfikacji podpisu cyfrowego podpisywanego dokumentu. Możesz skorzystać z`DigitalSignatureUtil.Verify` metoda sprawdzania ważności i autentyczności podpisu cyfrowego.