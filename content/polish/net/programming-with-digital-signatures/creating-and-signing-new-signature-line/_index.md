---
title: Tworzenie i podpisywanie nowej linii podpisu
linktitle: Tworzenie i podpisywanie nowej linii podpisu
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak utworzyć i podpisać nową linię podpisu w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
W tym samouczku przeprowadzimy Cię przez kolejne kroki korzystania z funkcji tworzenia i podpisywania nowej linii podpisu w Aspose.Words dla .NET. Ta funkcja umożliwia wstawienie linii podpisu do dokumentu programu Word, ustawienie opcji niestandardowych i podpisanie dokumentu. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i generatora

Zacznij od utworzenia instancji klasy Document i obiektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Wstawianie linii podpisu

Użyj metody InsertSignatureLine() obiektu DocumentBuilder, aby wstawić nową linię podpisu do dokumentu:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Krok 3: Zapisz dokument

Zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku, aby zapisać dokument.

## Krok 4: Podpisanie dokumentu

Aby podpisać dokument należy ustawić opcje podpisu i skorzystać z klasy DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Pamiętaj, aby określić prawidłowe ścieżki dokumentu, obrazu linii podpisu i podpisanego dokumentu.

### Przykładowy kod źródłowy do tworzenia i podpisywania nowej linii podpisu przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy umożliwiający utworzenie i podpisanie nowej linii podpisu za pomocą Aspose.Words dla .NET:

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Wykonując te kroki, będziesz mógł łatwo utworzyć i podpisać nową linię podpisu w dokumencie Word za pomocą Aspose.Words dla .NET.

## Wniosek

tym samouczku nauczyliśmy się tworzyć i podpisywać nową linię podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Wykonując podane czynności, możesz łatwo wstawić linię podpisu do dokumentu, dostosować jej opcje i podpisać dokument za pomocą certyfikatu cyfrowego. Dodawanie linii podpisu i podpisów cyfrowych do dokumentów zwiększa ich autentyczność i integralność, czyniąc je bezpieczniejszymi i godnymi zaufania. Aspose.Words dla .NET zapewnia potężne API do przetwarzania tekstu z podpisami i certyfikatami cyfrowymi w dokumentach Word, pozwalając zautomatyzować proces podpisywania i zapewnić ważność dokumentów.

### Często zadawane pytania

#### P: Co to jest linia podpisu w dokumencie programu Word?

Odp.: Linia podpisu w dokumencie programu Word to element zastępczy wskazujący, gdzie należy umieścić podpis. Zwykle zawiera imię i nazwisko, tytuł i datę oraz zapewnia miejsce na podpis odręczny lub cyfrowy.

#### P: Jak mogę utworzyć linię podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Aby utworzyć linię podpisu w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Utwórz instancję`Document` klasa i A`DocumentBuilder` obiekt.
2.  Użyj`InsertSignatureLine` metoda`DocumentBuilder` obiekt, aby wstawić nową linię podpisu do dokumentu.
3. Zapisz zmodyfikowany dokument.

#### P: Czy mogę dostosować opcje linii podpisu, takie jak imię i nazwisko, tytuł i data?

 Odp.: Tak, możesz dostosować opcje linii podpisu. The`SignatureLineOptions` class udostępnia właściwości umożliwiające ustawienie żądanych opcji, takich jak`Signer`, `SignerTitle`, `ShowDate`itp. Możesz modyfikować te właściwości przed wstawieniem linii podpisu.

#### P: Jak mogę podpisać dokument po utworzeniu linii podpisu?

 Odp.: Aby podpisać dokument po utworzeniu linii podpisu, musisz ustawić opcje podpisu i użyć opcji`DigitalSignatureUtil` klasa. Oto kroki:
1.  Ustaw`SignatureLineId` nieruchomość w`SignOptions` sprzeciw wobec identyfikatora linii podpisu.
2.  Ustaw`SignatureLineImage` nieruchomość w`SignOptions` sprzeciwić się obrazowi podpisu, którego chcesz użyć.
3.  Załaduj certyfikat podpisywania za pomocą pliku`CertificateHolder` klasa.
4.  Użyj`DigitalSignatureUtil.Sign` sposób podpisania dokumentu, podając niezbędne parametry.

#### P: Czy mogę użyć obrazu podpisu cyfrowego do podpisania dokumentu?

 Odp.: Tak, do podpisania dokumentu możesz użyć obrazu podpisu cyfrowego. Aby to zrobić, musisz dostarczyć plik obrazu w formacie`SignOptions` obiekt za pomocą`SignatureLineImage`nieruchomość. Obraz może być w dowolnym obsługiwanym formacie, takim jak JPEG, PNG lub EMF.

#### P: Jaki jest cel tworzenia i podpisywania nowej linii podpisu w dokumencie programu Word?

Odp.: Tworzenie i podpisywanie nowej linii podpisu w dokumencie Word przy użyciu Aspose.Words dla .NET umożliwia dodanie elementu zastępczego podpisu, a następnie podpisanie dokumentu przy użyciu certyfikatu cyfrowego. Proces ten zapewnia autentyczność i integralność dokumentu, stanowiąc dowód zatwierdzenia lub zgody.

#### P: Czy mogę utworzyć i podpisać wiele linii podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET?

Odp.: Tak, możesz tworzyć i podpisywać wiele linii podpisu w dokumencie programu Word przy użyciu Aspose.Words dla .NET. Każda linia podpisu może mieć swój własny, unikalny identyfikator i opcje. Możesz powtórzyć kroki, aby utworzyć i podpisać dodatkowe linie podpisu w dokumencie.

#### P: Czy mogę zmodyfikować linię podpisu lub dodać dodatkowe informacje po jego podpisaniu?

Odpowiedź: Po podpisaniu linia podpisu staje się częścią treści dokumentu i nie można jej oddzielnie modyfikować. Możesz jednak dodać dodatkowe informacje lub treść po podpisanej linii podpisu.

#### P: Czy mogę zweryfikować podpis cyfrowy dokumentu zawierającego linię podpisu?

 O: Tak, Aspose.Words dla .NET udostępnia funkcję weryfikacji podpisu cyfrowego dokumentu zawierającego linię podpisu. Możesz skorzystać z`DigitalSignatureUtil.Verify` metoda sprawdzania ważności i autentyczności podpisu cyfrowego.

#### P: Jaki format pliku obsługuje Aspose.Words dla .NET do tworzenia i podpisywania linii podpisu?

Odp.: Aspose.Words dla .NET obsługuje tworzenie i podpisywanie linii podpisu w formacie pliku DOCX. Możesz tworzyć i podpisywać linie podpisu w plikach DOCX, korzystając z dostarczonych metod i klas.