---
title: Wstaw dokument podczas korespondencji seryjnej
linktitle: Wstaw dokument podczas korespondencji seryjnej
second_title: Aspose.Words API do przetwarzania dokumentów
description: Dowiedz się, jak wstawiać dokumenty w polach korespondencji seryjnej za pomocą Aspose.Words dla .NET, w tym kompleksowym samouczku krok po kroku.
type: docs
weight: 10
url: /pl/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
## Wstęp

Witamy w świecie automatyzacji dokumentów dzięki Aspose.Words dla .NET! Czy zastanawiałeś się kiedyś, jak dynamicznie wstawiać dokumenty do określonych pól w dokumencie głównym podczas operacji korespondencji seryjnej? Cóż, jesteś we właściwym miejscu. Ten samouczek poprowadzi Cię krok po kroku przez proces wstawiania dokumentów w polach korespondencji seryjnej przy użyciu Aspose.Words dla .NET. To jak układanie puzzli, w których każdy element idealnie pasuje na swoje miejsce. Zatem zanurzmy się!

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1.  Aspose.Words dla .NET: Można[pobierz najnowszą wersję tutaj](https://releases.aspose.com/words/net/) . Jeśli chcesz kupić licencję, możesz to zrobić[Tutaj](https://purchase.aspose.com/buy) . Alternatywnie możesz otrzymać tzw[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) lub wypróbuj z[bezpłatna wersja próbna](https://releases.aspose.com/).
2. Środowisko programistyczne: Visual Studio lub dowolne inne IDE C#.
3. Podstawowa znajomość języka C#: Znajomość programowania w języku C# sprawi, że ten samouczek będzie prosty.

## Importuj przestrzenie nazw

Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw. Stanowią one elementy składowe Twojego projektu.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.MailMerging;
using System.Linq;
```

Podzielmy proces na łatwe do wykonania etapy. Każdy krok będzie kontynuacją poprzedniego, prowadząc do kompletnego rozwiązania.

## Krok 1: Konfigurowanie katalogu

Zanim zaczniesz wstawiać dokumenty, musisz zdefiniować ścieżkę do katalogu dokumentów. Tutaj przechowywane są Twoje dokumenty.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Ładowanie dokumentu głównego

Następnie załadujesz dokument główny. Ten dokument zawiera pola scalania, w których zostaną wstawione inne dokumenty.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

## Krok 3: Ustawianie wywołania zwrotnego łączenia pól

Aby obsłużyć proces łączenia, musisz ustawić funkcję wywołania zwrotnego. Ta funkcja będzie odpowiedzialna za wstawianie dokumentów w określonych polach scalania.

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Krok 4: Wykonywanie korespondencji seryjnej

Teraz nadszedł czas na wykonanie korespondencji seryjnej. To tutaj dzieje się magia. Określ pole scalania i dokument, który powinien zostać wstawiony w tym polu.

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { dataDir + "Document insertion 2.docx" });
```

## Krok 5: Zapisywanie dokumentu

Po zakończeniu korespondencji seryjnej zapiszesz zmodyfikowany dokument. W nowym dokumencie treść zostanie wstawiona dokładnie tam, gdzie chcesz.

```csharp
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

## Krok 6: Tworzenie procedury obsługi wywołania zwrotnego

Procedura obsługi wywołania zwrotnego to klasa, która wykonuje specjalne przetwarzanie pola scalania. Ładuje dokument określony w wartości pola i wstawia go do bieżącego pola scalania.

```csharp
private class InsertDocumentAtMailMergeHandler : IFieldMergingCallback
{
    void IFieldMergingCallback.FieldMerging(FieldMergingArgs args)
    {
        if (args.DocumentFieldName == "Document_1")
        {
            DocumentBuilder builder = new DocumentBuilder(args.Document);
            builder.MoveToMergeField(args.DocumentFieldName);

            Document subDoc = new Document((string)args.FieldValue);
            InsertDocument(builder.CurrentParagraph, subDoc);

            if (!builder.CurrentParagraph.HasChildNodes)
                builder.CurrentParagraph.Remove();

            args.Text = null;
        }
    }
}
```

## Krok 7: Wkładanie dokumentu

Ta metoda wstawia określony dokument do bieżącego akapitu lub komórki tabeli.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
    if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
    {
        CompositeNode destinationParent = insertionDestination.ParentNode;
        NodeImporter importer = new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

        foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
        foreach (Node srcNode in srcSection.Body)
        {
            if (srcNode.NodeType == NodeType.Paragraph)
            {
                Paragraph para = (Paragraph)srcNode;
                if (para.IsEndOfSection && !para.HasChildNodes)
                    continue;
            }

            Node newNode = importer.ImportNode(srcNode, true);
            destinationParent.InsertAfter(newNode, insertionDestination);
            insertionDestination = newNode;
        }
    }
    else
    {
        throw new ArgumentException("The destination node should be either a paragraph or table.");
    }
}
```

## Wniosek

masz to! Pomyślnie wstawiłeś dokumenty do określonych pól podczas operacji korespondencji seryjnej przy użyciu Aspose.Words dla .NET. Ta zaawansowana funkcja może zaoszczędzić mnóstwo czasu i wysiłku, szczególnie w przypadku dużych ilości dokumentów. Pomyśl o tym jak o osobistym asystentze, który zajmie się wszystkimi ciężkimi zadaniami za Ciebie. Więc śmiało, spróbuj. Miłego kodowania!

## Często zadawane pytania

### Czy mogę wstawić wiele dokumentów w różnych polach scalania?
 Tak, możesz. Wystarczy określić odpowiednie pola scalania i odpowiadające im ścieżki dokumentów w pliku`MailMerge.Execute` metoda.

### Czy można sformatować wstawiony dokument inaczej niż dokument główny?
 Absolutnie! Możesz skorzystać z`ImportFormatMode` parametry w`NodeImporter` do kontrolowania formatowania.

### Co się stanie, jeśli nazwa pola scalania jest dynamiczna?
Możesz obsługiwać dynamiczne nazwy pól scalania, przekazując je jako parametry do procedury obsługi wywołania zwrotnego.

### Czy mogę używać tej metody z różnymi formatami plików?
Tak, Aspose.Words obsługuje różne formaty plików, w tym DOCX, PDF i inne.

### Jak sobie radzić z błędami podczas procesu wstawiania dokumentu?
Zaimplementuj obsługę błędów w procedurze obsługi wywołania zwrotnego, aby zarządzać wszelkimi wyjątkami, które mogą wystąpić.