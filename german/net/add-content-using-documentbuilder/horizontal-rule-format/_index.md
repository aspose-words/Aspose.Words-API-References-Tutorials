---
title: Horizontales Regelformat
linktitle: Horizontales Regelformat
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET horizontale Regeln in Word-Dokumenten formatieren. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/horizontal-rule-format/
---

In diesem umfassenden Beispiel erfahren Sie, wie Sie mit Aspose.Words für .NET eine horizontale Linie in einem Word-Dokument formatieren. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieser Anleitung werden Sie in der Lage sein, die Ausrichtung, Breite, Höhe, Farbe und andere Eigenschaften eines horizontalen Lineals anzupassen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie einen DocumentBuilder und fügen Sie eine horizontale Regel ein
Erstellen Sie zunächst ein DocumentBuilder-Objekt und fügen Sie mit der Methode „InsertHorizontalRule“ eine horizontale Regel ein:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Schritt 2: Greifen Sie auf das horizontale Regelformat zu
Greifen Sie als Nächstes auf die Eigenschaft „HorizontalRuleFormat“ des Shape-Objekts zu, um die Formatierungsoptionen abzurufen:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Schritt 3: Passen Sie die Formatierungsoptionen an
Jetzt können Sie verschiedene Formatierungsoptionen für die horizontale Linie anpassen. Sie können beispielsweise Ausrichtung, Breite, Höhe, Farbe und Schattierung anpassen:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Schritt 4: Speichern Sie das Dokument
Speichern Sie das Dokument nach dem Formatieren der horizontalen Linie mit der Save-Methode des Document-Objekts in einer Datei:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Beispielquellcode für das horizontale Regelformat mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Formatieren einer horizontalen Regel mit Aspose.Words für .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Denken Sie daran, den Code an Ihre spezifischen Anforderungen anzupassen und ihn bei Bedarf um zusätzliche Funktionen zu erweitern.

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET eine horizontale Linie in einem Word-Dokument formatieren. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie jetzt das Erscheinungsbild horizontaler Linien anpassen, um das visuelle Layout Ihres Dokuments zu verbessern.

Experimentieren Sie mit verschiedenen Formatierungsoptionen, um den gewünschten Stil und Effekt für Ihre horizontalen Linien zu erzielen.
