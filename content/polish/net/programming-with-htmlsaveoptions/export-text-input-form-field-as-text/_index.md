---
title: Eksportuj pole formularza wprowadzania tekstu jako tekst
linktitle: Eksportuj pole formularza wprowadzania tekstu jako tekst
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak eksportować pola formularzy wprowadzania tekstu jako zwykły tekst za pomocą Aspose.Words dla .NET, korzystając z tego obszernego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## Wstęp

A więc nurkujesz w świecie Aspose.Words dla .NET? Świetny wybór! Jeśli chcesz dowiedzieć się, jak wyeksportować pole formularza wprowadzania tekstu jako tekst, jesteś we właściwym miejscu. Niezależnie od tego, czy dopiero zaczynasz, czy doskonalisz swoje umiejętności, ten przewodnik przeprowadzi Cię przez wszystko, co musisz wiedzieć. Zacznijmy, dobrze?

## Warunki wstępne

Zanim zagłębimy się w szczegóły, upewnijmy się, że masz wszystko, czego potrzebujesz, aby sprawnie działać:

-  Aspose.Words dla .NET: Pobierz i zainstaluj najnowszą wersję z[Tutaj](https://releases.aspose.com/words/net/).
- IDE: Visual Studio lub dowolne środowisko programistyczne C#.
- Podstawowa znajomość C#: Zrozumienie podstawowej składni C# i koncepcji programowania obiektowego.
- Dokument: przykładowy dokument programu Word (`Rendering.docx`) z polami formularza wprowadzania tekstu.

## Importuj przestrzenie nazw

Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw. Są to elementy konstrukcyjne, dzięki którym wszystko działa płynnie.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

W porządku, teraz, gdy mamy już gotowe przestrzenie nazw, przejdźmy do akcji!

## Krok 1: Skonfiguruj projekt

Zanim przejdziemy do kodu, upewnijmy się, że nasz projekt jest poprawnie skonfigurowany.

## Tworzenie projektu

1. Otwórz program Visual Studio: Zacznij od otwarcia programu Visual Studio lub preferowanego środowiska programistycznego C#.
2.  Utwórz nowy projekt: Przejdź do`File > New > Project` . Wybierać`Console App (.NET Core)` lub inny odpowiedni rodzaj projektu.
3.  Nazwij swój projekt: nadaj swojemu projektowi znaczącą nazwę, na przykład`AsposeWordsExportExample`.

## Dodawanie Aspose.Words

1.  Zarządzaj pakietami NuGet: kliknij projekt prawym przyciskiem myszy w Eksploratorze rozwiązań i wybierz`Manage NuGet Packages`.
2.  Wyszukaj Aspose.Words: w Menedżerze pakietów NuGet wyszukaj`Aspose.Words`.
3.  Zainstaluj Aspose.Words: Kliknij`Install` aby dodać bibliotekę Aspose.Words do swojego projektu.

## Krok 2: Załaduj dokument Word

Teraz, gdy nasz projekt jest już skonfigurowany, załadujmy dokument programu Word zawierający pola formularza wprowadzania tekstu.

1. Określ katalog dokumentów: Zdefiniuj ścieżkę do katalogu, w którym przechowywany jest dokument.
2.  Załaduj dokument: Użyj`Document` class, aby załadować dokument programu Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Przygotuj katalog eksportu

Zanim wyeksportujemy, upewnijmy się, że nasz katalog eksportu jest gotowy. Tutaj zostanie zapisany nasz plik HTML i obrazy.

1. Zdefiniuj katalog eksportu: Określ ścieżkę, w której zostaną zapisane eksportowane pliki.
2. Sprawdź i wyczyść katalog: Upewnij się, że katalog istnieje i jest pusty.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Krok 4: Skonfiguruj opcje zapisywania

Tutaj dzieje się magia. Musimy skonfigurować opcje zapisywania, aby wyeksportować pole formularza wprowadzania tekstu jako zwykły tekst.

1.  Utwórz Opcje zapisu: Zainicjuj nowy`HtmlSaveOptions` obiekt.
2.  Ustaw opcję eksportu tekstu: Skonfiguruj`ExportTextInputFormFieldAsText`własność do`true`.
3. Ustaw folder obrazów: Określ folder, w którym będą zapisywane obrazy.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Krok 5: Zapisz dokument jako HTML

Na koniec zapiszmy dokument programu Word jako plik HTML, korzystając z naszych skonfigurowanych opcji zapisywania.

1. Zdefiniuj ścieżkę wyjściową: Określ ścieżkę, w której plik HTML zostanie zapisany.
2.  Zapisz dokument: Użyj`Save` metoda`Document`klasa, aby wyeksportować dokument.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Wniosek

I masz to! Pomyślnie wyeksportowałeś pole formularza wprowadzania tekstu jako zwykły tekst przy użyciu Aspose.Words dla .NET. Ten przewodnik powinien dać Ci jasne, krok po kroku podejście do osiągnięcia tego zadania. Pamiętaj, praktyka czyni mistrza, więc eksperymentuj z różnymi opcjami i ustawieniami, aby zobaczyć, co jeszcze możesz zrobić z Aspose.Words.

## Często zadawane pytania

### Czy mogę eksportować inne typy pól formularzy przy użyciu tej samej metody?

 Tak, możesz eksportować inne typy pól formularzy, konfigurując różne właściwości pliku`HtmlSaveOptions` klasa.

### Co się stanie, jeśli mój dokument zawiera obrazy?

 Obrazy zostaną zapisane w określonym folderze obrazów. Upewnij się, że ustawiłeś`ImagesFolder` nieruchomość w`HtmlSaveOptions`.

### Czy potrzebuję licencji na Aspose.Words?

 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/) lub kup licencję[Tutaj](https://purchase.aspose.com/buy).

### Czy mogę dostosować wyeksportowany kod HTML?

 Absolutnie! Aspose.Words zapewnia różne opcje dostosowywania wyjścia HTML. Patrz[dokumentacja](https://reference.aspose.com/words/net/) po więcej szczegółów.

### Czy Aspose.Words jest kompatybilny z .NET Core?

Tak, Aspose.Words jest kompatybilny z .NET Core, .NET Framework i innymi platformami .NET.
