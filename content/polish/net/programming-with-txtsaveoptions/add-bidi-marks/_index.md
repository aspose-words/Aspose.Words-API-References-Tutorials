---
title: Dodaj znaki BiDi w dokumencie programu Word
linktitle: Dodaj znaki BiDi w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Z tego przewodnika dowiesz się, jak dodawać znaki dwukierunkowe (Bidi) w dokumentach programu Word przy użyciu Aspose.Words dla .NET. Zapewnij właściwy kierunek tekstu w przypadku treści wielojęzycznych.
type: docs
weight: 10
url: /pl/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## Wstęp

W świecie przetwarzania dokumentów zarządzanie tekstem dwukierunkowym (Bidi) może być często trudne. Jest to szczególnie prawdziwe w przypadku języków, które mają różne kierunki tekstu, takich jak arabski lub hebrajski. Na szczęście Aspose.Words dla .NET ułatwia obsługę takich scenariuszy. W tym samouczku omówimy, jak dodać znaczniki BiDi do dokumentu programu Word za pomocą Aspose.Words dla .NET.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnij się, że masz następujące elementy:

1.  Aspose.Words dla .NET: Musisz mieć zainstalowany Aspose.Words dla .NET. Można go pobrać z[Strona z plikami do pobrania Aspose](https://releases.aspose.com/words/net/).
2. .NET Framework lub .NET Core: Upewnij się, że masz skonfigurowane kompatybilne środowisko .NET do uruchamiania przykładów.
3. Podstawowa znajomość C#: Znajomość języka programowania C# i podstawowych operacji w .NET.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw. Oto jak możesz uwzględnić je w swoim projekcie:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Podzielmy proces dodawania znaków BiDi w dokumencie programu Word na jasne kroki. Każdy krok poprowadzi Cię przez kod i jego cel.

## Krok 1: Skonfiguruj swój dokument

 Zacznij od utworzenia nowej instancji pliku`Document` klasa i A`DocumentBuilder` aby dodać treść do dokumentu.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Utwórz dokument i dodaj treść
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Na tym etapie inicjujesz nowy dokument programu Word i konfigurujesz plik`DocumentBuilder` aby ułatwić wstawianie treści.

## Krok 2: Dodaj treść do swojego dokumentu

Następnie dodaj tekst do swojego dokumentu. W tym miejscu dodamy tekst w różnych językach, aby zilustrować obsługę tekstu BiDi.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Tutaj najpierw dodajemy standardowe angielskie wyrażenie. Następnie włączamy formatowanie tekstu BiDi dla kolejnego tekstu, który jest napisany w języku hebrajskim i arabskim. To pokazuje, jak włączyć tekst dwukierunkowy.

## Krok 3: Skonfiguruj opcje zapisywania znaków BiDi

 Aby mieć pewność, że znaki BiDi zostaną poprawnie zapisane w dokumencie, należy skonfigurować`TxtSaveOptions` i włącz`AddBidiMarks` opcja.

```csharp
// Dodaj znaki BiDi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 Na tym etapie tworzymy instancję`TxtSaveOptions` i ustaw`AddBidiMarks`własność do`true`. Dzięki temu podczas zapisywania dokumentu jako pliku tekstowego zostaną uwzględnione znaczniki BiDi.

## Wniosek

Dodawanie znaków BiDi do dokumentów programu Word może być kluczowym krokiem w przypadku treści wielojęzycznych, które obejmują języki o różnych kierunkach tekstu. Dzięki Aspose.Words dla .NET proces ten jest prosty i wydajny. Wykonując czynności opisane powyżej, możesz mieć pewność, że Twoje dokumenty poprawnie przedstawiają tekst BiDi, zwiększając czytelność i dokładność.

## Często zadawane pytania

### Czym są znaki Bidi i dlaczego są ważne?
Znaki BiDi to znaki specjalne używane do kontrolowania kierunku tekstu w dokumentach. Są niezbędne do prawidłowego wyświetlania języków czytanych od prawej do lewej, takich jak arabski i hebrajski.

### Czy mogę używać Aspose.Words dla .NET do obsługi innych typów problemów z kierunkiem tekstu?
Tak, Aspose.Words dla .NET zapewnia kompleksową obsługę różnych potrzeb w zakresie kierunku i formatowania tekstu, w tym języków pisanych od prawej do lewej i od lewej do prawej.

### Czy można zastosować formatowanie BiDi tylko do określonych części dokumentu?
Tak, w razie potrzeby możesz zastosować formatowanie BiDi do określonych akapitów lub sekcji dokumentu.

### W jakich formatach mogę zapisać dokument ze znakami BiDi?
W podanym przykładzie dokument jest zapisywany jako plik tekstowy. Jednak Aspose.Words obsługuje również zapisywanie dokumentów w różnych formatach, zachowując jednocześnie znaki BiDi.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Words dla .NET?
 Możesz dowiedzieć się więcej o Aspose.Words dla .NET poprzez[Dokumentacja Aspose](https://reference.aspose.com/words/net/) i uzyskaj dostęp do[Forum wsparcia](https://forum.aspose.com/c/words/8) o dodatkową pomoc.