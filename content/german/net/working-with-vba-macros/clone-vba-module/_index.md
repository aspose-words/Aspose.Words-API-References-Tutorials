---
title: VBA-Modul aus einem Word-Dokument klonen
linktitle: VBA-Modul aus einem Word-Dokument klonen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie in diesem Tutorial, wie Sie mit Aspose.Words für .NET ein VBA-Modul aus einem Word-Dokument klonen.
type: docs
weight: 10
url: /de/net/working-with-vba-macros/clone-vba-module/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET ein VBA-Modul aus einem Word-Dokument mit Makros klonen. Durch das Klonen eines VBA-Moduls können Sie VBA-Code aus einem Quelldokument in ein anderes Dokument wiederverwenden oder kopieren. Wir führen Sie Schritt für Schritt durch den Code und helfen Ihnen, ihn in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Elemente verfügen:
- Gute Kenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument mit einem VBA-Projekt mit dem Modul, das Sie klonen möchten

## Schritt 1: Dokumentverzeichnis festlegen
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments setzen. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Quelldokument laden
Als Nächstes laden wir das Quell-Word-Dokument, das das VBA-Projekt und das Modul enthält, das wir klonen möchten.

```csharp
// Laden des Quelldokuments
Document doc = new Document(dataDir + "VBA project.docm");
```

## Schritt 3: Erstellen Sie ein neues Dokument mit dem VBA-Projekt und klonen Sie das Modul
Wir erstellen ein neues Dokument mit einem leeren VBA-Projekt und klonen das angegebene Modul aus dem Quelldokument.

```csharp
// Erstellen Sie ein neues Dokument mit einem leeren VBA-Projekt
Document destDoc = new Document { VbaProject = new VbaProject() };

// Klonen Sie das Modul
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Schritt 4: Zieldokument speichern
Abschließend speichern wir das Zieldokument mit dem geklonten VBA-Modul in einer Datei.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Beispiel-Quellcode für das Klonen des VBA-Moduls mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET ein VBA-Modul aus einem Word-Dokument mit Makros klont. Durch das Klonen von VBA-Modulen können Sie VBA-Code aus einem Quelldokument problemlos in einem anderen Dokument wiederverwenden. Nutzen Sie diese Funktion, um Ihre Makros in verschiedenen Dokumenten zu organisieren und zu verwalten.

### Häufig gestellte Fragen

#### F: Was ist das Duplizieren eines VBA-Moduls?

A: Beim Duplizieren eines VBA-Moduls wird ein Modul mit VBA-Code aus einem Word-Quelldokument in ein anderes Dokument kopiert. So können Sie VBA-Code in verschiedenen Kontexten wiederverwenden oder mit anderen Dokumenten teilen.

#### F: Was sind die Voraussetzungen für das Klonen eines VBA-Moduls aus einem Word-Dokument?

A: Bevor Sie ein VBA-Modul aus einem Word-Dokument klonen können, müssen Sie über Kenntnisse der Programmiersprache C# verfügen. Sie müssen außerdem die Bibliothek Aspose.Words für .NET in Ihrem Projekt installieren. Außerdem benötigen Sie ein Word-Dokument, das ein VBA-Projekt mit dem Modul enthält, das Sie klonen möchten.

#### F: Wie lege ich das Dokumentverzeichnis im Code fest?

 A: Im bereitgestellten Code müssen Sie ersetzen`"YOUR DOCUMENTS DIRECTORY"` durch den entsprechenden Pfad zu dem Verzeichnis, in dem sich Ihr Word-Dokument mit dem VBA-Projekt befindet.

#### F: Wie speichere ich ein Zieldokument mit einem geklonten VBA-Modul?

 A: Um das Zieldokument mit dem geklonten VBA-Modul zu speichern, können Sie den`Save` Methode der`Document` Klasse, indem Sie den gewünschten Zielpfad und Dateinamen angeben.