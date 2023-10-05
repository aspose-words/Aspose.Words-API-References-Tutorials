---
title: Verwenden von OLE-Objekten und ActiveX-Steuerelementen in Aspose.Words für Java
linktitle: Verwendung von OLE-Objekten und ActiveX-Steuerelementen
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie OLE-Objekte und ActiveX-Steuerelemente in Aspose.Words für Java verwenden. Erstellen Sie ganz einfach interaktive Dokumente. Jetzt loslegen!
type: docs
weight: 21
url: /de/java/using-document-elements/using-ole-objects-and-activex/
---
In diesem Tutorial erfahren Sie, wie Sie mit OLE-Objekten (Object Linking and Embedding) und ActiveX-Steuerelementen in Aspose.Words für Java arbeiten. OLE-Objekte und ActiveX-Steuerelemente sind leistungsstarke Tools, mit denen Sie Ihre Dokumente durch das Einbetten oder Verknüpfen externer Inhalte wie Tabellenkalkulationen, Multimediadateien oder interaktiver Steuerelemente verbessern können. Folgen Sie uns, während wir uns mit den Codebeispielen befassen und lernen, wie Sie diese Funktionen effektiv nutzen können.

### Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Words für Java: Stellen Sie sicher, dass die Aspose.Words-Bibliothek in Ihrem Java-Projekt installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/words/java/).

2. Java-Entwicklungsumgebung: Auf Ihrem System sollte eine funktionierende Java-Entwicklungsumgebung eingerichtet sein.

### Einfügen eines OLE-Objekts

Beginnen wir mit dem Einfügen eines OLE-Objekts in ein Word-Dokument. Wir erstellen ein einfaches Word-Dokument und fügen dann ein OLE-Objekt ein, das eine Webseite darstellt.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com“, „htmlfile“, true, true, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

In diesem Code erstellen wir ein neues Dokument und fügen ein OLE-Objekt ein, das die Aspose-Website anzeigt. Sie können die URL durch den gewünschten Inhalt ersetzen.

### Einfügen eines OLE-Objekts mit OlePackage

Lassen Sie uns als Nächstes untersuchen, wie Sie mithilfe eines OlePackage ein OLE-Objekt einfügen. Dadurch können Sie externe Dateien als OLE-Objekte in Ihr Dokument einbetten.

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

In diesem Beispiel fügen wir ein OLE-Objekt mithilfe eines OlePackage ein, sodass Sie externe Dateien als eingebettete Objekte einbinden können.

### Einfügen eines OLE-Objekts als Symbol

Sehen wir uns nun an, wie man ein OLE-Objekt als Symbol einfügt. Dies ist nützlich, wenn Sie ein Symbol anzeigen möchten, das eine eingebettete Datei darstellt.

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

In diesem Code fügen wir ein OLE-Objekt als Symbol ein und sorgen so für eine optisch ansprechendere Darstellung des eingebetteten Inhalts.

### Eigenschaften des ActiveX-Steuerelements lesen

Lassen Sie uns nun unseren Fokus auf ActiveX-Steuerelemente verlagern. Wir lernen, wie man Eigenschaften von ActiveX-Steuerelementen in einem Word-Dokument liest.

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

In diesem Code durchlaufen wir die Formen in einem Word-Dokument, identifizieren ActiveX-Steuerelemente und rufen ihre Eigenschaften ab.

### Abschluss

Glückwunsch! Sie haben gelernt, wie Sie in Aspose.Words für Java mit OLE-Objekten und ActiveX-Steuerelementen arbeiten. Diese Funktionen eröffnen eine Welt voller Möglichkeiten für die Erstellung dynamischer und interaktiver Dokumente.

### FAQs

### Welchen Zweck haben OLE-Objekte in einem Word-Dokument? 
   - Mit OLE-Objekten können Sie externe Inhalte wie Dateien oder Webseiten in ein Word-Dokument einbetten oder verlinken.

### Kann ich das Erscheinungsbild von OLE-Objekten in meinem Dokument anpassen? 
   - Ja, Sie können das Erscheinungsbild von OLE-Objekten anpassen, einschließlich der Festlegung von Symbolen und Dateinamen.

### Was sind ActiveX-Steuerelemente und wie können sie meine Dokumente verbessern? 
   - ActiveX-Steuerelemente sind interaktive Elemente, die Ihren Word-Dokumenten Funktionen hinzufügen können, beispielsweise Formularsteuerelemente oder Multimedia-Player.

### Ist Aspose.Words für Java für die Dokumentenautomatisierung auf Unternehmensebene geeignet? 
   - Ja, Aspose.Words für Java ist eine leistungsstarke Bibliothek zur Automatisierung der Dokumentenerstellung und -bearbeitung in Java-Anwendungen.

### Wo erhalte ich Zugriff auf Aspose.Words für Java? 
   -  Sie können Aspose.Words für Java herunterladen von[Hier](https://releases.aspose.com/words/java/).

Beginnen Sie noch heute mit Aspose.Words für Java und nutzen Sie das volle Potenzial der Dokumentenautomatisierung und -anpassung!
