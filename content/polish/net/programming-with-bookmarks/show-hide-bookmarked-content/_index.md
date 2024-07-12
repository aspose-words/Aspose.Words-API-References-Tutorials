---
title: Pokaż Ukryj zawartość dodaną do zakładek w dokumencie programu Word
linktitle: Pokaż Ukryj zawartość dodaną do zakładek w dokumencie programu Word
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak dynamicznie wyświetlać lub ukrywać zawartość zakładek w dokumentach programu Word przy użyciu Aspose.Words dla .NET, korzystając z tego obszernego przewodnika krok po kroku.
type: docs
weight: 10
url: /pl/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Wstęp

No hej! Czy kiedykolwiek chciałeś kontrolować widoczność określonej treści w dokumencie programu Word w oparciu o określone warunki? Dzięki Aspose.Words dla .NET możesz dynamicznie pokazywać lub ukrywać zawartość zakładek za pomocą zaledwie kilku linijek kodu. W tym samouczku przeprowadzę Cię przez proces krok po kroku, upewniając się, że rozumiesz każdą część kodu. Na koniec będziesz profesjonalistą w manipulowaniu zakładkami w dokumentach programu Word. Zacznijmy!

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnijmy się, że masz wszystko, czego potrzebujesz:

1. Podstawowa znajomość języka C#: Powinieneś znać składnię i koncepcje języka C#.
2.  Aspose.Words dla .NET: Pobierz[Tutaj](https://releases.aspose.com/words/net/) . Jeśli nie jesteś jeszcze gotowy na zakup, możesz zacząć od[bezpłatna wersja próbna](https://releases.aspose.com/).
3. Visual Studio: każda najnowsza wersja będzie działać, ale zalecane jest użycie najnowszej wersji.
4. .NET Framework: Upewnij się, że jest zainstalowany na Twoim komputerze.

Gotowy żeby zacząć? Świetnie! Zacznijmy od zaimportowania niezbędnych przestrzeni nazw.

## Importuj przestrzenie nazw

Aby używać Aspose.Words dla .NET, musimy zaimportować wymagane przestrzenie nazw. Ten krok zapewnia nam dostęp do wszystkich klas i metod, których będziemy używać.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Te przestrzenie nazw są niezbędne do pracy z dokumentami programu Word i manipulowania ich zawartością.

## Krok 1: Konfiguracja dokumentu

Najpierw utwórzmy nowy dokument Word i narzędzie do tworzenia dokumentów. Kreator dokumentów pomaga nam łatwo dodawać zawartość dokumentu i manipulować nią.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Na tym etapie inicjujemy nowy dokument i narzędzie do tworzenia dokumentów. To przygotowuje nasze środowisko do dalszych działań.

## Krok 2: Dodawanie treści dodanych do zakładek

Następnie dodamy trochę treści do dokumentu i utworzymy wokół niego zakładkę. Ta zakładka pomoże nam zidentyfikować i manipulować treścią.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Tutaj dodajemy tekst przed i po treści dodanej do zakładek. The`StartBookmark`I`EndBookmark` metody definiują granice zakładki.

## Krok 3: Wstawianie pola warunkowego

Aby kontrolować widoczność treści dodanej do zakładek, użyjemy pola warunkowego. To pole sprawdzi warunek i odpowiednio wyświetli lub ukryje treść.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

W tym kroku wstawiamy pole JEŻELI, które sprawdza wartość zakładki. Jeśli wartość jest „prawda”, zostanie wyświetlony komunikat „Widoczny”; w przeciwnym razie wyświetli się komunikat „Ukryty”.

## Krok 4: Zmiana układu węzłów

Następnie musimy zmienić rozmieszczenie węzłów, aby mieć pewność, że logika warunkowa zostanie poprawnie zastosowana do treści dodanej do zakładek.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Tutaj przesuwamy węzły, aby upewnić się, że warunek prawidłowo obejmuje zawartość dodaną do zakładek.

## Krok 5: Wykonywanie korespondencji seryjnej

Na koniec przeprowadzimy korespondencję seryjną, aby ustawić wartość zakładki i określić, czy treść powinna być pokazana czy ukryta.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Ten krok ustawia wartość zakładki na „true”, co sprawi, że treść będzie widoczna na podstawie naszego warunku.

## Krok 6: Zapisywanie dokumentu

Po wszystkich manipulacjach ostatnim krokiem jest zapisanie zmodyfikowanego dokumentu.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Tutaj zapisujemy dokument z opisową nazwą pliku, aby wskazać zmiany.

## Wniosek

 I to wszystko! Pomyślnie nauczyłeś się, jak pokazywać lub ukrywać zawartość zakładek w dokumencie programu Word przy użyciu Aspose.Words dla .NET. W tym samouczku omówiono tworzenie dokumentu, dodawanie zakładek, wstawianie pól warunkowych, zmianę układu węzłów i wykonywanie korespondencji seryjnej. Aspose.Words oferuje mnóstwo funkcji, więc nie wahaj się ich poznać[Dokumentacja API](https://reference.aspose.com/words/net/) dla bardziej zaawansowanych możliwości.

## Często zadawane pytania

### 1. Co to jest Aspose.Words dla .NET?

Aspose.Words dla .NET to potężna biblioteka, która umożliwia programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów programu Word. Jest szeroko stosowany do zadań automatyzacji dokumentów.

### 2. Czy mogę używać Aspose.Words dla .NET za darmo?

 Możesz wypróbować Aspose.Words dla .NET przy użyciu pliku[bezpłatna wersja próbna](https://releases.aspose.com/). Aby używać długoterminowo, musisz kupić licencję.

### 3. Jak modyfikować inne właściwości zakładki?

 Aspose.Words umożliwia manipulowanie różnymi właściwościami zakładki, takimi jak jej tekst i lokalizacja. Patrz[Dokumentacja API](https://reference.aspose.com/words/net/) szczegółowe instrukcje.

### 4. Jak uzyskać wsparcie dla Aspose.Words dla .NET?

Możesz uzyskać wsparcie, odwiedzając stronę[Forum wsparcia Aspose](https://forum.aspose.com/c/words/8).

### 5. Czy mogę manipulować innymi typami treści za pomocą Aspose.Words dla .NET?

Tak, Aspose.Words dla .NET obsługuje różne typy manipulacji treścią, w tym tekstem, obrazami, tabelami i nie tylko.