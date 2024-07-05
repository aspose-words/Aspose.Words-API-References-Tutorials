---
title: Dokument mit Passwort verschlüsseln
linktitle: Dokument mit Passwort verschlüsseln
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Dokumente mit einem Kennwort verschlüsseln.
type: docs
weight: 10
url: /de/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Dokumentensicherheit ist bei der Textverarbeitung mit Dateien in einer C#-Anwendung unerlässlich. Mit der Aspose.Words-Bibliothek für .NET können Sie Ihre Dokumente ganz einfach schützen, indem Sie sie mit einem Kennwort verschlüsseln. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit dem C#-Quellcode von Aspose.Words für .NET ein Dokument mithilfe der Speicheroptionen von DocSaveOptions verschlüsseln.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Schritt 1: Dokumentverzeichnis festlegen

Der erste Schritt besteht darin, das Verzeichnis festzulegen, in dem Sie das verschlüsselte Dokument speichern möchten. Sie müssen den vollständigen Verzeichnispfad angeben. Beispiel:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Ersetzen Sie „IHR DOKUMENTVERZEICHNIS“ unbedingt durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

## Schritt 2: Erstellen und Bearbeiten eines Dokuments

Anschließend können Sie ein Dokument erstellen und Inhalt hinzufügen. Verwenden Sie die von Aspose.Words bereitgestellte DocumentBuilder-Klasse, um den Inhalt Ihres Dokuments zu erstellen. Beispiel:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

In diesem Beispiel erstellen wir ein neues leeres Dokument und verwenden dann DocumentBuilder, um den Text „Hallo Welt!“ zu schreiben.

## Schritt 3: Aufzeichnungsoptionen konfigurieren

Konfigurieren wir nun die Speicheroptionen für unser Dokument. Verwenden Sie die Klasse DocSaveOptions, um die Speichereinstellungen festzulegen. Beispiel:

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

In diesem Beispiel erstellen wir ein neues DocSaveOptions-Objekt und setzen die Password-Eigenschaft auf „password“, um das Dokument mit diesem Passwort zu verschlüsseln.

## Schritt 4: Funktion „Dokument mit Passwort verschlüsseln“ aktivieren

Wir haben bereits die Optionen für

Registrierung mit dem angegebenen Passwort, wodurch automatisch die Funktion „Dokument mit Passwort verschlüsseln“ aktiviert wird. Dadurch wird sichergestellt, dass das Dokument beim Speichern mit dem angegebenen Passwort verschlüsselt wird.

## Schritt 5: Speichern des Dokuments

Abschließend können Sie das Dokument mit der Save-Methode der Document-Klasse speichern. Geben Sie den vollständigen Pfad zur Datei und den gewünschten Dateinamen an. Beispiel:

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Ersetzen Sie „dataDir“ unbedingt durch den Verzeichnispfad zu Ihren Dokumenten.

### Beispielquellcode für DocSaveOptions-Speicheroptionen mit der Funktion „Dokument mit Kennwort verschlüsseln“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen und Bearbeiten eines Dokuments
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Konfigurieren Sie Speicheroptionen mit der Funktion „Dokument mit Kennwort verschlüsseln“
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Speichern Sie das Dokument mit den angegebenen Optionen
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie die Aspose.Words-Bibliothek für .NET verwenden, um ein Dokument mit einem Kennwort zu verschlüsseln, indem Sie die Speicheroptionen DocSaveOptions verwenden. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktion problemlos in Ihrer C#-Anwendung anwenden. Die Verschlüsselung des Dokuments mit einem Kennwort garantiert dessen Vertraulichkeit und Sicherheit bei der Verarbeitung.