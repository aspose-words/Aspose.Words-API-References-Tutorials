---
title: Drukowanie dokumentów w Aspose.Words dla Java
linktitle: Drukowanie dokumentów
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak drukować dokumenty za pomocą Aspose.Words dla Java. Przewodnik krok po kroku umożliwiający bezproblemowe drukowanie w aplikacjach Java.
type: docs
weight: 10
url: /pl/java/printing-documents/printing-documents/
---

Jeśli chcesz drukować dokumenty przy użyciu Aspose.Words dla Java, jesteś we właściwym miejscu. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces drukowania dokumentów za pomocą Aspose.Words dla Java przy użyciu dostarczonego kodu źródłowego.

## Wstęp

Drukowanie dokumentów jest częstym zadaniem w wielu aplikacjach. Aspose.Words for Java zapewnia potężne API do pracy z dokumentami Word, w tym możliwość ich drukowania. W tym samouczku przeprowadzimy Cię krok po kroku przez proces drukowania dokumentu programu Word.

## Konfigurowanie środowiska

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:

- Zainstalowany zestaw Java Development Kit (JDK).
- Biblioteka Aspose.Words for Java pobrana i dodana do Twojego projektu

## Ładowanie dokumentu

 Aby rozpocząć, musisz załadować dokument programu Word, który chcesz wydrukować. Zastępować`"Your Document Directory"` ze ścieżką do dokumentu i`"Your Output Directory"` z żądanym katalogiem wyjściowym.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Tworzenie zadania drukowania

Następnie utworzymy zadanie drukowania, aby wydrukować załadowany dokument. Poniższy fragment kodu inicjuje zadanie drukowania i ustawia żądane ustawienia drukarki.

```java
// Utwórz zadanie drukowania, za pomocą którego wydrukujesz nasz dokument.
PrinterJob pj = PrinterJob.getPrinterJob();
//Zainicjuj zestaw atrybutów liczbą stron w dokumencie.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Przekaż ustawienia drukarki wraz z innymi parametrami do drukowanego dokumentu.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## Drukowanie dokumentu

Teraz, gdy skonfigurowaliśmy zadanie drukowania, czas wydrukować dokument. Poniższy fragment kodu kojarzy dokument z zadaniem drukowania i inicjuje proces drukowania.

```java
// Przekaż dokument do wydrukowania za pomocą zadania drukowania.
pj.setPrintable(awPrintDoc);
pj.print();
```
## Kompletny kod źródłowy
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
// Utwórz zadanie drukowania, za pomocą którego wydrukujesz nasz dokument.
PrinterJob pj = PrinterJob.getPrinterJob();
//Zainicjuj zestaw atrybutów liczbą stron w dokumencie.
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
// Przekaż ustawienia drukarki wraz z innymi parametrami do drukowanego dokumentu.
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
// Przekaż dokument do wydrukowania za pomocą zadania drukowania.
pj.setPrintable(awPrintDoc);
pj.print();
```
Kod źródłowy MultipagePrintDocument
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <podsumowanie>
    /// Konstruktor niestandardowej klasy PrintDocument.
    // / </podsumowanie>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        // Indeksy początku i końca strony zgodnie z definicją w zestawie atrybutów.
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        // Oblicz indeks strony, która ma zostać wyrenderowana jako następna.
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        // Jeśli indeks strony jest większy niż całkowity zakres stron, nie ma nic
        // więcej do renderowania.
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        // Oblicz rozmiar każdego symbolu zastępczego miniatury w punktach.
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        // Oblicz numer pierwszej strony, która ma zostać wydrukowana na tym arkuszu papieru.
        int startPage = pagesOnCurrentSheet + fromPage;
        // Wybierz numer ostatniej strony, która ma zostać wydrukowana na tym arkuszu papieru.
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //Przejdź w pętli wybrane strony z zapisanej bieżącej strony do obliczenia
        // Ostatnia strona.
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            // Oblicz wskaźniki kolumn i wierszy.
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            // Zdefiniuj lokalizację miniatury we współrzędnych światowych (w tym przypadku punktów).
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                // Oblicz lewą i górną pozycję startową.
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                // Renderuj stronę dokumentu do obiektu Graphics przy użyciu obliczonych współrzędnych
                // i rozmiar symbolu zastępczego miniatury.
                // Przydatną wartością zwracaną jest skala, w jakiej strona została wyrenderowana.
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                // Narysuj krawędzie strony (miniatura strony może być mniejsza niż miniatura
                // rozmiar symbolu zastępczego).
                if (mPrintPageBorders) {
                    // Uzyskaj rzeczywisty 100% rozmiar strony w punktach.
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    // Narysuj obramowanie wokół skalowanej strony, korzystając ze znanego współczynnika skali.
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    // Narysuj obramowanie wokół symbolu zastępczego miniatury.
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                // Jeśli podczas renderowania wystąpią jakieś błędy, nie rób nic.
                // Spowoduje to narysowanie pustej strony, jeśli podczas renderowania wystąpią jakiekolwiek błędy.
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        // Określ liczbę kolumn i wierszy na arkuszu dla pliku
        //Papier o orientacji krajobrazowej.
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        // Zamień szerokość i wysokość, jeśli papier jest w orientacji pionowej.
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## Wniosek

Gratulacje! Pomyślnie wydrukowałeś dokument programu Word przy użyciu Aspose.Words for Java. Ten przewodnik krok po kroku powinien pomóc w bezproblemowej integracji drukowania dokumentów z aplikacjami Java.

## Często zadawane pytania

### P1: Czy mogę wydrukować określone strony dokumentu za pomocą Aspose.Words dla Java?

 Tak, możesz określić zakres stron podczas drukowania dokumentu. W przykładzie kodu użyliśmy`attributes.add(new PageRanges(1, doc.getPageCount()))` aby wydrukować wszystkie strony. W razie potrzeby możesz dostosować zakres stron.

### P2: Czy Aspose.Words dla Java nadaje się do drukowania wsadowego?

Absolutnie! Aspose.Words for Java doskonale nadaje się do zadań drukowania wsadowego. Możesz przeglądać listę dokumentów i drukować je jeden po drugim, używając podobnego kodu.

### P3: Jak mogę poradzić sobie z błędami lub wyjątkami w drukowaniu?

Należy uwzględnić wszelkie potencjalne wyjątki, które mogą wystąpić podczas procesu drukowania. Sprawdź dokumentację Aspose.Words for Java, aby uzyskać informacje na temat obsługi wyjątków.

### P4: Czy mogę bardziej dostosować ustawienia drukowania?

Tak, możesz dostosować ustawienia drukowania do swoich specyficznych wymagań. Zapoznaj się z dokumentacją Aspose.Words for Java, aby dowiedzieć się więcej o dostępnych opcjach drukowania.

### P5: Gdzie mogę uzyskać dodatkową pomoc i wsparcie dla Aspose.Words dla Java?

 Aby uzyskać dodatkowe wsparcie i pomoc, możesz odwiedzić stronę[Forum Aspose.Words dla Java](https://forum.aspose.com/).

---

Teraz, gdy już nauczyłeś się, jak drukować dokumenty przy użyciu Aspose.Words dla Java, możesz zacząć wdrażać tę funkcjonalność w swoich aplikacjach Java. Miłego kodowania!