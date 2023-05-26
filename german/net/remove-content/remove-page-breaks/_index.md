---
title: Seitenumbrüche entfernen
linktitle: Seitenumbrüche entfernen
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Seitenumbrüche in einem Dokument mithilfe der Aspose.Words-Bibliothek für .NET entfernen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung für ein nahtloses Layout.
type: docs
weight: 10
url: /de/net/remove-content/remove-page-breaks/
---
In diesem Tutorial erfahren Sie, wie Sie mithilfe der Bibliothek Aspose.Words für .NET Seitenumbrüche aus einem Dokument entfernen. Seitenumbrüche können manchmal die Formatierung und das Layout eines Dokuments beeinträchtigen und müssen möglicherweise programmgesteuert entfernt werden. Wir stellen Ihnen eine Schritt-für-Schritt-Anleitung zur Verfügung, die Ihnen hilft, den Prozess zu verstehen und ihn in Ihren eigenen C#-Projekten zu implementieren.

## Anforderungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Programmiersprache C#
- Aspose.Words für .NET-Bibliothek installiert
- Visual Studio oder eine andere C#-Entwicklungsumgebung eingerichtet

## Schritt 1: Einrichten der Umgebung

Erstellen Sie zunächst ein neues C#-Projekt in Ihrer bevorzugten Entwicklungsumgebung. Stellen Sie sicher, dass in Ihrem Projekt ordnungsgemäß auf die Aspose.Words for .NET-Bibliothek verwiesen wird.

## Schritt 2: Laden des Dokuments

Um Seitenumbrüche aus einem Dokument zu entfernen, müssen wir das Dokument zunächst in den Speicher laden. Der folgende Code zeigt, wie ein Dokument aus einem bestimmten Verzeichnis geladen wird:

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Laden Sie das Dokument
Document doc = new Document(dataDir + "your-document.docx");
```

 Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu Ihrem Dokument.

## Schritt 3: Seitenumbrüche entfernen

Sobald das Dokument geladen ist, können wir mit dem Entfernen der Seitenumbrüche beginnen. Der folgende Codeausschnitt zeigt, wie Sie alle Absätze im Dokument durchlaufen, auf Seitenumbrüche prüfen und diese entfernen:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
     // Wenn der Absatz zuvor einen Seitenumbruch hat, löschen Sie ihn
     if (para.ParagraphFormat.PageBreakBefore)
         para.ParagraphFormat.PageBreakBefore = false;

     // Überprüfen Sie alle Läufe im Absatz auf Seitenumbrüche und entfernen Sie diese
     foreach(Run run in para.Runs)
     {
         if (run.Text.Contains(ControlChar.PageBreak))
             run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
     }
}
```

Der obige Codeausschnitt durchläuft alle Absätze im Dokument und prüft, ob vor jedem Absatz ein Seitenumbruch steht. Wenn ein Seitenumbruch erkannt wird, wird dieser gelöscht. Anschließend prüft es jede Zeile innerhalb des Absatzes auf Seitenumbrüche und entfernt diese.

## Schritt 4: Speichern des geänderten Dokuments

Nachdem wir die Seitenumbrüche entfernt haben, müssen wir das geänderte Dokument speichern. Der folgende Code zeigt, wie das geänderte Dokument an einem bestimmten Speicherort gespeichert wird:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 Ersetzen`"modified-document.docx"` mit dem gewünschten Namen für Ihr geändertes Dokument.

### Beispielquellcode zum Entfernen von Seitenumbrüchen mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//Laden Sie das Dokument
Document doc = new Document(dataDir + "your-document.docx");

NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
	// Wenn der Absatz vor dem Satz einen Seitenumbruch hat, löschen Sie ihn.
	if (para.ParagraphFormat.PageBreakBefore)
		para.ParagraphFormat.PageBreakBefore = false;

	//Überprüfen Sie alle Läufe im Absatz auf Seitenumbrüche und entfernen Sie diese.
	foreach (Run run in para.Runs)
	{
		if (run.Text.Contains(ControlChar.PageBreak))
			run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
	}
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);        

```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mithilfe der Aspose.Words for .NET-Bibliothek Seitenumbrüche aus einem Dokument entfernt. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, sollten Sie nun in der Lage sein, diese Funktionalität in Ihren eigenen C#-Projekten zu implementieren. Das Entfernen von Seitenumbrüchen kann Ihnen helfen, ein einheitliches Layout und eine einheitliche Formatierung in Ihren Dokumenten beizubehalten.
