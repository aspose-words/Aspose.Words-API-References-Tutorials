---
title: Włącz opcję Wyłącz zastępowanie czcionek
linktitle: Włącz opcję Wyłącz zastępowanie czcionek
second_title: Aspose.Words API do przetwarzania dokumentów
description: tym samouczku dowiesz się, jak włączyć lub wyłączyć zastępowanie czcionek w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/working-with-fonts/enable-disable-font-substitution/
---
W tym samouczku przeprowadzimy Cię przez proces włączania lub wyłączania zastępowania czcionek w dokumencie programu Word podczas jego renderowania przy użyciu biblioteki Aspose.Words dla platformy .NET. Włączenie lub wyłączenie zastępowania czcionek pozwala kontrolować, czy brakujące czcionki są automatycznie zastępowane czcionką domyślną. Poprowadzimy Cię krok po kroku, aby pomóc Ci zrozumieć i wdrożyć kod w Twoim projekcie .NET.

## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Praktyczna znajomość języka programowania C#
- Biblioteka Aspose.Words dla .NET zainstalowana w Twoim projekcie
- Dokument programu Word, który chcesz renderować z podstawieniem czcionek lub bez

## Krok 1: Zdefiniuj katalog dokumentów
 Najpierw musisz ustawić ścieżkę katalogu do lokalizacji dokumentu programu Word. Zastępować`"YOUR DOCUMENT DIRECTORY"` w kodzie odpowiednią ścieżką.

```csharp
// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Prześlij dokument i skonfiguruj ustawienia czcionki
 Następnie załadujemy dokument programu Word, który chcesz wyrenderować, i utworzymy instancję pliku`FontSettings` klasa do obsługi ustawień czcionek. Ustawimy domyślne zastąpienie czcionki, określając nazwę czcionki w`DefaultFontName` i wyłącz zastępowanie informacji o czcionce za pomocą`Enabled` Ustawić`false`.

```csharp
// Załaduj dokument
Document doc = new Document(dataDir + "Rendering.docx");

// Skonfiguruj ustawienia czcionek
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Zastosuj ustawienia czcionki do dokumentu
doc.FontSettings = fontSettings;
```

## Krok 3: Zapisz wyrenderowany dokument
Na koniec zapiszemy wyrenderowany dokument, który będzie uwzględniał zdefiniowane ustawienia zastępowania czcionek.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Przykładowy kod źródłowy opcji Włącz wyłączanie zastępowania czcionek przy użyciu Aspose.Words dla .NET 

```csharp

// Ścieżka do katalogu dokumentów
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Wniosek
W tym samouczku widzieliśmy, jak włączyć lub wyłączyć zastępowanie czcionek w dokumencie programu Word podczas renderowania go za pomocą Aspose.Words dla .NET. Kontrolując zastępowanie czcionek, możesz wpływać na sposób obsługi brakujących czcionek w renderowanych dokumentach. Nie wahaj się użyć tej funkcji, aby dostosować zarządzanie czcionkami w dokumentach Word.

### Często zadawane pytania

#### P: Jak mogę włączyć zastępowanie czcionek w dokumencie Word za pomocą Aspose.Words?

Odp.: Aby włączyć zastępowanie czcionek w dokumencie Word za pomocą Aspose.Words, możesz użyć interfejsu API w celu określenia czcionek zastępczych, które mają być używane, gdy wymagane czcionki nie są dostępne. Zapewni to spójną wizualizację tekstu, nawet bez oryginalnych czcionek.

#### P: Czy można wyłączyć zastępowanie czcionek w dokumencie Word za pomocą Aspose.Words?

Odp.: Tak, za pomocą Aspose.Words możesz wyłączyć podstawianie czcionek w dokumencie Word. Korzystając z API, możesz uniemożliwić programowi Word zastępowanie wymaganych czcionek innymi czcionkami, co pozwala zachować oryginalny wygląd tekstu.

#### P: Co się stanie, jeśli podczas zastępowania w dokumencie programu Word zabraknie wymaganych czcionek?

Odp.: Jeśli podczas zastępowania w dokumencie Word brakuje wymaganych czcionek, Aspose.Words może wykryć ten problem i udostępnić opcje jego rozwiązania. Możesz zastąpić brakujące czcionki czcionkami alternatywnymi lub dołączyć brakujące czcionki do dokumentu, zapewniając prawidłowe przeglądanie.

#### P: Jak mogę sobie poradzić z brakującymi czcionkami podczas zastępowania w dokumencie Word za pomocą Aspose.Words?

Odp.: Aby obsłużyć brakujące czcionki podczas zastępowania w dokumencie Word za pomocą Aspose.Words, możesz użyć interfejsu API do wykrywania brakujących czcionek i zapewnienia opcji rozdzielczości. W zależności od potrzeb możesz zastąpić brakujące czcionki czcionkami alternatywnymi lub dołączyć brakujące czcionki do dokumentu.

#### P: Czy kontrolowanie zastępowania czcionek w dokumencie programu Word jest ważne?

Odp.: Tak, ważne jest kontrolowanie zastępowania czcionek w dokumencie programu Word, aby zachować wizualną integralność tekstu. Używając Aspose.Words do włączania lub wyłączania zastępowania czcionek, możesz mieć pewność, że wymagane czcionki zostaną użyte i uniknąć problemów z brakującymi lub zastąpionymi czcionkami.