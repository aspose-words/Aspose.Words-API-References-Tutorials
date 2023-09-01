---
title: Greifen Sie auf Lesezeichen im Word-Dokument zu
linktitle: Greifen Sie auf Lesezeichen im Word-Dokument zu
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET auf Lesezeichen in einem Word-Dokument zugreifen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/access-bookmarks/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Funktion „Zugriff auf Lesezeichen“ in der Bibliothek „Aspose.Words für .NET“ verwendet wird. Diese Funktion ermöglicht den Zugriff auf bestimmte Lesezeichen in einem Word-Dokument.

## Voraussetzungen

- Grundkenntnisse der C#-Sprache.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Laden des Dokuments

 Bevor wir auf Lesezeichen zugreifen können, müssen wir ein Word-Dokument mit Aspose.Words für .NET laden. Dies kann durch Instanziieren von a erfolgen`Document` Objekt, das den Pfad der Dokumentdatei angibt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Schritt 2: Zugriff auf Lesezeichen

Sobald das Dokument geladen ist, können wir auf die Lesezeichen im Dokument zugreifen. Es gibt zwei Möglichkeiten, auf Lesezeichen zuzugreifen: über den Index und über den Namen.

- Zugriff per Index: In unserem Beispiel verwenden wir Index 0, um auf das erste Lesezeichen des Dokuments zuzugreifen:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Zugriff über Namen: In unserem Beispiel verwenden wir den Namen „MyBookmark3“, um auf ein bestimmtes Lesezeichen im Dokument zuzugreifen:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Beispielquellcode für Access Bookmarks mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode, um den Zugriff auf Lesezeichen mit Aspose.Words für .NET zu demonstrieren:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Nach Index:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Namentlich:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Access Bookmarks-Funktion von Aspose.Words für .NET verwendet wird. Wir folgten einer Schritt-für-Schritt-Anleitung zum Hochladen eines Dokuments und zum Zugriff auf Lesezeichen mithilfe von Index und Name.

### FAQs zum Zugriff auf Lesezeichen in Word-Dokumenten

#### F: Wie kann ich ein Word-Dokument mit Aspose.Words für .NET hochladen?

 A: Um ein Word-Dokument mit Aspose.Words für .NET zu laden, können Sie ein instanziieren`Document`Objekt durch Angabe des Dateipfads des Dokuments. Hier ist ein Beispielcode:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

#### F: Wie kann ich auf Lesezeichen in einem Word-Dokument zugreifen?

 A: Sie können mit auf Lesezeichen in einem Word-Dokument zugreifen`Bookmarks` Eigentum der`Range` Objekt. Sie können auf Lesezeichen nach Index oder Namen zugreifen. Hier ist ein Beispielcode:

- Zugriff per Index:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Zugriff mit Namen:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

#### F: Welche Bibliothek ist erforderlich, um die Lesezeichenzugriffsfunktion in Aspose.Words für .NET zu verwenden?

A: Um die Lesezeichenzugriffsfunktion in Aspose.Words für .NET nutzen zu können, benötigen Sie die Aspose.Words-Bibliothek. Stellen Sie sicher, dass diese Bibliothek in Ihrer .NET-Entwicklungsumgebung installiert ist.

#### F: Gibt es andere Möglichkeiten, auf Lesezeichen in einem Word-Dokument zuzugreifen?

 A: Ja, zusätzlich zum Zugriff auf Lesezeichen nach Index oder Name können Sie mithilfe einer Schleife auch alle Lesezeichen im Dokument durchlaufen. Sie können die Gesamtzahl der Lesezeichen im Dokument mithilfe von ermitteln`Count` Eigentum der`Bookmarks` Sammlung. Anschließend können Sie über den Index auf jedes Lesezeichen zugreifen. Hier ist ein Beispielcode:

```csharp
int bookmarkCount = doc.Range.Bookmarks.Count;

for (int i = 0; i < bookmarkCount; i++)
{
     Bookmark bookmark = doc.Range.Bookmarks[i];
     // Machen Sie etwas mit dem Lesezeichen ...
}
```