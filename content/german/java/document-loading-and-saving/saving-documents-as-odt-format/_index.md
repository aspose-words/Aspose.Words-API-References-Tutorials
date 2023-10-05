---
title: Speichern von Dokumenten im ODT-Format in Aspose.Words für Java
linktitle: Dokumente im ODT-Format speichern
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie Dokumente im ODT-Format mit Aspose.Words für Java speichern. Stellen Sie die Kompatibilität mit Open-Source-Office-Suiten sicher.
type: docs
weight: 19
url: /de/java/document-loading-and-saving/saving-documents-as-odt-format/
---

## Einführung in das Speichern von Dokumenten im ODT-Format in Aspose.Words für Java

In diesem Artikel erfahren Sie, wie Sie Dokumente mit Aspose.Words für Java im ODT-Format (Open Document Text) speichern. ODT ist ein beliebtes offenes Standarddokumentformat, das von verschiedenen Office-Suiten verwendet wird, darunter OpenOffice und LibreOffice. Durch das Speichern von Dokumenten im ODT-Format können Sie die Kompatibilität mit diesen Softwarepaketen sicherstellen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Java-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem System das Java Development Kit (JDK) installiert ist.

2.  Aspose.Words für Java: Laden Sie die Aspose.Words für Java-Bibliothek herunter und installieren Sie sie. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/words/java/).

3. Beispieldokument: Sie verfügen über ein Beispiel-Word-Dokument (z. B. „Document.docx“), das Sie in das ODT-Format konvertieren möchten.

## Schritt 1: Laden Sie das Dokument

Laden wir zunächst das Word-Dokument mit Aspose.Words für Java:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
```

 Hier,`"Your Directory Path"` sollte auf das Verzeichnis verweisen, in dem sich Ihr Dokument befindet.

## Schritt 2: Geben Sie die ODT-Speicheroptionen an

Um das Dokument als ODT zu speichern, müssen wir die ODT-Speicheroptionen angeben. Zusätzlich können wir die Maßeinheit für das Dokument festlegen. Open Office verwendet Zentimeter, während MS Office Zoll verwendet. Wir stellen es auf Zoll ein:

```java
OdtSaveOptions saveOptions = new OdtSaveOptions();
saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES);
```

## Schritt 3: Speichern Sie das Dokument

Jetzt ist es an der Zeit, das Dokument im ODT-Format zu speichern:

```java
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

 Hier,`"Your Directory Path"` sollte auf das Verzeichnis verweisen, in dem Sie die konvertierte ODT-Datei speichern möchten.

## Vollständiger Quellcode zum Speichern von Dokumenten im ODT-Format in Aspose.Words für Java

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
// Open Office verwendet Zentimeter, wenn Längen, Breiten und andere messbare Formatierungen angegeben werden
// und Inhaltseigenschaften in Dokumenten, während MS Office Zoll verwendet.
OdtSaveOptions saveOptions = new OdtSaveOptions(); { saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES); }
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Abschluss

In diesem Artikel haben wir erfahren, wie man Dokumente mit Aspose.Words für Java im ODT-Format speichert. Dies kann besonders nützlich sein, wenn Sie die Kompatibilität mit Open-Source-Office-Suiten wie OpenOffice und LibreOffice sicherstellen müssen.

## FAQs

### Wie kann ich Aspose.Words für Java herunterladen?

 Sie können Aspose.Words für Java von der Aspose-Website herunterladen. Besuchen[dieser Link](https://releases.aspose.com/words/java/)um auf die Download-Seite zuzugreifen.

### Welchen Vorteil bietet das Speichern von Dokumenten im ODT-Format?

Das Speichern von Dokumenten im ODT-Format stellt die Kompatibilität mit Open-Source-Office-Suiten wie OpenOffice und LibreOffice sicher und erleichtert Benutzern dieser Softwarepakete den Zugriff und die Bearbeitung Ihrer Dokumente.

### Muss ich beim Speichern im ODT-Format die Maßeinheit angeben?

Ja, es empfiehlt sich, die Maßeinheit anzugeben. Open Office verwendet standardmäßig Zentimeter, daher gewährleistet die Einstellung auf Zoll eine konsistente Formatierung.

### Kann ich mehrere Dokumente in einem Batch-Prozess in das ODT-Format konvertieren?

Ja, Sie können die Konvertierung mehrerer Dokumente in das ODT-Format mit Aspose.Words für Java automatisieren, indem Sie Ihre Dokumentdateien durchlaufen und den Konvertierungsprozess anwenden.

### Ist Aspose.Words für Java mit den neuesten Java-Versionen kompatibel?

Aspose.Words für Java wird regelmäßig aktualisiert, um die neuesten Java-Versionen zu unterstützen und so Kompatibilität und Leistungsverbesserungen sicherzustellen. Überprüfen Sie unbedingt die Systemanforderungen in der Dokumentation, um aktuelle Informationen zu erhalten.