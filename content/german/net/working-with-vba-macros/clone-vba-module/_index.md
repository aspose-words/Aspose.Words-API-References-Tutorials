---
title: Klonen Sie ein VBA-Modul aus einem Word-Dokument
linktitle: Klonen Sie ein VBA-Modul aus einem Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Words für .NET ein VBA-Modul aus einem Word-Dokument klonen.
type: docs
weight: 10
url: /de/net/working-with-vba-macros/clone-vba-module/
---

In diesem Tutorial erklären wir Ihnen, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET ein VBA-Modul aus einem Word-Dokument mit Makros klonen. Durch das Klonen eines VBA-Moduls können Sie VBA-Code von einem Quelldokument wiederverwenden oder in ein anderes Dokument kopieren. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET
- Ein Word-Dokument, das ein VBA-Projekt mit dem Modul enthält, das Sie klonen möchten

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Quelldokument laden
Als Nächstes laden wir das Word-Quelldokument, das das VBA-Projekt und das Modul enthält, das wir klonen möchten.

```csharp
// Laden Sie das Quelldokument
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

## Schritt 4: Speichern Sie das Zieldokument
Abschließend speichern wir das Zieldokument mit dem geklonten VBA-Modul in einer Datei.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Beispielquellcode für Clone Vba Module mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie man mit Aspose.Words für .NET ein VBA-Modul aus einem Word-Dokument mit Makros klont. Durch das Klonen von VBA-Modulen können Sie VBA-Code aus einem Quelldokument problemlos in einem anderen Dokument wiederverwenden. Nutzen Sie diese Funktion gerne zum Organisieren und Verwalten Ihrer Makros in verschiedenen Dokumenten.

### FAQs

#### F: Was ist das Duplizieren eines VBA-Moduls?

A: Beim Duplizieren eines VBA-Moduls wird ein Modul, das VBA-Code enthält, aus einem Word-Quelldokument in ein anderes Dokument kopiert. Dadurch können Sie VBA-Code in verschiedenen Kontexten wiederverwenden oder mit anderen Dokumenten teilen.

#### F: Was sind die Voraussetzungen für das Klonen eines VBA-Moduls aus einem Word-Dokument?

A: Bevor Sie ein VBA-Modul aus einem Word-Dokument klonen können, müssen Sie über praktische Kenntnisse der Programmiersprache C# verfügen. Sie müssen außerdem die Aspose.Words for .NET-Bibliothek in Ihrem Projekt installieren. Außerdem benötigen Sie ein Word-Dokument, das ein VBA-Projekt mit dem Modul enthält, das Sie klonen möchten.

#### F: Wie lege ich das Dokumentverzeichnis im Code fest?

 A: Im bereitgestellten Code müssen Sie ersetzen.`"YOUR DOCUMENTS DIRECTORY"` mit dem entsprechenden Pfad zu dem Verzeichnis, in dem sich Ihr Word-Dokument mit dem VBA-Projekt befindet.

#### F: Wie speichere ich ein Zieldokument mit einem geklonten VBA-Modul?

 A: Um das Zieldokument mit dem geklonten VBA-Modul zu speichern, können Sie das verwenden`Save` Methode der`Document` Klasse durch Angabe des gewünschten Zielpfads und Dateinamens.