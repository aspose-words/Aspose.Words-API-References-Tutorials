---
title: Używanie znaków wodnych w dokumentach w Aspose.Words dla Java
linktitle: Używanie znaków wodnych w dokumentach
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Dowiedz się, jak dodawać znaki wodne do dokumentów w Aspose.Words dla Java. Dostosuj tekstowe i graficzne znaki wodne, aby uzyskać profesjonalnie wyglądające dokumenty.
type: docs
weight: 15
url: /pl/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Wprowadzenie do dodawania znaków wodnych do dokumentów w Aspose.Words dla Java

W tym samouczku omówimy, jak dodawać znaki wodne do dokumentów za pomocą interfejsu API Aspose.Words for Java. Znaki wodne to przydatny sposób oznaczania dokumentów tekstem lub grafiką w celu wskazania ich stanu, poufności lub innych istotnych informacji. W tym przewodniku omówimy zarówno tekstowe, jak i graficzne znaki wodne.

## Konfigurowanie Aspose.Words dla Java

Zanim zaczniemy dodawać znaki wodne do dokumentów, musimy skonfigurować Aspose.Words dla Java. Aby rozpocząć, wykonaj następujące kroki:

1.  Pobierz Aspose.Words dla Java z[Tutaj](https://releases.aspose.com/words/java/).
2. Dodaj bibliotekę Aspose.Words for Java do swojego projektu Java.
3. Zaimportuj niezbędne klasy do swojego kodu Java.

Teraz, gdy mamy już skonfigurowaną bibliotekę, przejdźmy do dodawania znaków wodnych.

## Dodawanie tekstowych znaków wodnych

Tekstowe znaki wodne są częstym wyborem, gdy chcesz dodać informacje tekstowe do swoich dokumentów. Oto jak dodać tekstowy znak wodny za pomocą Aspose.Words dla Java:

```java
//Utwórz instancję dokumentu
Document doc = new Document("Document.docx");

// Zdefiniuj opcje TextWatermark
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Ustaw tekst i opcje znaku wodnego
doc.getWatermark().setText("Test", options);

// Zapisz dokument ze znakiem wodnym
doc.save("DocumentWithWatermark.docx");
```

## Dodawanie znaków wodnych obrazu

Oprócz tekstowych znaków wodnych do dokumentów można także dodawać graficzne znaki wodne. Oto jak dodać znak wodny obrazu:

```java
//Utwórz instancję dokumentu
Document doc = new Document("Document.docx");

// Załaduj obraz znaku wodnego
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Ustaw rozmiar i położenie znaku wodnego
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Dodaj znak wodny do dokumentu
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Zapisz dokument ze znakiem wodnym
doc.save("DocumentWithImageWatermark.docx");
```

## Dostosowywanie znaków wodnych

Znaki wodne można dostosować, dostosowując ich wygląd i położenie. W przypadku tekstowych znaków wodnych można zmienić czcionkę, rozmiar, kolor i układ. W przypadku graficznych znaków wodnych można modyfikować ich rozmiar i położenie, jak pokazano w poprzednich przykładach.

## Usuwanie znaków wodnych

Aby usunąć znaki wodne z dokumentu, możesz użyć następującego kodu:

```java
//Utwórz instancję dokumentu
Document doc = new Document("DocumentWithWatermark.docx");

// Usuń znak wodny
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Zapisz dokument bez znaku wodnego
doc.save("DocumentWithoutWatermark.docx");
```


## Wniosek

tym samouczku nauczyliśmy się, jak dodawać znaki wodne do dokumentów za pomocą Aspose.Words dla Java. Niezależnie od tego, czy chcesz dodać tekstowe, czy graficzne znaki wodne, Aspose.Words zapewnia narzędzia do dostosowywania ich i efektywnego zarządzania nimi. Możesz także usunąć znaki wodne, gdy nie są już potrzebne, dzięki czemu Twoje dokumenty będą czyste i profesjonalne.

## Często zadawane pytania

### Jak zmienić czcionkę tekstowego znaku wodnego?

 Aby zmienić czcionkę tekstowego znaku wodnego, zmodyfikuj plik`setFontFamily` nieruchomość w`TextWatermarkOptions`. Na przykład:

```java
options.setFontFamily("Times New Roman");
```

### Czy mogę dodać wiele znaków wodnych do jednego dokumentu?

 Tak, możesz dodać wiele znaków wodnych do dokumentu, tworząc ich wiele`Shape` obiekty z różnymi ustawieniami i dodanie ich do dokumentu.

### Czy można obrócić znak wodny?

 Tak, możesz obrócić znak wodny, ustawiając opcję`setRotation` nieruchomość w`Shape` obiekt. Wartości dodatnie obracają znak wodny w kierunku zgodnym z ruchem wskazówek zegara, a wartości ujemne obracają go w kierunku przeciwnym do ruchu wskazówek zegara.

### Jak ustawić półprzezroczysty znak wodny?

 Aby znak wodny stał się półprzezroczysty, ustaw opcję`setSemitransparent`własność do`true` w`TextWatermarkOptions`.

### Czy mogę dodać znaki wodne do określonych sekcji dokumentu?

Tak, możesz dodawać znaki wodne do określonych sekcji dokumentu, przeglądając sekcje i dodając znak wodny do wybranych sekcji.