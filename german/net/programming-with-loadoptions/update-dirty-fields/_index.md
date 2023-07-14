---
title: Aktualisieren Sie schmutzige Felder
linktitle: Aktualisieren Sie schmutzige Felder
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie ein Word-Dokument laden, indem Sie fehlerhafte Felder mit Aspose.Words für .NET aktualisieren.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/update-dirty-fields/
---

Bei der Textverarbeitung mit Word-Dokumenten in einer C#-Anwendung kann es erforderlich sein, fehlerhafte Felder zu aktualisieren, um die neuesten Werte anzuzeigen. Mit der Aspose.Words-Bibliothek für .NET können Sie fehlerhafte Felder beim Laden des Dokuments mithilfe von LoadOptions problemlos aktualisieren. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung von Aspose.Words für .NET C#-Quellcode zum Laden eines Dokuments durch Aktualisieren fehlerhafter Felder mithilfe von LoadOptions.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Ladeoptionen konfigurieren

Der erste Schritt besteht darin, die Ladeoptionen für unser Dokument zu konfigurieren. Verwenden Sie die LoadOptions-Klasse, um Ladeparameter anzugeben. In unserem Fall müssen wir die Eigenschaft „UpdateDirtyFields“ auf „true“ setzen, um fehlerhafte Felder zu aktualisieren. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { UpdateDirtyFields = true };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die UpdateDirtyFields-Eigenschaft auf „true“, um fehlerhafte Felder beim Laden des Dokuments zu aktualisieren.

## Dokument wird geladen und fehlerhafte Felder werden aktualisiert

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Dirty field.docx", loadOptions);
```

In diesem Beispiel laden wir das Dokument „Dirty field.docx“, das sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

## Beispielquellcode für LoadOptions mit der Funktionalität „Dirty Fields aktualisieren“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurieren Sie Ladeoptionen mit der Funktion „Dirty Fields aktualisieren“.
LoadOptions loadOptions = new LoadOptions { UpdateDirtyFields = true };

// Laden Sie das Dokument, indem Sie die fehlerhaften Felder aktualisieren
Document doc = new Document(dataDir + "Dirty field.docx", loadOptions);

// Speichern Sie das Dokument
doc.Save(dataDir + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie ein Dokument hochladen, indem Sie fehlerhafte Felder mithilfe der Aspose.Words-Bibliothek für .NET aktualisieren. Indem Sie die bereitgestellten Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Durch die Aktualisierung fehlerhafter Felder beim Laden des Dokuments werden die neuesten Werte in Ihrem Word-Dokument angezeigt.
