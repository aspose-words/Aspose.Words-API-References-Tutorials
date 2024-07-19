---
title: Konwertuj pola w akapicie
linktitle: Konwertuj pola w akapicie
second_title: Aspose.Words API do przetwarzania dokumentów
description: Konwertuj pola JEŻELI na zwykły tekst w akapicie za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fields/convert-fields-in-paragraph/
---

Oto samouczek pokazujący, jak używać funkcji Konwertuj pola na akapit w Aspose.Words dla .NET. Ten kod konwertuje wszystkie pola typu IF napotkane w ostatnim akapicie dokumentu na zwykły tekst. Wykonaj poniższe kroki, aby zrozumieć i uruchomić ten kod.

Zanim zaczniesz, upewnij się, że zainstalowałeś Aspose.Words dla .NET i skonfiguruj środowisko programistyczne.

## Krok 1: Importuj referencje

Aby użyć Aspose.Words w swoim projekcie, musisz dodać niezbędne odniesienia. Upewnij się, że dodałeś odwołanie do biblioteki Aspose.Words w swoim projekcie.

## Krok 2: Załaduj dokument

Zanim będzie można dokonać konwersji pól, należy załadować dokument zawierający pola do konwersji. Pamiętaj, aby podać poprawną ścieżkę do katalogu zawierającego dokument. Oto jak przesłać dokument:

```csharp
//Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Zastąp „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 3: Konwersja pól na tekst

Po załadowaniu dokumentu możemy przystąpić do konwersji pól typu na zwykły tekst. W tym przykładzie kierujemy tylko pola znajdujące się w ostatnim akapicie dokumentu. Oto kod wykonujący tę konwersję:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Ten kod wykorzystuje kombinację metod LINQ do odfiltrowywania pól w ostatnim akapicie dokumentu, a następnie konwertuje je na zwykły tekst, wywołując metodę`Unlink()` metoda.

## Krok 4: Zapisanie zmodyfikowanego dokumentu

 Po przekonwertowaniu pól możesz zapisać zmodyfikowany dokument. Użyj`Save()` na to metoda. Oto przykład :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku kopii zapasowej.

### Przykład kodu źródłowego dla opcji Konwertuj pola w akapicie przy użyciu Aspose.Words dla .NET

```csharp
//Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument.
Document doc = new Document(dataDir + "Linked fields.docx");

// Konwertuj pola JEŻELI na zwykły tekst w ostatnim akapicie dokumentu.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Zapisz zmodyfikowany dokument.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### Często zadawane pytania

#### P: Co to jest pole konwersji w Aspose.Words?

O: Pole konwersji w Aspose.Words to typ pola, który konwertuje wartość lub wyrażenie na inny format lub typ danych. Na przykład możesz użyć pola konwersji, aby przekonwertować datę na określony format, liczbę na tekst lub wykonać inne rodzaje konwersji.

#### P: Jak wstawić pole konwersji do akapitu za pomocą Aspose.Words?

Odp.: Aby wstawić pole konwersji do akapitu za pomocą Aspose.Words, możesz wykonać następujące kroki:

1. Zaimportuj klasę Document z przestrzeni nazw Aspose.Words.
2. Utwórz instancję dokumentu, ładując istniejący dokument.
3. Pobierz akapit, w którym chcesz wstawić pole konwersji.
4. Użyj metody InsertField, aby wstawić pole konwersji z poprawną składnią.

#### P: Jakie formaty konwersji obsługuje Aspose.Words?

Odp.: Aspose.Words obsługuje szeroką gamę formatów konwersji pól, w tym formaty dat, formaty liczb, formaty tekstowe, formaty walut, formaty procentowe i inne. Pełną listę dostępnych formatów konwersji znajdziesz w dokumentacji Aspose.Words.

#### P: Jak zaktualizować pole konwersji w dokumencie Word za pomocą Aspose.Words?

Odp.: Aby zaktualizować pole konwersji w dokumencie Word za pomocą Aspose.Words, możesz użyć metody UpdateFields. Ta metoda przegląda dokument i aktualizuje wszystkie pola, w tym pola konwersji, przeliczając wartości na podstawie bieżących danych.