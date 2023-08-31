---
title: Verschlüsseltes Word-Dokument laden
linktitle: Laden Sie das verschlüsselte Dokument in ein Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET verschlüsselte Word-Dokumente laden und speichern.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/load-encrypted-document/
---
Bei der Textverarbeitung mit verschlüsselten Word-Dokumenten in einer C#-Anwendung ist es wichtig, diese durch Angabe des richtigen Passworts korrekt laden zu können. Mit der Aspose.Words-Bibliothek für .NET können Sie mithilfe der entsprechenden Ladeoptionen problemlos verschlüsselte Dokumente in Word laden. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um ein verschlüsseltes Dokument mithilfe der LoadOptions-Ladeoptionen zu laden.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Laden eines verschlüsselten Dokuments

Der erste Schritt besteht darin, ein verschlüsseltes Dokument mit den entsprechenden Upload-Optionen hochzuladen. In unserem Fall verwenden wir die Document-Klasse, um das Dokument zu laden, indem wir den Dokumentpfad und das Passwort angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

In diesem Beispiel laden wir das Dokument „Encrypted.docx“, das sich im Dokumentenverzeichnis befindet, mit dem Passwort „password“.

## Speichern eines verschlüsselten Dokuments

Nach dem Hochladen eines verschlüsselten Dokuments können Sie dieses auch speichern, indem Sie ein neues Passwort für die Ausgabedatei festlegen. In unserem Beispiel verwenden wir die Klasse OdtSaveOptions, um das Dokument im ODT-Format mit einem neuen Passwort zu speichern. So geht's:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

In diesem Beispiel speichern wir das Dokument unter dem Namen „WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt“, indem wir das neue Passwort „newpassword“ angeben.

### Beispielquellcode für LoadOptions mit der Funktionalität „Load Encrypted Document“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie ein verschlüsseltes Dokument mit dem angegebenen Passwort
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

// Speichern Sie ein verschlüsseltes Dokument mit einem neuen Passwort
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie man verschlüsselte Dokumente mit der Aspose.Words-Bibliothek für .NET lädt und speichert. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das Hochladen verschlüsselter Dokumente schützt Ihre Daten und ermöglicht Ihnen die Arbeit mit geschützten Dokumenten in Aspose.Words.


### FAQs zum Laden verschlüsselter Dateien in Word-Dokumenten

#### F: Was sind verschlüsselte Word-Dokumente?

A: Verschlüsselte Word-Dokumente sind Dateien, die mit einem Passwort geschützt wurden, um unbefugten Zugriff zu verhindern. Diese Passwörter sind erforderlich, um den Inhalt des Dokuments zu öffnen, anzuzeigen oder zu ändern.

#### F: Wie geht Aspose.Words mit verschlüsselten Dokumenten in einer C#-Anwendung um?

A: Aspose.Words für .NET bietet die notwendigen Tools und Funktionen zum Laden verschlüsselter Word-Dokumente durch Angabe des richtigen Passworts und gewährleistet so einen sicheren Zugriff auf geschützte Dateien.

#### F: Kann ich das Passwort eines verschlüsselten Dokuments mit Aspose.Words ändern?

A: Auf jeden Fall! Mit Aspose.Words können Sie verschlüsselte Dokumente mit einem neuen Passwort speichern und haben so die Flexibilität, das Passwort bei Bedarf zu aktualisieren.

#### F: Welche Verschlüsselungsalgorithmen unterstützt Aspose.Words?

A: Aspose.Words unterstützt verschiedene Verschlüsselungsalgorithmen, einschließlich Advanced Encryption Standard (AES), der einen starken Datenschutz gewährleistet.

#### F: Ist Aspose.Words mit anderen Dokumentformaten außer Word kompatibel?

A: Ja, Aspose.Words unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, HTML, EPUB und mehr, was es zu einer vielseitigen Lösung für die Dokumentenverarbeitung macht.