---
title: Metody pomocnicze do wyodrębniania treści w Aspose.Words dla Java
linktitle: Metody pomocnicze do wyodrębniania zawartości
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak efektywnie wyodrębniać zawartość z dokumentów programu Word przy użyciu Aspose.Words dla Java. Poznaj metody pomocnicze, niestandardowe formatowanie i wiele więcej w tym obszernym przewodniku.
type: docs
weight: 14
url: /pl/java/document-manipulation/helper-methods-for-extracting-content/
---

## Wprowadzenie do metod pomocniczych do wyodrębniania treści w Aspose.Words dla Java

Aspose.Words dla Java to potężna biblioteka, która umożliwia programistom programową pracę z dokumentami programu Word. Jednym z typowych zadań podczas pracy z dokumentami programu Word jest wyodrębnianie z nich treści. W tym artykule omówimy niektóre metody pomocnicze umożliwiające efektywne wyodrębnianie treści przy użyciu Aspose.Words dla Java.

## Warunki wstępne

Zanim zagłębimy się w przykłady kodu, upewnij się, że masz zainstalowane i skonfigurowane Aspose.Words for Java w swoim projekcie Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).

## Metoda pomocnicza 1: Wyodrębnianie akapitów według stylu

```java
public static ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    // Utwórz tablicę do zbierania akapitów o określonym stylu.
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);

    // Przejrzyj wszystkie akapity, aby znaleźć te, które mają określony styl.
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}
```

Możesz użyć tej metody, aby wyodrębnić akapity o określonym stylu w dokumencie programu Word. Jest to przydatne, gdy chcesz wyodrębnić treść o określonym formatowaniu, taką jak nagłówki lub cytaty blokowe.

## Metoda pomocnicza 2: Wyodrębnianie zawartości przez węzły

```java
public static ArrayList<Node> extractContentBetweenNodes(Node startNode, Node endNode, boolean isInclusive) {
    // Najpierw sprawdź, czy węzły przekazane do tej metody są prawidłowe do użycia.
    verifyParameterNodes(startNode, endNode);
    
    // Utwórz listę do przechowywania wyodrębnionych węzłów.
    ArrayList<Node> nodes = new ArrayList<Node>();

    // Jeśli którykolwiek ze znaczników jest częścią komentarza, łącznie z samym komentarzem, musimy przesunąć wskaźnik
    // przekazać do węzła komentarza znalezionego za węzłem CommentRangeEnd.
    if (endNode.getNodeType() == NodeType.COMMENT_RANGE_END && isInclusive) {
        Node node = findNextNode(NodeType.COMMENT, endNode.getNextSibling());
        if (node != null)
            endNode = node;
    }
    
    // Rejestruj oryginalne węzły przekazane do tej metody, aby w razie potrzeby podzielić węzły znaczników.
    Node originalStartNode = startNode;
    Node originalEndNode = endNode;

    //Wyodrębnij treść w oparciu o węzły na poziomie bloków (akapity i tabele). Przemierzaj węzły nadrzędne, aby je znaleźć.
    // Podzielimy zawartość pierwszego i ostatniego węzła, w zależności od tego, czy węzły znaczników są wbudowane.
    startNode = getAncestorInBody(startNode);
    endNode = getAncestorInBody(endNode);
    boolean isExtracting = true;
    boolean isStartingNode = true;
    // Bieżący węzeł, który wyodrębniamy z dokumentu.
    Node currNode = startNode;

    // Rozpocznij wyodrębnianie zawartości. Przetwórz wszystkie węzły na poziomie bloków i konkretnie podziel pierwszy
    // i ostatnie węzły, jeśli to konieczne, aby zachować formatowanie akapitu.
    // Ta metoda jest nieco bardziej skomplikowana niż zwykły ekstraktor, ponieważ musimy to uwzględnić
    // podczas wyodrębniania przy użyciu wbudowanych węzłów, pól, zakładek itp., aby było to przydatne.
    while (isExtracting) {
        // Sklonuj bieżący węzeł i jego elementy podrzędne, aby uzyskać kopię.
        Node cloneNode = currNode.deepClone(true);
        boolean isEndingNode = currNode.equals(endNode);
        if (isStartingNode || isEndingNode) {
            // Musimy przetwarzać każdy znacznik osobno, więc zamiast tego przekaż go osobnej metodzie.
            // End powinien zostać przetworzony jako pierwszy, aby zachować indeksy węzłów.
            if (isEndingNode) {
                // !isStartingNode: nie dodawaj węzła dwa razy, jeśli znaczniki są tym samym węzłem.
                processMarker(cloneNode, nodes, originalEndNode, currNode, isInclusive,
                        false, !isStartingNode, false);
                isExtracting = false;
            }
            //Warunkowy musi być oddzielony, ponieważ znaczniki początkowe i końcowe na poziomie bloku mogą być tym samym węzłem.
            if (isStartingNode) {
                processMarker(cloneNode, nodes, originalStartNode, currNode, isInclusive,
                        true, true, false);
                isStartingNode = false;
            }
        } else
            // Węzeł nie jest znacznikiem początkowym ani końcowym, po prostu dodaj kopię do listy.
            nodes.add(cloneNode);

        // Przejdź do następnego węzła i wyodrębnij go. Jeśli następny węzeł ma wartość null,
        // reszta treści znajduje się w innej sekcji.
        if (currNode.getNextSibling() == null && isExtracting) {
            // Przejdź do następnej sekcji.
            Section nextSection = (Section) currNode.getAncestor(NodeType.SECTION).getNextSibling();
            currNode = nextSection.getBody().getFirstChild();
        } else {
            // Przejdź do następnego węzła w ciele.
            currNode = currNode.getNextSibling();
        }
    }

    // Aby zapewnić zgodność z trybem zakładek wbudowanych, dodaj kolejny akapit (pusty).
    if (isInclusive && originalEndNode == endNode && !originalEndNode.isComposite())
        includeNextParagraph(endNode, nodes);

    // Zwróć węzły pomiędzy znacznikami węzłów.
    return nodes;
}
```

