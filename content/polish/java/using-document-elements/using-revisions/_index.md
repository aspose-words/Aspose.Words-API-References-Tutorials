---
title: Korzystanie z wersji w Aspose.Words dla Java
linktitle: Korzystanie z wersji
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Naucz się efektywnie korzystać z Aspose.Words w wersji Java. Przewodnik krok po kroku dla programistów. Zoptymalizuj zarządzanie dokumentami.
type: docs
weight: 22
url: /pl/java/using-document-elements/using-revisions/
---

Jeśli jesteś programistą Java i chcesz pracować z dokumentami i potrzebujesz wdrożyć kontrolę wersji, Aspose.Words dla Java zapewnia potężny zestaw narzędzi, które pomogą Ci skutecznie zarządzać wersjami. W tym samouczku poprowadzimy Cię krok po kroku przez korzystanie z wersji Aspose.Words dla Java. 

## 1. Wprowadzenie do Aspose.Words dla Javy

Aspose.Words for Java to solidny interfejs API Java, który umożliwia tworzenie, modyfikowanie i manipulowanie dokumentami programu Word bez potrzeby korzystania z programu Microsoft Word. Jest to szczególnie przydatne, gdy trzeba wprowadzić poprawki w dokumentach.

## 2. Konfigurowanie środowiska programistycznego

Zanim zaczniemy używać Aspose.Words dla Java, musisz skonfigurować środowisko programistyczne. Upewnij się, że masz zainstalowane niezbędne narzędzia programistyczne Java i zainstalowaną bibliotekę Aspose.Words for Java.

## 3. Tworzenie nowego dokumentu

Zacznijmy od utworzenia nowego dokumentu Worda przy użyciu Aspose.Words dla Java. Oto jak możesz to zrobić:

```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
```

## 4. Dodawanie treści do dokumentu

Teraz, gdy masz pusty dokument, możesz dodać do niego treść. W tym przykładzie dodamy trzy akapity:

```java
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
```

## 5. Rozpoczęcie śledzenia wersji

Aby śledzić wersje w swoim dokumencie, możesz użyć następującego kodu:

```java
doc.startTrackRevisions("John Doe", new Date());
```

## 6. Dokonywanie poprawek

Wprowadźmy poprawkę, dodając kolejny akapit:

```java
para = body.appendParagraph("Paragraph 4. ");
```

## 7. Akceptowanie i odrzucanie poprawek

Możesz akceptować lub odrzucać poprawki w swoim dokumencie za pomocą Aspose.Words for Java. Wersjami można łatwo zarządzać w programie Microsoft Word po wygenerowaniu dokumentu.

## 8. Zatrzymywanie śledzenia wersji

Aby zatrzymać śledzenie wersji, użyj następującego kodu:

```java
doc.stopTrackRevisions();
```

## 9. Zapisywanie dokumentu

Na koniec zapisz swój dokument:

```java
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
```

## 10. Wniosek

W tym samouczku omówiliśmy podstawy korzystania z wersji w Aspose.Words dla Java. Wiesz już, jak utworzyć dokument, dodać treść, rozpocząć i zatrzymać śledzenie wersji oraz zapisać dokument.

Teraz masz narzędzia potrzebne do skutecznego zarządzania wersjami aplikacji Java za pomocą Aspose.Words for Java.

## Kompletny kod źródłowy
```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
// Dodaj tekst do pierwszego akapitu, a następnie dodaj dwa kolejne akapity.
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
//Mamy trzy akapity, z których żaden nie jest zarejestrowany jako jakikolwiek rodzaj rewizji
// Jeśli dodamy/usuniemy jakąkolwiek treść w dokumencie podczas śledzenia wersji,
// będą one wyświetlane jako takie w dokumencie i można je zaakceptować/odrzucić.
doc.startTrackRevisions("John Doe", new Date());
// Ten akapit jest wersją i będzie miał ustawioną odpowiednią flagę „IsInsertRevision”.
para = body.appendParagraph("Paragraph 4. ");
Assert.assertTrue(para.isInsertRevision());
// Pobierz zbiór akapitów dokumentu i usuń akapit.
ParagraphCollection paragraphs = body.getParagraphs();
Assert.assertEquals(4, paragraphs.getCount());
para = paragraphs.get(2);
para.remove();
// Ponieważ śledzimy wersje, akapit nadal istnieje w dokumencie i będzie miał ustawioną opcję „IsDeleteRevision”
// i będzie wyświetlana jako wersja w programie Microsoft Word, dopóki nie zaakceptujemy lub odrzucimy wszystkich wersji.
Assert.assertEquals(4, paragraphs.getCount());
Assert.assertTrue(para.isDeleteRevision());
// Usunięty akapit dotyczący wersji zostanie usunięty po zaakceptowaniu zmian.
doc.acceptAllRevisions();
Assert.assertEquals(3, paragraphs.getCount());
Assert.assertEquals(para.getRuns().getCount(), 0); //był Jest.Pusty
// Zatrzymanie śledzenia wersji powoduje, że ten tekst wygląda jak zwykły tekst.
// W przypadku zmiany dokumentu korekty nie są liczone.
doc.stopTrackRevisions();
// Zapisz dokument.
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
  
```

## Często zadawane pytania

### 1. Czy mogę używać Aspose.Words for Java z innymi językami programowania?

Nie, Aspose.Words for Java został specjalnie zaprojektowany do programowania w języku Java.

### 2. Czy Aspose.Words for Java jest kompatybilny ze wszystkimi wersjami Microsoft Word?

Tak, Aspose.Words for Java został zaprojektowany tak, aby był kompatybilny z różnymi wersjami Microsoft Word.

### 3. Czy mogę śledzić poprawki w istniejących dokumentach programu Word?

Tak, możesz używać Aspose.Words for Java do śledzenia wersji w istniejących dokumentach Word.

### 4. Czy istnieją jakieś wymagania licencyjne dotyczące korzystania z Aspose.Words dla Java?

 Tak, musisz nabyć licencję, aby używać Aspose.Words for Java w swoich projektach. Możesz[uzyskaj dostęp do licencji tutaj](https://purchase.aspose.com/buy).

### 5. Gdzie mogę znaleźć wsparcie dla Aspose.Words dla Java?

 W przypadku jakichkolwiek pytań lub problemów możesz odwiedzić stronę[Forum pomocy technicznej Aspose.Words dla języka Java](https://forum.aspose.com/).

Zacznij korzystać z Aspose.Words dla Java już dziś i usprawnij procesy zarządzania dokumentami.
