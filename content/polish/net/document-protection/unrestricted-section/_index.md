---
title: Nieograniczona sekcja w dokumencie programu Word
linktitle: Nieograniczona sekcja w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak definiować nieograniczone sekcje w dokumencie programu Word za pomocą Aspose.Words dla .NET.
type: docs
weight: 10
url: /pl/net/document-protection/unrestricted-section/
---
W tym samouczku przeprowadzimy Cię przez kolejne etapy korzystania z funkcji nieograniczonej sekcji Aspose.Words dla .NET. Ta funkcja umożliwia zdefiniowanie określonych sekcji dokumentu programu Word, które nie są chronione, nawet jeśli chroniona jest reszta dokumentu. Wykonaj poniższe kroki:

## Krok 1: Tworzenie dokumentu i sekcji

Zacznij od utworzenia instancji klasy Document i obiektu DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Dodaj treść do dokumentu
Użyj obiektu DocumentBuilder, aby dodać treść do dokumentu i wstawić podziały sekcji:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Krok 3: Chroń dokument i sekcje

Ochrona sekcji działa tylko wtedy, gdy włączona jest ochrona dokumentów i dozwolona jest tylko edycja w polach formularza. Możesz chronić dokument za pomocą metody Protect() obiektu Document:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Pamiętaj, aby określić prawidłowy typ ochrony i ustawić żądane hasło.

## Krok 4: Wyłączenie ochrony dla określonej sekcji

Domyślnie chronione są wszystkie sekcje, ale można selektywnie wyłączyć ochronę konkretnej sekcji, korzystając z właściwości ProtectedForForms obiektu Sekcja:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

W tym przykładzie ochrona jest wyłączona dla pierwszej sekcji.

## Krok 5: Zapisz dokument

Na koniec zapisz zmodyfikowany dokument:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Pamiętaj, aby podać poprawną ścieżkę i nazwę pliku, aby zapisać dokument z nieograniczoną liczbą sekcji.

### Przykładowy kod źródłowy dla sekcji nieograniczonej przy użyciu Aspose.Words dla .NET

Oto pełny kod źródłowy nieograniczonej sekcji przy użyciu Aspose.Words dla .NET:


```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Wstaw dwie sekcje z tekstem.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Ochrona sekcji działa tylko wtedy, gdy włączona jest ochrona dokumentów i dozwolona jest tylko edycja w polach formularza.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Domyślnie chronione są wszystkie sekcje, ale możemy selektywnie wyłączyć ochronę.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Wykonując te kroki, będziesz mógł łatwo zdefiniować nieograniczone sekcje w swoim dokumencie Word za pomocą Aspose.Words dla .NET.

## Wniosek

W tym samouczku zbadaliśmy funkcję nieograniczonej sekcji w Aspose.Words dla .NET, która pozwala, aby określone sekcje w dokumencie programu Word pozostały niechronione, podczas gdy reszta dokumentu jest chroniona. Wykonując podane kroki, możesz łatwo zdefiniować sekcje w swoim dokumencie, w których użytkownicy będą mogli swobodnie edytować treść, zachowując jednocześnie ochronę innych sekcji. Aspose.Words dla .NET oferuje potężne możliwości ochrony i dostosowywania dokumentów, dając Ci kontrolę nad uprawnieniami do edycji w dokumentach Word.

### Często zadawane pytania dotyczące nieograniczonej sekcji w dokumencie programu Word

#### P: Jakie są nieograniczone sekcje w Aspose.Words dla .NET?

Odp.: Nieograniczone sekcje w Aspose.Words dla .NET to określone sekcje w dokumencie programu Word, które nie są chronione, nawet jeśli reszta dokumentu jest chroniona. Sekcje te umożliwiają użytkownikom modyfikowanie zawartej w nich treści, przy jednoczesnym zachowaniu ochrony pozostałych części dokumentu.

#### P: Jak mogę tworzyć nieograniczone sekcje przy użyciu Aspose.Words dla .NET?

Odp.: Aby utworzyć nieograniczone sekcje w dokumencie programu Word za pomocą Aspose.Words dla .NET, możesz wykonać następujące kroki:
1.  Utwórz instancję`Document` klasa i A`DocumentBuilder` obiekt.
2.  Użyj`DocumentBuilder` , aby dodać treść do dokumentu i wstawić podziały sekcji.
3.  Chroń dokument za pomocą`Protect` metoda`Document` obiektu, określając żądany typ ochrony i hasło.
4.  Wyłącz ochronę dla określonej sekcji, ustawiając opcję`ProtectedForForms` właściwość odpowiedniego`Section` oponować`false`.
5. Zapisz zmodyfikowany dokument.

#### P: Czy mogę mieć wiele nieograniczonych sekcji w dokumencie programu Word?

 Odp.: Tak, w dokumencie programu Word możesz mieć wiele nieograniczonych sekcji. Poprzez selektywne wyłączanie ochrony dla określonych sekcji za pomocą`ProtectedForForms` własność`Section`obiektu, możesz zdefiniować wiele sekcji, w których użytkownicy będą mogli swobodnie modyfikować zawartość, jednocześnie chroniąc inne sekcje.

#### Pytanie 4. Czy mogę usunąć ochronę z sekcji, która była początkowo chroniona?
 Tak, możesz usunąć ochronę z sekcji, która była początkowo chroniona, ustawiając opcję`ProtectedForForms` właściwość odpowiedniego`Section` oponować`false`. Dzięki temu użytkownicy mogą edytować treść w tej konkretnej sekcji bez żadnych ograniczeń.

#### P: Jakie typy ochrony można zastosować do dokumentu programu Word?

Odp.: Aspose.Words dla .NET zapewnia różne typy ochrony, które można zastosować do dokumentu programu Word, w tym:
- NoProtection: Nie jest stosowana żadna ochrona.
- ZezwalajTylkoRewizje: Użytkownicy mogą wprowadzać tylko poprawki do dokumentu.
- Zezwalaj tylko na komentarze: użytkownicy mogą dodawać tylko komentarze do dokumentu.
- ZezwalajOnlyFormFields: Użytkownicy mogą edytować tylko pola formularzy w dokumencie.
- Tylko do odczytu: dokument jest tylko do odczytu i nie można go edytować.


