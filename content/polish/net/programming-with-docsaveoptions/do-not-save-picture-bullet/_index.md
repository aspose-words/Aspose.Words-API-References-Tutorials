---
title: Nie zapisuj punktora obrazkowego
linktitle: Nie zapisuj punktora obrazkowego
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wyłączyć zapisywanie punktorów graficznych w dokumentach programu Word przy użyciu Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Punktory obrazkowe to często używana funkcja w dokumentach programu Word służąca do dodawania niestandardowych punktorów. Jednak w niektórych przypadkach może być konieczne wyłączenie rejestracji punktorów obrazu podczas manipulowania dokumentami przy użyciu biblioteki Aspose.Words dla .NET. W tym przewodniku krok po kroku wyjaśnimy, jak używać kodu źródłowego Aspose.Words C# dla .NET, aby wyłączyć zapisywanie punktorów obrazu przy użyciu opcji zapisywania DocSaveOptions.

## Zrozumienie biblioteki Aspose.Words

Przed zagłębieniem się w kod ważne jest zapoznanie się z biblioteką Aspose.Words dla platformy .NET. Aspose.Words to potężna biblioteka do tworzenia, edytowania, konwertowania i ochrony dokumentów programu Word na różnych platformach, w tym .NET. Oferuje wiele funkcji do manipulowania dokumentami, takich jak wstawianie tekstu, zmiana formatowania, dodawanie sekcji i wiele więcej.

## Krok 1: Ustawianie katalogu dokumentów

Pierwszym krokiem jest zdefiniowanie katalogu, w którym znajdują się Twoje dokumenty. Należy podać pełną ścieżkę katalogu. Na przykład :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Pamiętaj, aby zastąpić „TWOJ KATALOG DOKUMENTÓW” rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Ładowanie dokumentu z punktorami obrazkowymi

Następnie musisz załadować dokument z punktorami obrazkowymi. Użyj klasy Document, aby załadować dokument z pliku. Na przykład :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

W tym przykładzie ładujemy dokument z pliku „Image bullet points.docx”

  znajduje się w katalogu dokumentów.

## Krok 3: Skonfiguruj opcje nagrywania

Teraz skonfigurujmy opcje zapisywania naszego dokumentu. Użyj klasy DocSaveOptions, aby określić ustawienia zapisywania. Na przykład :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

tym przykładzie tworzymy nowy obiekt DocSaveOptions i ustawiamy właściwość SavePictureBullet na false, aby wyłączyć zapisywanie punktorów obrazkowych.

## Krok 4: Włącz funkcję „Nie zapisuj punktora obrazkowego”.

Aby włączyć funkcję „Nie zapisuj punktora obrazu”, skonfigurowaliśmy już opcje zapisywania przy ustawieniu opcji SavePictureBullet na wartość false. Dzięki temu punktory graficzne nie zostaną zapisane w dokumencie końcowym.

## Krok 5: Zapisz dokument

Na koniec można zapisać dokument za pomocą metody Save klasy Document. Podaj pełną ścieżkę do pliku i żądaną nazwę pliku. Na przykład :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Pamiętaj, aby zastąpić „dataDir” ścieżką katalogu do dokumentów.

## Przykładowy kod źródłowy opcji zapisywania DocSaveOptions z funkcją „Nie zapisuj punktora obrazkowego” przy użyciu Aspose.Words dla .NET

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Załaduj dokument z punktorami obrazkowymi
Document doc = new Document(dataDir + "Image bullet points.docx");

// Skonfiguruj opcje zapisywania za pomocą funkcji „Nie zapisuj punktora obrazkowego”.
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Zapisz dokument z określonymi opcjami
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Wniosek

tym przewodniku omówiliśmy, jak wyłączyć zapisywanie punktorów graficznych w dokumencie przy użyciu biblioteki Aspose.Words dla .NET. Wykonując podane kroki i korzystając z dostarczonego kodu źródłowego C#, możesz łatwo zastosować tę funkcjonalność w swojej aplikacji C#. Wyłączenie zapisywania punktorów obrazkowych może być przydatne w niektórych sytuacjach, aby zachować strukturę i formatowanie dokumentu bez zapisywania punktorów obrazkowych.