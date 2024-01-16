---
title: Ustaw względną pozycję poziomą lub pionową
linktitle: Ustaw względną pozycję poziomą lub pionową
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak ustawić względną pozycję poziomą lub pionową tabeli w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

W tym samouczku nauczymy się, jak ustawić względną pozycję poziomą lub pionową tabeli w dokumencie programu Word za pomocą Aspose.Words dla .NET. Będziemy postępować zgodnie z przewodnikiem krok po kroku, aby zrozumieć kod i wdrożyć tę funkcję. Pod koniec tego samouczka będziesz mógł ustawić względną poziomą lub pionową pozycję tabeli w dokumentach programu Word.

## Krok 1: Konfiguracja projektu
1. Uruchom program Visual Studio i utwórz nowy projekt C#.
2. Dodaj odwołanie do biblioteki Aspose.Words dla .NET.

## Krok 2: Załaduj dokument
Aby rozpocząć przetwarzanie tekstu w dokumencie, wykonaj następujące kroki:

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów i podać poprawną nazwę pliku.

## Krok 3: Ustawienie względnej pozycji stołu
Następnie ustalimy względną pozycję stołu w poziomie lub w pionie. Użyj następującego kodu:

```csharp
// Odzyskaj stół
Table table = doc.FirstSection.Body.Tables[0];

//Definicja względnego poziomego położenia stołu
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Określ względne położenie pionowe stołu
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Tutaj używamy dokumentu, aby pobrać pierwszą tabelę z treści pierwszej sekcji. Następnie ustawiamy względną poziomą pozycję stołu za pomocą`HorizontalAnchor` nieruchomość za pomocą`RelativeHorizontalPosition.Column` wartość. Podobnie ustawiamy względną pozycję pionową stołu za pomocą`VerticalAnchor` nieruchomość za pomocą`RelativeVerticalPosition.Page` wartość.

## Krok 4: Zapisanie zmodyfikowanego dokumentu
Na koniec musimy zapisać zmodyfikowany dokument ze zdefiniowanym względnym położeniem tabeli. Użyj następującego kodu:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Pamiętaj, aby określić poprawną ścieżkę i nazwę pliku dokumentu wyjściowego.

### Przykładowy kod źródłowy dla Ustaw względną pozycję poziomą lub pionową przy użyciu Aspose.Words dla .NET 

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Wniosek
W tym samouczku nauczyliśmy się, jak ustawić względne położenie tabeli w poziomie lub pionie w dokumencie programu Word za pomocą Aspose.Words dla .NET. Postępując zgodnie z tym przewodnikiem krok po kroku i wdrażając dostarczony kod C#, możesz zastosować tę względną pozycję do tabel w dokumentach programu Word.