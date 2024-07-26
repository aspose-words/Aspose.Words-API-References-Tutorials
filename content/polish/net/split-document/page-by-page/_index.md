---
title: Podziel dokument programu Word według stron
linktitle: Podziel dokument programu Word według stron
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak podzielić dokument programu Word na poszczególne strony za pomocą Aspose.Words dla .NET. To potężne API upraszcza proces dzielenia dokumentów, czyniąc go wydajnym i wygodnym.
type: docs
weight: 10
url: /pl/net/split-document/page-by-page/
---

W tym samouczku przeprowadzimy Cię przez proces dzielenia dokumentu programu Word na poszczególne strony przy użyciu funkcji przetwarzania dokumentów Aspose.Words dla .NET. Wykonaj poniższe kroki, aby zrozumieć kod źródłowy i uzyskać osobne dokumenty dla każdej strony.

## Krok 1: Ładowanie dokumentu

Aby rozpocząć, określ katalog dla swojego dokumentu i załaduj dokument do obiektu Document. Oto jak:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Krok 2: Podział dokumentu według stron

Teraz przejdziemy przez każdą stronę dokumentu i podzielimy dokument na poszczególne strony. Oto jak:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Zapisz każdą stronę jako oddzielny dokument.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Przykładowy kod źródłowy dla Page By Page przy użyciu Aspose.Words dla .NET

Oto kompletny kod źródłowy funkcji Page by Page w Aspose.Words dla .NET:

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Zapisz każdą stronę jako oddzielny dokument.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Dzięki temu kodowi będziesz mógł podzielić dokument Worda na poszczególne strony za pomocą Aspose.Words dla .NET. W razie potrzeby możesz także scalić oddzielne dokumenty.

## Wniosek

Gratulacje! Nauczyłeś się, jak dzielić dokument programu Word na pojedyncze strony, korzystając z funkcji Strona po stronie w Aspose.Words dla .NET. Postępując zgodnie z dostarczonym kodem źródłowym, możesz wyodrębnić każdą stronę dokumentu i zapisać je jako osobne dokumenty.

Dzielenie dokumentu według stron może być przydatne, gdy trzeba pracować z określonymi stronami lub szczegółowo rozpowszechniać zawartość. Aspose.Words dla .NET zapewnia potężne API, które upraszcza proces dzielenia dokumentów, czyniąc go wydajnym i wygodnym.

Zachęcamy do zapoznania się z innymi funkcjami oferowanymi przez Aspose.Words dla .NET, aby zwiększyć możliwości przetwarzania dokumentów i usprawnić przepływ pracy.

### Często zadawane pytania

#### Jak podzielić dokument na wiele stron za pomocą Aspose.Words dla .NET?

 Aby podzielić dokument na wiele stron, możesz użyć opcji`ExtractPages` metoda interfejsu API Aspose.Words w celu uzyskania zakresu stron. Określając stronę początkową i liczbę stron do wyodrębnienia, możesz utworzyć osobne dokumenty dla każdej strony.

#### Czy mogę dostosować format wyjściowy podczas dzielenia dokumentu według stron?

Tak, Aspose.Words dla .NET obsługuje różne formaty wyjściowe podczas dzielenia dokumentu według stron. Możesz zapisać każdą stronę jako osobny dokument w formatach takich jak DOCX, PDF, HTML i innych, w zależności od wymagań.

#### Czy mogę podzielić dokument według określonego zakresu stron?

Absolutnie! Aspose.Words dla .NET umożliwia podzielenie dokumentu według określonego zakresu stron. Dostosowując stronę początkową i liczbę stron do wyodrębnienia, możesz precyzyjnie określić zakres stron do podziału dokumentu.

#### Czy możliwe jest ponowne połączenie podzielonych dokumentów w jeden dokument?

Tak, możesz scalić podzielone dokumenty z powrotem w jeden dokument, korzystając z funkcji scalania zapewnianej przez Aspose.Words dla .NET. Łącząc oddzielne dokumenty, możesz w razie potrzeby odtworzyć oryginalny dokument lub utworzyć nowy dokument o innej strukturze.