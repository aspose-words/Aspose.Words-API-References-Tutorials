---
title: Zachowaj numerację źródłową
linktitle: Zachowaj numerację źródłową
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak importować dokumenty, zachowując formatowanie, używając Aspose.Words dla .NET. Przewodnik krok po kroku z przykładami kodu.
type: docs
weight: 10
url: /pl/net/join-and-append-documents/keep-source-numbering/
---
## Wstęp

 Podczas pracy z Aspose.Words dla .NET importowanie dokumentów z jednego źródła do drugiego przy zachowaniu formatowania może być efektywnie obsługiwane przy użyciu`NodeImporter` klasa. Ten samouczek przeprowadzi Cię przez proces krok po kroku.

## Warunki wstępne

Przed rozpoczęciem upewnij się, że posiadasz następujące elementy:
- Program Visual Studio zainstalowany na Twoim komputerze.
-  Zainstalowano Aspose.Words dla .NET. Jeśli nie, pobierz go z[Tutaj](https://releases.aspose.com/words/net/).
- Podstawowa znajomość programowania w C# i .NET.

## Importuj przestrzenie nazw

Najpierw uwzględnij w swoim projekcie niezbędne przestrzenie nazw:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Krok 1: Skonfiguruj swój projekt

Rozpocznij od utworzenia nowego projektu C# w programie Visual Studio i zainstaluj Aspose.Words za pośrednictwem Menedżera pakietów NuGet.

## Krok 2: Zainicjuj dokumenty
Utwórz instancje źródła (`srcDoc`) i miejsce docelowe (`dstDoc`) dokumenty.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Krok 3: Skonfiguruj opcje importu
Skonfiguruj opcje importu, aby zachować formatowanie źródłowe, w tym numerowane akapity.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Krok 4: Importuj akapity
Iteruj po akapitach w dokumencie źródłowym i importuj je do dokumentu docelowego.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Krok 5: Zapisz dokument
Zapisz scalony dokument w wybranej lokalizacji.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Wniosek

 Podsumowując, używanie Aspose.Words dla .NET do importowania dokumentów przy zachowaniu formatowania jest proste dzięki`NodeImporter` klasa. Ta metoda gwarantuje, że dokumenty bezproblemowo zachowają swój oryginalny wygląd i strukturę.

## Często zadawane pytania

### Czy mogę importować dokumenty z różnymi stylami formatowania?
 Tak`NodeImporter` klasa obsługuje importowanie dokumentów o różnych stylach formatowania.

### Co się stanie, jeśli moje dokumenty zawierają złożone tabele i obrazy?
Aspose.Words dla .NET obsługuje złożone struktury, takie jak tabele i obrazy, podczas operacji importu.

### Czy Aspose.Words jest kompatybilny ze wszystkimi wersjami .NET?
Aspose.Words obsługuje wersje .NET Framework i .NET Core w celu zapewnienia bezproblemowej integracji.

### Jak radzić sobie z błędami podczas importu dokumentów?
Użyj bloków try-catch do obsługi wyjątków, które mogą wystąpić podczas procesu importu.

### Gdzie mogę znaleźć bardziej szczegółową dokumentację dotyczącą Aspose.Words dla .NET?
 Odwiedzić[dokumentacja](https://reference.aspose.com/words/net/) w celu uzyskania kompleksowych przewodników i referencji API.
