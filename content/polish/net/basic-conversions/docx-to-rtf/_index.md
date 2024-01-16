---
title: Konwertuj dokument docx na Rtf
linktitle: Konwertuj dokument docx na Rtf
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak konwertować dokumenty programu Word z formatu Docx do formatu RTF przy użyciu Aspose.Words dla .NET. Samouczek krok po kroku z przykładowym kodem źródłowym.
type: docs
weight: 10
url: /pl/net/basic-conversions/docx-to-rtf/
---

W tym samouczku krok po kroku poprowadzimy Cię, jak używać Aspose.Words dla .NET do konwersji dokumentu Word w formacie Docx na RTF. Wyjaśnimy dostarczony kod źródłowy C# i pokażemy, jak zaimplementować go we własnych projektach.

 Aby rozpocząć, upewnij się, że masz zainstalowany i skonfigurowany Aspose.Words for .NET w swoim środowisku programistycznym. Jeśli jeszcze tego nie zrobiłeś, pobierz i zainstaluj bibliotekę z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Czytanie dokumentu ze strumienia

Najpierw otwórz strumień, aby przeczytać dokument Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Krok 2: Ładowanie dokumentu

Następnie załaduj dokument ze strumienia:

```csharp
Document doc = new Document(stream);
```

## Krok 3: Zamykanie strumienia

Ponieważ dokument jest ładowany do pamięci, możesz zamknąć strumień:

```csharp
stream.Close();
```

## Krok 4: Wykonywanie operacji na dokumencie

W tym momencie możesz wykonać dowolne operacje na dokumencie.

## Krok 5: Zapisywanie dokumentu w formacie RTF

Aby zapisać dokument w formacie RTF, zapisz go w strumieniu pamięci:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Krok 6: Przewijanie strumienia

Przed zapisaniem strumienia pamięci do pliku przewiń jego położenie z powrotem do zera:

```csharp
dstStream.Position = 0;
```

## Krok 7: Zapisywanie strumienia do pliku

Na koniec zapisz strumień pamięci do pliku RTF:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

Otóż to! Pomyślnie przekonwertowałeś dokument Word w formacie Docx na RTF przy użyciu Aspose.Words dla .NET.

### Przykładowy kod źródłowy dla Docx To Rtf przy użyciu Aspose.Words dla .NET

```csharp

	// Ścieżka do katalogu dokumentów.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Dostęp tylko do odczytu jest wystarczający, aby Aspose.Words załadował dokument.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	// Możesz teraz zamknąć strumień, nie jest on już potrzebny, ponieważ dokument znajduje się w pamięci.
	stream.Close();

	// ...zrób coś z dokumentem.

	// Przekonwertuj dokument na inny format i zapisz w strumieniu.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Przewiń pozycję strumienia z powrotem do zera, aby był gotowy do następnego czytnika.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Możesz swobodnie używać tego kodu we własnych projektach i modyfikować go zgodnie ze swoimi specyficznymi wymaganiami.

### Często zadawane pytania

#### Jak mogę przekonwertować plik DOCX do formatu RTF?

Aby przekonwertować plik DOCX do formatu RTF, można skorzystać z różnych narzędzi programowych lub bibliotek zapewniających tę funkcję. Jednym z takich niezawodnych narzędzi jest Aspose.Words dla .NET. Oferuje prosty i skuteczny sposób programowej konwersji plików DOCX do formatu RTF. Możesz użyć interfejsu API biblioteki, aby załadować plik DOCX i zapisać go w żądanym formacie RTF.

#### Czy są jakieś ograniczenia w procesie konwersji?

Ograniczenia procesu konwersji zależą od konkretnego narzędzia lub biblioteki, z której korzystasz. Niektóre narzędzia mogą mieć ograniczenia dotyczące rozmiaru lub złożoności dokumentu wejściowego. Ważne jest, aby wybrać narzędzie, które sprosta wymaganiom Twojego zadania konwersji.

#### Czy mogę zachować formatowanie i układ oryginalnego dokumentu?

Tak, dzięki Aspose.Words możesz zachować formatowanie i układ oryginalnego dokumentu podczas procesu konwersji. Na przykład Aspose.Words dla .NET zapewnia kompleksową obsługę formatowania, stylów i innych elementów pliku DOCX w przekonwertowanym dokumencie RTF.

#### Czy Aspose to niezawodne narzędzie do konwersji DOCX na RTF?

Tak, Aspose.Words dla .NET jest wysoce niezawodnym narzędziem do konwersji DOCX do RTF. Jest szeroko stosowany przez programistów i firmy na całym świecie ze względu na jego solidne funkcje i doskonałą wydajność. Biblioteka oferuje obszerną dokumentację, regularne aktualizacje i dedykowaną pomoc techniczną, co czyni ją zaufanym wyborem w przypadku zadań związanych z konwersją dokumentów.