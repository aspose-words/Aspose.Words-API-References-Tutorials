---
title: Nach Abschnitten
linktitle: Nach Abschnitten
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie anhand eines vollständigen Codebeispiels, wie Sie mit Aspose.Words für .NET ein Word-Dokument in separate Abschnitte aufteilen.
type: docs
weight: 10
url: /de/net/split-document/by-sections/
---

In diesem Beispiel zeigen wir Ihnen, wie Sie ein Word-Dokument mithilfe der Funktion „Nach Abschnitten“ von Aspose.Words für .NET in separate Abschnitte unterteilen. Befolgen Sie die nachstehenden Schritte, um den Quellcode zu verstehen und separate Dokumente für jeden Abschnitt zu erhalten.

## Schritt 1: Laden des Dokuments

Zunächst müssen wir das Verzeichnis Ihres Dokuments angeben und das Dokument in ein Document-Objekt laden. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Schritt 2: Teilen Sie das Dokument in Abschnitte

Jetzt werden wir jeden Abschnitt des Dokuments durchlaufen und das Dokument Abschnitt für Abschnitt in kleinere Teile aufteilen. So geht's:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Teilen Sie das Dokument in kleinere Teile auf, in diesem Fall in Abschnitte.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Speichern Sie jeden Abschnitt als separates Dokument.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Beispielquellcode für By Sections mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Nach Abschnitten“ von Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	for (int i = 0; i < doc.Sections.Count; i++)
	{
		// Teilen Sie ein Dokument in kleinere Teile auf, in diesem Fall nach Abschnitten.
		Section section = doc.Sections[i].Clone();

		Document newDoc = new Document();
		newDoc.Sections.Clear();

		Section newSection = (Section) newDoc.ImportNode(section, true);
		newDoc.Sections.Add(newSection);

		// Speichern Sie jeden Abschnitt als separates Dokument.
		newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
	}

```

Mit diesem Code können Sie ein Word-Dokument mit Aspose.Words für .NET in separate Abschnitte aufteilen.

Jetzt können Sie ganz einfach mit bestimmten Abschnitten arbeiten.

