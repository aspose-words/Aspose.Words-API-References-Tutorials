---
title: Horizontale Regel einfügen
linktitle: Horizontale Regel einfügen
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET horizontale Regeln in Word-Dokumente einfügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

In diesem umfassenden Beispiel erfahren Sie, wie Sie mit Aspose.Words für .NET eine horizontale Linie in ein Word-Dokument einfügen. Wir führen Sie durch den Prozess und stellen Ihnen die notwendigen C#-Code-Snippets zur Verfügung. Am Ende dieses Leitfadens werden Sie in der Lage sein, Ihren Dokumenten horizontale Regeln zur visuellen Trennung und Organisation hinzuzufügen.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Aspose.Words für .NET-Bibliothek auf Ihrem System installiert.

## Schritt 1: Erstellen Sie ein neues Dokument und einen neuen DocumentBuilder
Erstellen Sie zunächst ein neues Dokument mit der Document-Klasse und initialisieren Sie ein DocumentBuilder-Objekt:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Fügen Sie eine horizontale Regel ein
Als nächstes verwenden Sie die Writeln-Methode der DocumentBuilder-Klasse, um einen beschreibenden Text hinzuzufügen und anschließend eine horizontale Regel einzufügen:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Schritt 3: Speichern Sie das Dokument
Speichern Sie das Dokument nach dem Einfügen der horizontalen Linie mit der Save-Methode der Document-Klasse in einer Datei:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Beispielquellcode für „Horizontale Regel einfügen“ mit Aspose.Words für .NET
Hier ist der vollständige Quellcode zum Einfügen einer horizontalen Regel mit Aspose.Words für .NET:
Horizontale Regeln sind für verschiedene Szenarien nützlich, z. B. zum Unterteilen von Abschnitten, zum Erstellen visueller Unterbrechungen oder zum Hervorheben wichtiger Informationen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Denken Sie daran, den Code an Ihre spezifischen Anforderungen anzupassen und ihn bei Bedarf um zusätzliche Funktionen zu erweitern.

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aspose.Words für .NET eine horizontale Linie in ein Word-Dokument einfügen. Indem Sie der Schritt-für-Schritt-Anleitung folgen und den bereitgestellten Quellcode verwenden, können Sie Ihre Dokumente jetzt mithilfe horizontaler Regeln visuell trennen und organisieren.

