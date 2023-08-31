---
title: Bildaufzählung nicht speichern
linktitle: Bildaufzählung nicht speichern
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie das Speichern von Bildaufzählungszeichen in Word-Dokumenten mit Aspose.Words für .NET deaktivieren.
type: docs
weight: 10
url: /de/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Bildaufzählungszeichen sind eine häufig verwendete Funktion in Word-Dokumenten, um benutzerdefinierte Aufzählungszeichen hinzuzufügen. In einigen Fällen kann es jedoch erforderlich sein, die Bildaufzählungsregistrierung zu deaktivieren, wenn Dokumente mithilfe der Aspose.Words-Bibliothek für .NET bearbeitet werden. In dieser Schritt-für-Schritt-Anleitung erklären wir, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um das Speichern von Bildaufzählungszeichen mithilfe der Speicheroptionen von DocSaveOptions zu deaktivieren.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Schritt 1: Festlegen des Dokumentenverzeichnisses

Der erste Schritt besteht darin, das Verzeichnis zu definieren, in dem sich Ihre Dokumente befinden. Sie müssen den vollständigen Verzeichnispfad angeben. Zum Beispiel :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Stellen Sie sicher, dass Sie „IHR DOKUMENTENVERZEICHNIS“ durch den tatsächlichen Pfad zu Ihrem Dokumentenverzeichnis ersetzen.

## Schritt 2: Laden des Dokuments mit Bildaufzählungszeichen

Als nächstes müssen Sie das Dokument mit Bildaufzählungszeichen laden. Verwenden Sie die Document-Klasse, um das Dokument aus einer Datei zu laden. Zum Beispiel :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

In diesem Beispiel laden wir das Dokument aus der Datei „Image Bullet Points.docx“.

  befindet sich im Dokumentenverzeichnis.

## Schritt 3: Aufnahmeoptionen konfigurieren

Jetzt konfigurieren wir die Speicheroptionen für unser Dokument. Verwenden Sie die DocSaveOptions-Klasse, um Speichereinstellungen anzugeben. Zum Beispiel :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

In diesem Beispiel erstellen wir ein neues DocSaveOptions-Objekt und setzen die SavePictureBullet-Eigenschaft auf „false“, um das Speichern von Bildaufzählungszeichen zu deaktivieren.

## Schritt 4: Aktivieren Sie die Funktion „Bildaufzählung nicht speichern“.

Um die Funktion „Bildaufzählungszeichen nicht speichern“ zu aktivieren, haben wir die Speicheroptionen bereits so konfiguriert, dass „SavePictureBullet“ auf „false“ gesetzt ist. Dadurch wird sichergestellt, dass Bildaufzählungszeichen nicht im endgültigen Dokument gespeichert werden.

## Schritt 5: Speichern Sie das Dokument

Abschließend können Sie das Dokument mit der Save-Methode der Document-Klasse speichern. Geben Sie den vollständigen Pfad zur Datei und den gewünschten Dateinamen an. Zum Beispiel :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Ersetzen Sie „dataDir“ unbedingt durch den Verzeichnispfad zu Ihren Dokumenten.

## Beispielquellcode für DocSaveOptions-Speicheroptionen mit der Funktion „Bildaufzählungszeichen nicht speichern“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laden Sie das Dokument mit Bildaufzählungszeichen
Document doc = new Document(dataDir + "Image bullet points.docx");

// Konfigurieren Sie Speicheroptionen mit der Funktion „Bildaufzählung nicht speichern“.
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Speichern Sie das Dokument mit den angegebenen Optionen
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Abschluss

In dieser Anleitung haben wir erläutert, wie Sie das Speichern von Bildaufzählungszeichen in einem Dokument mithilfe der Aspose.Words-Bibliothek für .NET deaktivieren. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Das Deaktivieren der Bildaufzählungsspeicherung kann in manchen Situationen nützlich sein, um die Struktur und Formatierung des Dokuments beizubehalten, ohne Bildaufzählungszeichen zu speichern.