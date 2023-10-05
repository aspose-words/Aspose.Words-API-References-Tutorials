---
title: Bestimmen des Dokumentformats in Aspose.Words für Java
linktitle: Bestimmen des Dokumentformats
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words Dokumentformate in Java erkennen. Identifizieren Sie DOC, DOCX und mehr. Dateien effizient organisieren.
type: docs
weight: 25
url: /de/java/document-loading-and-saving/determining-document-format/
---

## Einführung in die Bestimmung des Dokumentformats in Aspose.Words für Java

Wenn Sie mit der Dokumentverarbeitung in Java arbeiten, ist es wichtig, das Format der Dateien zu bestimmen, mit denen Sie arbeiten. Aspose.Words für Java bietet leistungsstarke Funktionen zum Identifizieren von Dokumentformaten und wir führen Sie durch den Prozess.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- [Aspose.Words für Java](https://releases.aspose.com/words/java/)
- Java Development Kit (JDK) auf Ihrem System installiert
- Grundkenntnisse der Java-Programmierung

## Schritt 1: Verzeichniseinrichtung

Zuerst müssen wir die notwendigen Verzeichnisse einrichten, um unsere Dateien effektiv zu organisieren. Wir erstellen Verzeichnisse für verschiedene Dokumenttypen.

```java
File supportedDir = new File("Your Directory Path" + "Supported");
File unknownDir = new File("Your Directory Path" + "Unknown");
File encryptedDir = new File("Your Directory Path" + "Encrypted");
File pre97Dir = new File("Your Directory Path" + "Pre97");

// Erstellen Sie die Verzeichnisse, falls sie noch nicht vorhanden sind.
if (!supportedDir.exists())
    supportedDir.mkdir();
if (!unknownDir.exists())
    unknownDir.mkdir();
if (!encryptedDir.exists())
    encryptedDir.mkdir();
if (!pre97Dir.exists())
    pre97Dir.mkdir();
```

Wir haben Verzeichnisse für unterstützte, unbekannte, verschlüsselte und vor 97 erstellte Dokumenttypen erstellt.

## Schritt 2: Dokumentformat erkennen

Lassen Sie uns nun das Format der Dokumente in unseren Verzeichnissen ermitteln. Um dies zu erreichen, verwenden wir Aspose.Words für Java.

```java
Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
    .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
    .map(File::getPath)
    .collect(Collectors.toSet());

for (String fileName : listFiles) {
    String nameOnly = Paths.get(fileName).getFileName().toString();
    System.out.println(nameOnly);
    FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);

    // Zeigen Sie den Dokumenttyp an
    switch (info.getLoadFormat()) {
        case LoadFormat.DOC:
            System.out.println("\tMicrosoft Word 97-2003 document.");
            break;
        // Fügen Sie nach Bedarf Fälle für andere Dokumentformate hinzu
    }

    // Behandeln Sie verschlüsselte Dokumente
    if (info.isEncrypted()) {
        System.out.println("\tAn encrypted document.");
        FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
    } else {
        // Behandeln Sie andere Dokumenttypen
        switch (info.getLoadFormat()) {
            case LoadFormat.DOC_PRE_WORD_60:
                FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                break;
            case LoadFormat.UNKNOWN:
                FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                break;
            default:
                FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                break;
        }
    }
}
```

In diesem Codeausschnitt durchlaufen wir die Dateien, erkennen ihre Formate und organisieren sie in den jeweiligen Verzeichnissen.

## Vollständiger Quellcode zur Bestimmung des Dokumentformats in Aspose.Words für Java

```java
        File supportedDir = new File("Your Directory Path" + "Supported");
        File unknownDir = new File("Your Directory Path" + "Unknown");
        File encryptedDir = new File("Your Directory Path" + "Encrypted");
        File pre97Dir = new File("Your Directory Path" + "Pre97");
        // Erstellen Sie die Verzeichnisse, falls sie noch nicht vorhanden sind.
        if (supportedDir.exists() == false)
            supportedDir.mkdir();
        if (unknownDir.exists() == false)
            unknownDir.mkdir();
        if (encryptedDir.exists() == false)
            encryptedDir.mkdir();
        if (pre97Dir.exists() == false)
            pre97Dir.mkdir();
        Set<String> listFiles = Stream.of(new File("Your Directory Path").listFiles())
                .filter(file -> !file.getName().endsWith("Corrupted document.docx") && !Files.isDirectory(file.toPath()))
                .map(File::getPath)
                .collect(Collectors.toSet());
        for (String fileName : listFiles) {
            String nameOnly = Paths.get(fileName).getFileName().toString();
            System.out.println(nameOnly);
            FileFormatInfo info = FileFormatUtil.detectFileFormat(fileName);
            // Zeigen Sie den Dokumenttyp an
            switch (info.getLoadFormat()) {
                case LoadFormat.DOC:
                    System.out.println("\tMicrosoft Word 97-2003 document.");
                    break;
                case LoadFormat.DOT:
                    System.out.println("\tMicrosoft Word 97-2003 template.");
                    break;
                case LoadFormat.DOCX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Document.");
                    break;
                case LoadFormat.DOCM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
                    break;
                case LoadFormat.DOTX:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Free Template.");
                    break;
                case LoadFormat.DOTM:
                    System.out.println("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
                    break;
                case LoadFormat.FLAT_OPC:
                    System.out.println("\tFlat OPC document.");
                    break;
                case LoadFormat.RTF:
                    System.out.println("\tRTF format.");
                    break;
                case LoadFormat.WORD_ML:
                    System.out.println("\tMicrosoft Word 2003 WordprocessingML format.");
                    break;
                case LoadFormat.HTML:
                    System.out.println("\tHTML format.");
                    break;
                case LoadFormat.MHTML:
                    System.out.println("\tMHTML (Web archive) format.");
                    break;
                case LoadFormat.ODT:
                    System.out.println("\tOpenDocument Text.");
                    break;
                case LoadFormat.OTT:
                    System.out.println("\tOpenDocument Text Template.");
                    break;
                case LoadFormat.DOC_PRE_WORD_60:
                    System.out.println("\tMS Word 6 or Word 95 format.");
                    break;
                case LoadFormat.UNKNOWN:
                    System.out.println("\tUnknown format.");
                    break;
            }
            if (info.isEncrypted()) {
                System.out.println("\tAn encrypted document.");
                FileUtils.copyFile(new File(fileName), new File(encryptedDir, nameOnly));
            } else {
                switch (info.getLoadFormat()) {
                    case LoadFormat.DOC_PRE_WORD_60:
                        FileUtils.copyFile(new File(fileName), new File(pre97Dir, nameOnly));
                        break;
                    case LoadFormat.UNKNOWN:
                        FileUtils.copyFile(new File(fileName), new File(unknownDir, nameOnly));
                        break;
                    default:
                        FileUtils.copyFile(new File(fileName), new File(supportedDir, nameOnly));
                        break;
                }
            }
        }

```

## Abschluss

Die Bestimmung von Dokumentformaten in Aspose.Words für Java ist für eine effiziente Dokumentenverarbeitung unerlässlich. Mit den in diesem Handbuch beschriebenen Schritten können Sie Dokumenttypen identifizieren und sie in Ihren Java-Anwendungen entsprechend verarbeiten.

## FAQs

### Wie installiere ich Aspose.Words für Java?

 Sie können Aspose.Words für Java von herunterladen[Hier](https://releases.aspose.com/words/java/) und befolgen Sie die mitgelieferten Installationsanweisungen.

### Welche Dokumentformate werden unterstützt?

Aspose.Words für Java unterstützt verschiedene Dokumentformate, darunter DOC, DOCX, RTF, HTML und mehr. Eine vollständige Liste finden Sie in der Dokumentation.

### Wie kann ich verschlüsselte Dokumente mit Aspose.Words für Java erkennen?

 Du kannst den ... benutzen`FileFormatUtil.detectFileFormat()` Methode zum Erkennen verschlüsselter Dokumente, wie in diesem Handbuch gezeigt.

### Gibt es Einschränkungen bei der Arbeit mit älteren Dokumentformaten?

Bei älteren Dokumentformaten wie MS Word 6 oder Word 95 können Einschränkungen hinsichtlich der Funktionen und der Kompatibilität mit modernen Anwendungen auftreten. Erwägen Sie bei Bedarf eine Aktualisierung oder Konvertierung dieser Dokumente.

### Kann ich die Dokumentformaterkennung in meiner Java-Anwendung automatisieren?

Ja, Sie können die Dokumentformaterkennung automatisieren, indem Sie den bereitgestellten Code in Ihre Java-Anwendung integrieren. Dadurch können Sie Dokumente basierend auf ihren erkannten Formaten verarbeiten.