---
title: Absatzstil im Word-Dokument anwenden
linktitle: Absatzstil im Word-Dokument anwenden
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET einen Absatzstil in einem Word-Dokument anwenden.
type: docs
weight: 10
url: /de/net/document-formatting/apply-paragraph-style/
---
In diesem Tutorial zeigen wir Ihnen, wie Sie mit Aspose.Words für .NET einen Absatzstil anwenden. Führen Sie die folgenden Schritte aus, um den Quellcode zu verstehen und den Absatzstil anzuwenden.

## Schritt 1: Dokument erstellen und konfigurieren

Erstellen Sie zunächst ein neues Dokument und ein zugehöriges DocumentBuilder-Objekt. Hier ist wie:

```csharp
// Pfad zum Dokumentenverzeichnis.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Schritt 2: Konfigurieren des Absatzstils

Wir konfigurieren nun den Absatzstil mithilfe der integrierten Stilkennung. Hier ist wie:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Schritt 3: Inhalte hinzufügen

Wir werden dem Absatz Inhalte hinzufügen. Hier ist wie:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Beispielquellcode für „Absatzstil anwenden“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Absatzstil anwenden“ mit Aspose.Words für .NET:

```csharp

	// Der Pfad zum Dokumentenverzeichnis.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Mit diesem Code können Sie mit Aspose.Words für .NET einen Absatzstil anwenden.

## Abschluss

 In diesem Tutorial haben wir untersucht, wie man mit Aspose.Words für .NET einen Absatzstil in einem Word-Dokument anwendet. Durch Einstellen der`StyleIdentifier` Eigentum der`ParagraphFormat`konnten wir einen integrierten Stil auf den Absatz anwenden. Aspose.Words für .NET bietet eine breite Palette an Formatierungsoptionen, einschließlich der Möglichkeit, benutzerdefinierte Stile zu erstellen und anzuwenden, sodass Sie problemlos professionell aussehende Dokumente erstellen können.

### FAQs

#### F: Wie wende ich mit Aspose.Words für .NET einen Absatzstil in einem Word-Dokument an?

A: Um einen Absatzstil in einem Word-Dokument mit Aspose.Words für .NET anzuwenden, führen Sie die folgenden Schritte aus:
1.  Erstellen Sie ein neues Dokument und a`DocumentBuilder` Objekt.
2.  Konfigurieren Sie den Absatzstil, indem Sie festlegen`StyleIdentifier` Eigentum der`ParagraphFormat` auf die gewünschte Stilkennung (z. B.`StyleIdentifier.Title`, `StyleIdentifier.Heading1`, usw.).
3.  Fügen Sie dem Absatz Inhalte hinzu, indem Sie verwenden`Write` Methode der`DocumentBuilder`.
4.  Speichern Sie das Dokument mit`Save` Methode.

#### F: Was sind Stilbezeichner in Aspose.Words für .NET?

 A: Stilbezeichner in Aspose.Words für .NET sind vordefinierte Konstanten, die integrierte Absatzstile darstellen. Jeder Stilbezeichner entspricht einem bestimmten Stil wie „Titel“, „Überschrift1“, „Überschrift2“ usw. Durch Festlegen von`StyleIdentifier` Eigentum der`ParagraphFormat`können Sie den entsprechenden Stil auf den Absatz anwenden.

#### F: Kann ich mit Aspose.Words für .NET benutzerdefinierte Absatzstile erstellen und anwenden?

A: Ja, mit Aspose.Words für .NET können Sie benutzerdefinierte Absatzstile erstellen und anwenden. Sie können Ihre eigenen Stile mit bestimmten Formatierungseigenschaften wie Schriftart, Ausrichtung, Einrückung usw. definieren und diese auf Absätze in Ihrem Dokument anwenden. Dadurch können Sie im gesamten Dokument eine konsistente und individuelle Formatierung erreichen.