---
title: Zugriff auf Lesezeichen im Word-Dokument
linktitle: Zugriff auf Lesezeichen im Word-Dokument
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET auf Lesezeichen in einem Word-Dokument zugreifen.
type: docs
weight: 10
url: /de/net/programming-with-bookmarks/access-bookmarks/
---

In diesem Artikel werden wir den obigen C#-Quellcode untersuchen, um zu verstehen, wie die Access-Lesezeichenfunktion in der Aspose.Words-Bibliothek für .NET verwendet wird. Diese Funktion bietet Zugriff auf bestimmte Lesezeichen in einem Word-Dokument.

## Voraussetzungen

- Grundkenntnisse der Sprache C#.
- .NET-Entwicklungsumgebung mit installierter Aspose.Words-Bibliothek.

## Schritt 1: Dokument einlegen

 Bevor wir auf Lesezeichen zugreifen können, müssen wir ein Word-Dokument mit Aspose.Words für .NET laden. Dies kann durch die Instanziierung eines`Document` Objekt, das den Dokumentdateipfad angibt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Schritt 2: Zugriff auf Lesezeichen

Sobald das Dokument geladen ist, können wir auf die Lesezeichen im Dokument zugreifen. Es gibt zwei Möglichkeiten, auf Lesezeichen zuzugreifen: über den Index und über den Namen.

- Zugriff per Index: In unserem Beispiel verwenden wir den Index 0, um auf das erste Lesezeichen des Dokuments zuzugreifen:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Zugriff über den Namen: In unserem Beispiel verwenden wir den Namen „MyBookmark3“, um auf ein bestimmtes Lesezeichen im Dokument zuzugreifen:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Beispielquellcode für Access-Lesezeichen mit Aspose.Words für .NET

Hier ist der vollständige Beispielquellcode zur Demonstration des Zugriffs auf Lesezeichen mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Nach Index:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Namentlich:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Abschluss

In diesem Artikel haben wir den C#-Quellcode untersucht, um zu verstehen, wie die Access Bookmarks-Funktion von Aspose.Words für .NET verwendet wird. Wir sind einer Schritt-für-Schritt-Anleitung gefolgt, um ein Dokument hochzuladen und über Index und Name auf Lesezeichen zuzugreifen.

### FAQs zum Zugriff auf Lesezeichen in Word-Dokumenten

#### F: Wie kann ich mit Aspose.Words für .NET ein Word-Dokument hochladen?

 A: Um ein Word-Dokument mit Aspose.Words für .NET zu laden, können Sie eine`Document`Objekt, indem Sie den Dateipfad des Dokuments angeben. Hier ist ein Beispielcode:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

#### F: Wie kann ich auf Lesezeichen in einem Word-Dokument zugreifen?

 A: Sie können auf Lesezeichen in einem Word-Dokument zugreifen, indem Sie`Bookmarks` Eigentum der`Range` Objekt. Sie können auf Lesezeichen nach Index oder nach Namen zugreifen. Hier ist ein Beispielcode:

- Zugriff per Index:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Zugriff über den Namen:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

#### F: Welche Bibliothek wird benötigt, um die Lesezeichenzugriffsfunktion in Aspose.Words für .NET zu verwenden?

A: Um die Lesezeichenzugriffsfunktion in Aspose.Words für .NET zu verwenden, benötigen Sie die Aspose.Words-Bibliothek. Stellen Sie sicher, dass diese Bibliothek in Ihrer .NET-Entwicklungsumgebung installiert ist.

#### F: Gibt es andere Möglichkeiten, auf Lesezeichen in einem Word-Dokument zuzugreifen?

 A: Ja, zusätzlich zum Zugriff auf Lesezeichen nach Index oder Name können Sie auch alle Lesezeichen im Dokument mithilfe einer Schleife durchlaufen. Sie können die Gesamtzahl der Lesezeichen im Dokument mithilfe der`Count` Eigentum der`Bookmarks` Sammlung. Anschließend können Sie über den Index auf jedes Lesezeichen zugreifen. Hier ist ein Beispielcode:

```csharp
int bookmarkCount = doc.Range.Bookmarks.Count;

for (int i = 0; i < bookmarkCount; i++)
{
     Bookmark bookmark = doc.Range.Bookmarks[i];
     // Machen Sie etwas mit dem Lesezeichen...
}
```