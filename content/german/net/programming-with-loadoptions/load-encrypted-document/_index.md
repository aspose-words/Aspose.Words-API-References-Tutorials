---
title: Verschlüsselt in Word-Dokument laden
linktitle: Verschlüsseltes Dokument in Word-Dokument laden
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET verschlüsselte Word-Dokumente laden und speichern.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/load-encrypted-document/
---
Bei der Verarbeitung verschlüsselter Word-Dokumente in einer C#-Anwendung ist es wichtig, diese durch Angabe des richtigen Passworts korrekt laden zu können. Mit der Aspose.Words-Bibliothek für .NET können Sie verschlüsselte Word-Dokumente mithilfe der entsprechenden Ladeoptionen problemlos laden. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um ein verschlüsseltes Dokument mithilfe der Ladeoptionen LoadOptions zu laden.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Laden eines verschlüsselten Dokuments

Der erste Schritt besteht darin, ein verschlüsseltes Dokument mit den entsprechenden Upload-Optionen hochzuladen. In unserem Fall verwenden wir die Document-Klasse, um das Dokument zu laden, indem wir den Dokumentpfad und das Passwort angeben. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

In diesem Beispiel laden wir das im Dokumentenverzeichnis liegende Dokument „Encrypted.docx“ mit dem Passwort „password“.

## Speichern eines verschlüsselten Dokuments

Nach dem Hochladen eines verschlüsselten Dokuments können Sie es auch speichern, indem Sie ein neues Passwort für die Ausgabedatei angeben. In unserem Beispiel verwenden wir die Klasse OdtSaveOptions, um das Dokument im ODT-Format mit einem neuen Passwort zu speichern. So geht's:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

In diesem Beispiel speichern wir das Dokument unter dem Namen „WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt“ indem wir das neue Passwort „newpassword“ angeben.

### Beispielquellcode für LoadOptions mit der Funktion „Verschlüsseltes Dokument laden“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie ein verschlüsseltes Dokument mit dem angegebenen Passwort
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

// Speichern Sie ein verschlüsseltes Dokument mit einem neuen Passwort
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie verschlüsselte Dokumente mit der Aspose.Words-Bibliothek für .NET laden und speichern. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Durch das Hochladen verschlüsselter Dokumente bleiben Ihre Daten sicher und Sie können mit geschützten Dokumenten in Aspose.Words arbeiten.


### FAQs zum verschlüsselten Laden in Word-Dokumenten

#### F: Was sind verschlüsselte Word-Dokumente?

A: Verschlüsselte Word-Dokumente sind Dateien, die mit einem Kennwort geschützt wurden, um unbefugten Zugriff zu verhindern. Diese Kennwörter sind erforderlich, um den Inhalt des Dokuments zu öffnen, anzuzeigen oder zu ändern.

#### F: Wie verarbeitet Aspose.Words verschlüsselte Dokumente in einer C#-Anwendung?

A: Aspose.Words für .NET bietet die erforderlichen Tools und Funktionen zum Laden verschlüsselter Word-Dokumente durch Angabe des richtigen Kennworts und gewährleistet so einen sicheren Zugriff auf geschützte Dateien.

#### F: Kann ich mit Aspose.Words das Passwort eines verschlüsselten Dokuments ändern?

A: Auf jeden Fall! Aspose.Words ermöglicht es Ihnen, verschlüsselte Dokumente mit einem neuen Passwort zu speichern und bietet Ihnen die Flexibilität, das Passwort bei Bedarf zu aktualisieren.

#### F: Welche Verschlüsselungsalgorithmen unterstützt Aspose.Words?

A: Aspose.Words unterstützt verschiedene Verschlüsselungsalgorithmen, darunter Advanced Encryption Standard (AES), der einen starken Datenschutz gewährleistet.

#### F: Ist Aspose.Words mit anderen Dokumentformaten außer Word kompatibel?

A: Ja, Aspose.Words unterstützt eine große Bandbreite an Dokumentformaten, darunter PDF, HTML, EPUB und mehr, und ist damit eine vielseitige Lösung für die Dokumentenverarbeitung.