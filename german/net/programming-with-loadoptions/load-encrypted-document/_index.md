---
title: Verschlüsseltes Dokument laden
linktitle: Verschlüsseltes Dokument laden
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie verschlüsselte Dokumente mit Aspose.Words für .NET laden und speichern.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/load-encrypted-document/
---

Bei der Textverarbeitung mit verschlüsselten Dokumenten in einer C#-Anwendung ist es wichtig, diese durch Angabe des richtigen Passworts korrekt laden zu können. Mit der Aspose.Words-Bibliothek für .NET können Sie mithilfe der entsprechenden Ladeoptionen problemlos verschlüsselte Dokumente laden. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um ein verschlüsseltes Dokument mithilfe der LoadOptions-Ladeoptionen zu laden.

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

//Speichern Sie ein verschlüsseltes Dokument mit einem neuen Passwort
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie man verschlüsselte Dokumente mit der Aspose.Words-Bibliothek für .NET lädt und speichert. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das Hochladen verschlüsselter Dokumente schützt Ihre Daten und ermöglicht Ihnen die Arbeit mit geschützten Dokumenten in Aspose.Words.