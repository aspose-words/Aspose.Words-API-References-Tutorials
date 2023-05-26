---
title: Erhalten Sie Benachrichtigungen über Schriftarten
linktitle: Erhalten Sie Benachrichtigungen über Schriftarten
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie Benachrichtigungen über fehlende oder ersetzte Schriftarten erhalten, wenn Sie Aspose.Words für .NET verwenden.
type: docs
weight: 10
url: /de/net/working-with-fonts/receive-notifications-of-fonts/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie Schriftartenbenachrichtigungen erhalten, während Sie Aspose.Words für .NET verwenden. Mithilfe von Schriftartbenachrichtigungen können Sie fehlende oder ersetzte Schriftarten in Ihren Dokumenten erkennen und verwalten. Wir begleiten Sie Schritt für Schritt, um Ihnen zu helfen, den Code in Ihrem .NET-Projekt zu verstehen und zu implementieren.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über die folgenden Artikel verfügen:
- Grundkenntnisse der Programmiersprache C#
- Die in Ihrem Projekt installierte Aspose.Words-Bibliothek für .NET

## Schritt 1: Definieren Sie das Dokumentenverzeichnis
 Zuerst müssen Sie den Verzeichnispfad auf den Speicherort Ihres Word-Dokuments festlegen. Ersetzen`"YOUR DOCUMENT DIRECTORY"` im Code mit dem entsprechenden Pfad.

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und konfigurieren Sie die Schriftarteinstellungen
 Als nächstes laden wir das Dokument mit`Document` Klasse und konfigurieren Sie die Schriftarteinstellungen mithilfe der`FontSettings` Klasse. Wir werden die Standardschriftart festlegen, die verwendet werden soll, falls Schriftarten fehlen.

```csharp
//Laden Sie das Dokument und konfigurieren Sie die Schriftarteinstellungen
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Schritt 3: Benachrichtigungshandler festlegen
 Als Nächstes definieren wir einen Benachrichtigungshandler, indem wir den implementieren`IWarningCallback` Schnittstelle. Dadurch können wir beim Speichern des Dokuments Schriftartenwarnungen erfassen.

```csharp
// Definieren Sie den Benachrichtigungshandler
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Schritt 4: Schriftarteinstellungen anwenden und das Dokument speichern
Abschließend wenden wir die Schriftarteinstellungen auf das Dokument an und speichern es. Alle Schriftartwarnungen werden vom zuvor definierten Benachrichtigungshandler erfasst.

```csharp
// Übernehmen Sie die Schriftarteinstellungen und speichern Sie das Dokument
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Beispielquellcode für den Empfang von Benachrichtigungen über Schriftarten mit Aspose.Words für .NET 
```csharp

// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Wir können die Standardschriftart auswählen, die verwendet werden soll, falls Schriftarten fehlen.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// Zum Testen stellen wir Aspose.Words so ein, dass es nur in einem Ordner nach Schriftarten sucht, der nicht existiert. Da Aspose.Words dies nicht tut
// Suchen Sie alle Schriftarten im angegebenen Verzeichnis. Beim Rendern werden die Schriftarten im Dokument dann durch die Standardschriftarten ersetzt
//Schriftart, die unter FontSettings.DefaultFontName angegeben ist. Diesen Antrag können wir über unseren Rückruf aufgreifen.
fontSettings.SetFontsFolder(string.Empty, false);
// Erstellen Sie eine neue Klasse, die IWarningCallback implementiert und alle beim Speichern des Dokuments erzeugten Warnungen sammelt.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Abschluss
In diesem Tutorial haben wir gesehen, wie Sie Schriftartbenachrichtigungen erhalten, während Sie Aspose.Words für .NET verwenden. Mithilfe von Schriftartbenachrichtigungen können Sie fehlende oder ersetzte Schriftarten in Ihren Dokumenten erkennen und verwalten. Nutzen Sie diese Funktion, um die Schriftartenkonsistenz in Ihren Dokumenten sicherzustellen und bei fehlenden Schriftarten entsprechende Maßnahmen zu ergreifen.
