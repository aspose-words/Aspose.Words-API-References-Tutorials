---
title: Fügen Sie Textwasserzeichen mit spezifischen Optionen hinzu
linktitle: Fügen Sie Textwasserzeichen mit spezifischen Optionen hinzu
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Textwasserzeichen mit bestimmten Optionen hinzufügen. Schritt für Schritt Anleitung.
type: docs
weight: 10
url: /de/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Textwasserzeichen mit bestimmten Optionen hinzufügen. Ein Textwasserzeichen ist Text, der einem Dokument überlagert wird, um anzuzeigen, dass es sich um einen Entwurf, vertraulich usw. handelt.

## Schritt 1: Verwendung eines Dokumentengenerators

Zuerst verwenden wir einen Dokumentgenerator, um Inhalte zu unserem Dokument hinzuzufügen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden des Dokuments

Wir laden ein vorhandenes Dokument über den Dokumentpfad.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Schritt 3: Fügen Sie ein Textwasserzeichen mit bestimmten Optionen hinzu

 Wir werden eine Instanz davon erstellen`TextWatermarkOptions` Klasse und legen Sie die gewünschten Optionen für das Textwasserzeichen fest.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Schritt 4: Speichern Sie das Dokument

Schließlich können wir das Dokument mit dem hinzugefügten Textwasserzeichen speichern.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Beispielquellcode zum Hinzufügen von Textwasserzeichen mit spezifischen Optionen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Herzlichen Glückwunsch! Sie haben jetzt gelernt, wie Sie mit Aspose.Words für .NET Textwasserzeichen mit bestimmten Optionen hinzufügen.

