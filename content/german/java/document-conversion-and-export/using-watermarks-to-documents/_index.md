---
title: Verwenden von Wasserzeichen für Dokumente in Aspose.Words für Java
linktitle: Verwenden von Wasserzeichen für Dokumente
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie in Aspose.Words für Java Wasserzeichen zu Dokumenten hinzufügen. Passen Sie Text- und Bildwasserzeichen an, um Dokumente professionell aussehen zu lassen.
type: docs
weight: 15
url: /de/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Einführung in das Hinzufügen von Wasserzeichen zu Dokumenten in Aspose.Words für Java

In diesem Tutorial erfahren Sie, wie Sie mit der Aspose.Words for Java-API Wasserzeichen zu Dokumenten hinzufügen. Wasserzeichen sind eine nützliche Möglichkeit, Dokumente mit Text oder Grafiken zu kennzeichnen, um ihren Status, ihre Vertraulichkeit oder andere relevante Informationen anzuzeigen. In diesem Leitfaden werden wir sowohl Text- als auch Bildwasserzeichen behandeln.

## Einrichten von Aspose.Words für Java

Bevor wir mit dem Hinzufügen von Wasserzeichen zu Dokumenten beginnen, müssen wir Aspose.Words für Java einrichten. Befolgen Sie diese Schritte, um zu beginnen:

1.  Laden Sie Aspose.Words für Java herunter von[Hier](https://releases.aspose.com/words/java/).
2. Fügen Sie die Aspose.Words for Java-Bibliothek zu Ihrem Java-Projekt hinzu.
3. Importieren Sie die erforderlichen Klassen in Ihren Java-Code.

Nachdem wir nun die Bibliothek eingerichtet haben, können wir mit dem Hinzufügen von Wasserzeichen fortfahren.

## Hinzufügen von Textwasserzeichen

Textwasserzeichen werden häufig verwendet, wenn Sie Ihren Dokumenten Textinformationen hinzufügen möchten. So können Sie mit Aspose.Words für Java ein Textwasserzeichen hinzufügen:

```java
//Erstellen Sie eine Dokumentinstanz
Document doc = new Document("Document.docx");

// Definieren Sie TextWatermarkOptions
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Legen Sie den Wasserzeichentext und die Optionen fest
doc.getWatermark().setText("Test", options);

// Speichern Sie das Dokument mit dem Wasserzeichen
doc.save("DocumentWithWatermark.docx");
```

## Bildwasserzeichen hinzufügen

Zusätzlich zu Textwasserzeichen können Sie Ihren Dokumenten auch Bildwasserzeichen hinzufügen. So fügen Sie ein Bildwasserzeichen hinzu:

```java
//Erstellen Sie eine Dokumentinstanz
Document doc = new Document("Document.docx");

// Laden Sie das Bild für das Wasserzeichen
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Legen Sie die Größe und Position des Wasserzeichens fest
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Fügen Sie das Wasserzeichen zum Dokument hinzu
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Speichern Sie das Dokument mit dem Wasserzeichen
doc.save("DocumentWithImageWatermark.docx");
```

## Anpassen von Wasserzeichen

Sie können Wasserzeichen anpassen, indem Sie deren Aussehen und Position anpassen. Bei Textwasserzeichen können Sie Schriftart, Größe, Farbe und Layout ändern. Bei Bildwasserzeichen können Sie deren Größe und Position ändern, wie in den vorherigen Beispielen gezeigt.

## Wasserzeichen entfernen

Um Wasserzeichen aus einem Dokument zu entfernen, können Sie den folgenden Code verwenden:

```java
//Erstellen Sie eine Dokumentinstanz
Document doc = new Document("DocumentWithWatermark.docx");

// Entfernen Sie das Wasserzeichen
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Speichern Sie das Dokument ohne Wasserzeichen
doc.save("DocumentWithoutWatermark.docx");
```


## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Words für Java Wasserzeichen zu Dokumenten hinzufügt. Unabhängig davon, ob Sie Text- oder Bildwasserzeichen hinzufügen müssen, bietet Aspose.Words die Tools, um diese effizient anzupassen und zu verwalten. Sie können Wasserzeichen auch entfernen, wenn sie nicht mehr benötigt werden, um sicherzustellen, dass Ihre Dokumente sauber und professionell sind.

## FAQs

### Wie kann ich die Schriftart eines Textwasserzeichens ändern?

 Um die Schriftart eines Textwasserzeichens zu ändern, ändern Sie die`setFontFamily` Eigentum in der`TextWatermarkOptions`. Zum Beispiel:

```java
options.setFontFamily("Times New Roman");
```

### Kann ich einem einzelnen Dokument mehrere Wasserzeichen hinzufügen?

 Ja, Sie können einem Dokument mehrere Wasserzeichen hinzufügen, indem Sie mehrere erstellen`Shape` Objekte mit unterschiedlichen Einstellungen bearbeiten und zum Dokument hinzufügen.

### Ist es möglich, ein Wasserzeichen zu drehen?

 Ja, Sie können ein Wasserzeichen drehen, indem Sie das festlegen`setRotation` Eigentum in der`Shape` Objekt. Positive Werte drehen das Wasserzeichen im Uhrzeigersinn, negative Werte drehen es gegen den Uhrzeigersinn.

### Wie kann ich ein Wasserzeichen halbtransparent machen?

 Um ein Wasserzeichen halbtransparent zu machen, legen Sie fest`setSemitransparent`Eigentum zu`true` im`TextWatermarkOptions`.

### Kann ich Wasserzeichen zu bestimmten Abschnitten eines Dokuments hinzufügen?

Ja, Sie können Wasserzeichen zu bestimmten Abschnitten eines Dokuments hinzufügen, indem Sie die Abschnitte durchlaufen und das Wasserzeichen zu den gewünschten Abschnitten hinzufügen.