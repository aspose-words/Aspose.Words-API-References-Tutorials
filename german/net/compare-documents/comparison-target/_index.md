---
title: Vergleichsziel
linktitle: Vergleichsziel
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Lernen Sie die Zielvergleichsfunktion von Aspose.Words für .NET kennen, mit der Sie Dokumente vergleichen und ein neues Dokument mit den vorgenommenen Änderungen erstellen können.
type: docs
weight: 10
url: /de/net/compare-documents/comparison-target/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der die Vergleichszielfunktionalität von Aspose.Words für .NET nutzt.

## Schritt 1: Einführung

Mit der Zielvergleichsfunktion von Aspose.Words für .NET können Sie zwei Dokumente vergleichen und ein neues Dokument erstellen, das die am Zieldokument vorgenommenen Änderungen enthält. Dies kann nützlich sein, um Änderungen zu verfolgen, die zwischen verschiedenen Versionen eines Dokuments vorgenommen wurden.

## Schritt 2: Einrichten der Umgebung

Bevor Sie beginnen, müssen Sie Ihre Entwicklungsumgebung für die Arbeit mit Aspose.Words für .NET einrichten. Stellen Sie sicher, dass Sie die Aspose.Words-Bibliothek installiert haben und über ein geeignetes C#-Projekt zum Einbetten des Codes verfügen.

## Schritt 3: Erforderliche Baugruppen hinzufügen

Um die Vergleichszielfunktion von Aspose.Words für .NET nutzen zu können, müssen Sie Ihrem Projekt die erforderlichen Assemblys hinzufügen. Stellen Sie sicher, dass Ihr Projekt über die richtigen Verweise auf Aspose.Words verfügt.

```csharp
using Aspose.Words;
```

## Schritt 4: Dokumentinitialisierung

In diesem Schritt initialisieren wir zwei Dokumente zum Vergleich. Sie müssen den Verzeichnispfad angeben, in dem sich Ihre Dokumente befinden, sowie den Namen des Quelldokuments.

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Initialisierung des zu vergleichenden Dokuments A.
Document docA = new Document(dataDir + "DocumentA.docx");

// Klonen Sie Dokument A, um eine identische Kopie von Dokument B zu erstellen.
Document docB = docA.Clone();
```

## Schritt 5: Vergleichsoptionen konfigurieren

In diesem Schritt konfigurieren wir die Vergleichsoptionen, um das Verhalten des Vergleichs festzulegen. Zu den Optionen gehören die Möglichkeit, Formatierungen zu ignorieren, sowie das Vergleichsziel, bei dem es sich um die Option „Änderungen anzeigen in“ im Dialogfeld „Dokumente vergleichen“ von Microsoft Word handelt.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Schritt 6: Dokumentenvergleich

Jetzt vergleichen wir die Dokumente und generieren das Ergebnis in einem neuen Dokument.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 Der`Compare` Die Methode vergleicht Dokument A mit Dokument B und speichert die Änderungen an Dokument A. Sie können den Benutzernamen und das Datum des Vergleichs als Referenz angeben.

### Beispielquellcode für Compare Target mit Aspose.Words für .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Bezieht sich auf die Microsoft Word-Option „Änderungen anzeigen in“ im Dialogfeld „Dokumente vergleichen“.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Abschluss

In diesem Artikel haben wir die Diff-Zielfunktion von Aspose.Words für .NET untersucht. Mit dieser Funktion können Sie zwei Dokumente vergleichen und ein neues Dokument erstellen, das die vorgenommenen Änderungen enthält. Mit diesem Wissen können Sie Änderungen zwischen verschiedenen Versionen Ihrer Dokumente nachverfolgen.

