---
title: Verwenden Sie den Temp-Ordner
linktitle: Verwenden Sie den Temp-Ordner
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie beim Hochladen von Dokumenten mit Aspose.Words für .NET einen temporären Ordner verwenden.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/use-temp-folder/
---

Beim Arbeiten mit Word-Dokumenten in einer C#-Anwendung kann es erforderlich sein, einen temporären Ordner zum Speichern temporärer Dateien zu verwenden, die während der Dokumentverarbeitung generiert werden. Mit der Aspose.Words-Bibliothek für .NET können Sie mithilfe der LoadOptions-Ladeoptionen ganz einfach einen temporären Ordner angeben. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie Aspose.Words für .NET C#-Quellcode verwenden, um ein Dokument mithilfe eines temporären Ordners zu laden, der mit den LoadOptions-Ladeoptionen angegeben wurde.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Ladeoptionen konfigurieren

Der erste Schritt besteht darin, die Ladeoptionen für unser Dokument zu konfigurieren. Verwenden Sie die LoadOptions-Klasse, um Ladeparameter anzugeben. In unserem Fall müssen wir die TempFolder-Eigenschaft auf den Pfad des gewünschten temporären Ordners setzen. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die TempFolder-Eigenschaft auf den Pfad des gewünschten temporären Ordners.

## Laden Sie das Dokument mithilfe des angegebenen temporären Ordners hoch

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

In diesem Beispiel laden wir das Dokument „Document.docx“, das sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

### Beispielquellcode für LoadOptions mit der Funktionalität „Temporären Ordner verwenden“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurieren Sie Ladeoptionen mit der Funktion „Temporären Ordner verwenden“.
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };

// Laden Sie das Dokument mithilfe eines angegebenen temporären Ordners
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET ein Dokument mithilfe eines angegebenen temporären Ordners hochladen. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Durch die Verwendung eines temporären Ordners können temporäre Dateien, die während der Dokumentenverarbeitung generiert werden, auf organisierte und effiziente Weise gespeichert werden.
