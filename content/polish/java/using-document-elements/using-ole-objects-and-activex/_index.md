---
title: Używanie obiektów OLE i kontrolek ActiveX w Aspose.Words dla Java
linktitle: Korzystanie z obiektów OLE i kontrolek ActiveX
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Naucz się korzystać z obiektów OLE i kontrolek ActiveX w Aspose.Words dla Java. Z łatwością twórz interaktywne dokumenty. Zacznij teraz!
type: docs
weight: 21
url: /pl/java/using-document-elements/using-ole-objects-and-activex/
---
tym samouczku omówimy, jak pracować z obiektami OLE (łączenie i osadzanie obiektów) oraz kontrolkami ActiveX w Aspose.Words dla Java. Obiekty OLE i kontrolki ActiveX to potężne narzędzia umożliwiające ulepszanie dokumentów poprzez osadzanie lub łączenie zawartości zewnętrznej, takiej jak arkusze kalkulacyjne, pliki multimedialne lub interaktywne kontrolki. Obserwuj, jak zagłębimy się w przykłady kodu i dowiemy się, jak efektywnie korzystać z tych funkcji.

### Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Aspose.Words dla Java: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Words w swoim projekcie Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/).

2. Środowisko programistyczne Java: W swoim systemie powinieneś mieć skonfigurowane działające środowisko programistyczne Java.

### Wstawianie obiektu OLE

Zacznijmy od wstawienia obiektu OLE do dokumentu Word. Stworzymy prosty dokument Word, a następnie wstawimy obiekt OLE reprezentujący stronę internetową.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com”, „plik html”, prawda, prawda, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

W tym kodzie tworzymy nowy dokument i wstawiamy obiekt OLE wyświetlający stronę internetową Aspose. Możesz zastąpić adres URL żądaną treścią.

### Wstawianie obiektu OLE za pomocą pakietu OlePackage

Następnie przyjrzyjmy się, jak wstawić obiekt OLE przy użyciu pakietu OlePackage. Umożliwia to osadzanie plików zewnętrznych jako obiektów OLE w dokumencie.

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

W tym przykładzie wstawiamy obiekt OLE przy użyciu pakietu OlePackage, co pozwala na dołączenie plików zewnętrznych jako obiektów osadzonych.

### Wstawianie obiektu OLE jako ikony

Zobaczmy teraz, jak wstawić obiekt OLE jako ikonę. Jest to przydatne, gdy chcesz wyświetlić ikonę reprezentującą osadzony plik.

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

W tym kodzie wstawiamy obiekt OLE jako ikonę, zapewniając bardziej atrakcyjną wizualnie reprezentację osadzonej treści.

### Odczytywanie właściwości kontrolki ActiveX

Teraz skupmy się na kontrolkach ActiveX. Dowiemy się, jak czytać właściwości kontrolek ActiveX w dokumencie Word.

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

W tym kodzie iterujemy po kształtach w dokumencie programu Word, identyfikujemy kontrolki ActiveX i pobieramy ich właściwości.

### Wniosek

Gratulacje! Nauczyłeś się, jak pracować z obiektami OLE i kontrolkami ActiveX w Aspose.Words dla Java. Funkcje te otwierają świat możliwości tworzenia dynamicznych i interaktywnych dokumentów.

### Często zadawane pytania

### Jaki jest cel obiektów OLE w dokumencie programu Word? 
   - Obiekty OLE umożliwiają osadzanie lub łączenie zawartości zewnętrznej, takiej jak pliki lub strony internetowe, w dokumencie programu Word.

### Czy mogę dostosować wygląd obiektów OLE w moim dokumencie? 
   - Tak, możesz dostosować wygląd obiektów OLE, w tym ustawić ikony i nazwy plików.

### Co to są formanty ActiveX i jak mogą ulepszyć moje dokumenty? 
   - Formanty ActiveX to interaktywne elementy, które mogą dodawać funkcje do dokumentów programu Word, takie jak kontrolki formularzy lub odtwarzacze multimedialne.

### Czy Aspose.Words dla Java nadaje się do automatyzacji dokumentów na poziomie przedsiębiorstwa? 
   - Tak, Aspose.Words for Java to potężna biblioteka do automatyzacji generowania i manipulowania dokumentami w aplikacjach Java.

### Gdzie mogę uzyskać dostęp do Aspose.Words dla Java? 
   -  Możesz pobrać Aspose.Words dla Java z[Tutaj](https://releases.aspose.com/words/java/).

Zacznij korzystać z Aspose.Words dla Java już dziś i odblokuj pełny potencjał automatyzacji i dostosowywania dokumentów!