Ta metoda umożliwia wyodrębnienie treści pomiędzy dwoma określonymi węzłami, niezależnie od tego, czy są to akapity, tabele czy inne elementy na poziomie bloków. Obsługuje różne scenariusze, w tym znaczniki wbudowane, pola i zakładki.

## Metoda pomocnika 3: Generowanie nowego dokumentu

```java
public static Document generateDocument(Document srcDoc, ArrayList<Node> nodes) throws Exception {
    Document dstDoc = new Document();
    
    // Usuń pierwszy akapit z pustego dokumentu.
    dstDoc.getFirstSection().getBody().removeAllChildren();
    
    // Zaimportuj każdy węzeł z listy do nowego dokumentu. Zachowaj oryginalne formatowanie węzła.
    NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
    for (Node node : nodes) {
        Node importNode = importer.importNode(node, true);
        dstDoc.getFirstSection().getBody().appendChild(importNode);
    }
    
    return dstDoc;
}
```

Metoda ta umożliwia wygenerowanie nowego dokumentu poprzez import listy węzłów z dokumentu źródłowego. Zachowuje oryginalne formatowanie węzłów, dzięki czemu jest przydatne do tworzenia nowych dokumentów o określonej treści.

## Wniosek

Wyodrębnianie treści z dokumentów programu Word może być kluczową częścią wielu zadań związanych z przetwarzaniem dokumentów. Aspose.Words dla Java zapewnia potężne metody pomocnicze, które upraszczają ten proces. Niezależnie od tego, czy chcesz wyodrębnić akapity według stylu, treści między węzłami, czy wygenerować nowe dokumenty, te metody pomogą Ci wydajnie pracować z dokumentami programu Word w aplikacjach Java.

## Często zadawane pytania

### Jak mogę zainstalować Aspose.Words dla Java?

 Aby zainstalować Aspose.Words dla Java, możesz pobrać go ze strony internetowej Aspose. Odwiedzać[Tutaj](https://releases.aspose.com/words/java/) aby uzyskać najnowszą wersję.

### Czy mogę wyodrębnić treść z określonych sekcji dokumentu programu Word?

Tak, możesz wyodrębnić zawartość z określonych sekcji dokumentu programu Word, korzystając z metod opisanych w tym artykule. Po prostu określ węzły początkowe i końcowe, które definiują sekcję, którą chcesz wyodrębnić.

### Czy Aspose.Words for Java jest kompatybilny z Java 11?

Tak, Aspose.Words for Java jest kompatybilny z Java 11 i nowszymi wersjami. Możesz go używać w aplikacjach Java bez żadnych problemów.

### Czy mogę dostosować formatowanie wyodrębnionej treści?

Tak, możesz dostosować formatowanie wyodrębnionej treści, modyfikując zaimportowane węzły w wygenerowanym dokumencie. Aspose.Words dla Java zapewnia rozbudowane opcje formatowania, aby spełnić Twoje potrzeby.

### Gdzie mogę znaleźć więcej dokumentacji i przykładów Aspose.Words dla Java?

 Obszerną dokumentację i przykłady Aspose.Words dla Java można znaleźć na stronie internetowej Aspose. Odwiedzać[https://reference.aspose.com/words/java/](https://reference.aspose.com/words/java/) szczegółowej dokumentacji i zasobów.