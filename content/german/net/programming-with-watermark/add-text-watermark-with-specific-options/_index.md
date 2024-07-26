---
title: Textwasserzeichen mit bestimmten Optionen hinzufügen
linktitle: Textwasserzeichen mit bestimmten Optionen hinzufügen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Textwasserzeichen mit bestimmten Optionen hinzufügen. Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET ein Textwasserzeichen mit bestimmten Optionen hinzufügen. Ein Textwasserzeichen ist Text, der einem Dokument überlagert wird, um anzuzeigen, dass es sich um einen Entwurf, vertraulich usw. handelt.

## Schritt 1: Einen Dokumentgenerator verwenden

Zuerst verwenden wir einen Dokumentgenerator, um unserem Dokument Inhalt hinzuzufügen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Dokument einlegen

Wir laden ein vorhandenes Dokument über den Dokumentpfad.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Schritt 3: Textwasserzeichen mit bestimmten Optionen hinzufügen

 Wir erstellen eine Instanz des`TextWatermarkOptions` Klasse und legen Sie die gewünschten Optionen für das Textwasserzeichen fest.

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

Abschließend können wir das Dokument mit dem hinzugefügten Textwasserzeichen speichern.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Beispielquellcode zum Hinzufügen eines Textwasserzeichens mit bestimmten Optionen mit Aspose.Words für .NET

```csharp

	// Der Pfad zum Dokumentverzeichnis.
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

