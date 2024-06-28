---
title: Horizontales Regelformat im Word-Dokument
linktitle: Horizontales Regelformat im Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET anpassbare horizontale Regeln in Word-Dokumente einfügen. Verbessern Sie Ihre Dokumentenautomatisierung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## Einführung

Im Bereich der .NET-Entwicklung kann die programmgesteuerte Bearbeitung und Formatierung von Word-Dokumenten eine entmutigende Aufgabe sein. Glücklicherweise bietet Aspose.Words für .NET eine robuste Lösung, mit der Entwickler die Erstellung, Bearbeitung und Verwaltung von Dokumenten problemlos automatisieren können. Dieser Artikel befasst sich mit einer der wesentlichen Funktionen: dem Einfügen horizontaler Regeln in Word-Dokumente. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst mit Aspose.Words beginnen, wird die Beherrschung dieser Funktion Ihren Dokumentenerstellungsprozess verbessern.

## Voraussetzungen

Bevor Sie mit der Implementierung horizontaler Regeln mit Aspose.Words für .NET beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Visual Studio: Installieren Sie die Visual Studio-IDE für die .NET-Entwicklung.
- Aspose.Words für .NET: Laden Sie Aspose.Words für .NET herunter und installieren Sie es von[Hier](https://releases.aspose.com/words/net/).
- Grundlegende C#-Kenntnisse: Vertrautheit mit den Grundlagen der Programmiersprache C#.
-  DocumentBuilder-Klasse: Verständnis der`DocumentBuilder` Klasse in Aspose.Words zur Dokumentbearbeitung.

## Namespaces importieren

Importieren Sie zunächst die erforderlichen Namespaces in Ihr C#-Projekt:

```csharp
using Aspose.Words;
using System.Drawing;
```

Diese Namespaces bieten Zugriff auf Aspose.Words-Klassen zur Dokumentbearbeitung und Standard-.NET-Klassen zur Verarbeitung von Farben.

Lassen Sie uns den Prozess des Hinzufügens einer horizontalen Linie in einem Word-Dokument mithilfe von Aspose.Words für .NET in umfassende Schritte unterteilen:

## Schritt 1: DocumentBuilder initialisieren und Verzeichnis festlegen

 Initialisieren Sie zunächst a`DocumentBuilder` Objekt und legen Sie den Verzeichnispfad fest, in dem das Dokument gespeichert wird.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## Schritt 2: Horizontales Lineal einfügen

 Benutzen Sie die`InsertHorizontalRule()` Methode der`DocumentBuilder` Klasse, um eine horizontale Regel hinzuzufügen.

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## Schritt 3: Passen Sie das horizontale Regelformat an

 Greife auf ... zu`HorizontalRuleFormat` Eigenschaft der eingefügten Form, um das Erscheinungsbild der horizontalen Linie anzupassen.

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- Ausrichtung: Gibt die Ausrichtung der horizontalen Linie an (`HorizontalRuleAlignment.Center` in diesem Beispiel).
- Breitenprozent: Legt die Breite der horizontalen Linie als Prozentsatz der Seitenbreite fest (70 % in diesem Beispiel).
- Höhe: Definiert die Höhe der horizontalen Linie in Punkten (in diesem Beispiel 3 Punkte).
- Farbe: Legt die Farbe der horizontalen Linie fest (`Color.Blue` in diesem Beispiel).
- NoShade: Gibt an, ob die horizontale Linie einen Schatten haben soll (`true` in diesem Beispiel).

## Schritt 4: Dokument speichern

 Speichern Sie abschließend das geänderte Dokument mit`Save` Methode der`Document` Objekt.

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## Abschluss

Wenn Sie das Einfügen horizontaler Regeln in Word-Dokumente mit Aspose.Words für .NET beherrschen, verbessern Sie Ihre Möglichkeiten zur Dokumentautomatisierung. Durch die Nutzung der Flexibilität und Leistungsfähigkeit von Aspose.Words können Entwickler Prozesse zur Dokumentenerstellung und -formatierung effizient optimieren.

## FAQs

### Was ist Aspose.Words für .NET?
Aspose.Words für .NET ist eine leistungsstarke Bibliothek für die programmgesteuerte Arbeit mit Word-Dokumenten in .NET-Anwendungen.

### Wie kann ich Aspose.Words für .NET herunterladen?
 Sie können Aspose.Words für .NET herunterladen von[Hier](https://releases.aspose.com/words/net/).

### Kann ich das Erscheinungsbild horizontaler Regeln in Aspose.Words anpassen?
Ja, Sie können mit Aspose.Words verschiedene Aspekte wie Ausrichtung, Breite, Höhe, Farbe und Schattierung horizontaler Linien anpassen.

### Ist Aspose.Words für die Dokumentenverarbeitung auf Unternehmensebene geeignet?
Ja, Aspose.Words wird aufgrund seiner robusten Funktionen zur Dokumentenbearbeitung häufig in Unternehmensumgebungen verwendet.

### Wo erhalte ich Unterstützung für Aspose.Words für .NET?
 Für Unterstützung und gemeinschaftliches Engagement besuchen Sie die[Aspose.Words-Forum](https://forum.aspose.com/c/words/8).
