---
title: Dokument mit Passwort verschlüsseln
linktitle: Dokument mit Passwort verschlüsseln
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Dokumente mit Aspose.Words für .NET mit einem Passwort verschlüsseln.
type: docs
weight: 10
url: /de/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
Dokumentensicherheit ist bei der Arbeit mit Dateien in einer C#-Anwendung von entscheidender Bedeutung. Mit der Aspose.Words-Bibliothek für .NET können Sie Ihre Dokumente ganz einfach schützen, indem Sie sie mit einem Passwort verschlüsseln. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung des Aspose.Words für .NET C#-Quellcodes zum Verschlüsseln eines Dokuments mithilfe der DocSaveOptions-Speicheroptionen.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Schritt 1: Definieren des Dokumentenverzeichnisses

Der erste Schritt besteht darin, das Verzeichnis festzulegen, in dem Sie das verschlüsselte Dokument speichern möchten. Sie müssen den vollständigen Verzeichnispfad angeben. Zum Beispiel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 2: Erstellen und Bearbeiten eines Dokuments

Anschließend können Sie ein Dokument erstellen und Inhalte hinzufügen. Verwenden Sie die von Aspose.Words bereitgestellte DocumentBuilder-Klasse, um den Inhalt Ihres Dokuments zu erstellen. Zum Beispiel :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

In diesem Beispiel erstellen wir ein neues leeres Dokument und schreiben dann mit DocumentBuilder den Text „Hello World!“.

## Schritt 3: Aufnahmeoptionen konfigurieren

Jetzt konfigurieren wir die Speicheroptionen für unser Dokument. Verwenden Sie die DocSaveOptions-Klasse, um Speichereinstellungen anzugeben. Zum Beispiel :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

In diesem Beispiel erstellen wir ein neues DocSaveOptions-Objekt und setzen die Password-Eigenschaft auf „password“, um das Dokument mit diesem Passwort zu verschlüsseln.

## Schritt 4: Aktivieren der Funktion „Dokument mit Passwort verschlüsseln“.

Wir haben die Optionen für bereits konfiguriert

Registrierung mit dem angegebenen Passwort, wodurch automatisch die Funktion „Dokument mit Passwort verschlüsseln“ aktiviert wird. Dadurch wird sichergestellt, dass das Dokument mit dem beim Speichern angegebenen Passwort verschlüsselt wird.

## Schritt 5: Speichern des Dokuments

Abschließend können Sie das Dokument mit der Save-Methode der Document-Klasse speichern. Geben Sie den vollständigen Pfad zur Datei und den gewünschten Dateinamen an. Zum Beispiel :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

Ersetzen Sie „dataDir“ unbedingt durch den Verzeichnispfad zu Ihren Dokumenten.

### Beispielquellcode für DocSaveOptions-Speicheroptionen mit der Funktion „Dokument mit Passwort verschlüsseln“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen und bearbeiten Sie ein Dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

// Konfigurieren Sie Speicheroptionen mit der Funktion „Dokument mit Passwort verschlüsseln“.
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

// Speichern Sie das Dokument mit den angegebenen Optionen
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## Abschluss

In diesem Handbuch haben wir erklärt, wie Sie die Aspose.Words-Bibliothek für .NET verwenden, um ein Dokument mithilfe der DocSaveOptions-Speicheroptionen mit einem Kennwort zu verschlüsseln. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Die Verschlüsselung des Dokuments mit einem Passwort gewährleistet dessen Vertraulichkeit und Sicherheit bei der Handhabung.