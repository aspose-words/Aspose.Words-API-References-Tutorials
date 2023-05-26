---
title: Absatzknoten erstellen und hinzufügen
linktitle: Absatzknoten erstellen und hinzufügen
second_title: Aspose.Words für .NET API-Referenz
description: Erstellen Sie mit Aspose.Words für .NET einen Absatzknoten und fügen Sie ihn zu Ihren Word-Dokumenten hinzu.
type: docs
weight: 10
url: /de/net/working-with-node/create-and-add-paragraph-node/
---

Hier finden Sie eine Schritt-für-Schritt-Anleitung zur Erläuterung des folgenden C#-Quellcodes, der veranschaulicht, wie Sie mit Aspose.Words für .NET einen Absatzknoten erstellen und hinzufügen.

## Schritt 1: Importieren Sie die erforderlichen Referenzen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die erforderlichen Referenzen zur Verwendung von Aspose.Words für .NET in Ihr Projekt importiert haben. Dazu gehört das Importieren der Aspose.Words-Bibliothek und das Hinzufügen der erforderlichen Namespaces zu Ihrer Quelldatei.

```csharp
using Aspose.Words;
```

## Schritt 2: Erstellen Sie ein neues Dokument
 In diesem Schritt erstellen wir ein neues Dokument mit`Document` Klasse.

```csharp
Document doc = new Document();
```

## Schritt 3: Erstellen Sie einen Absatzknoten
 Jetzt erstellen wir einen Absatzknoten mit`Paragraph` Klasse und Übergabe des Dokuments als Parameter.

```csharp
Paragraph para = new Paragraph(doc);
```

## Schritt 4: Greifen Sie auf den Dokumentbereich zu
 Um den Absatz zum Dokument hinzuzufügen, müssen wir mit auf den letzten Abschnitt des Dokuments zugreifen`LastSection` Eigentum.

```csharp
Section section = doc.LastSection;
```

## Schritt 5: Fügen Sie den Absatzknoten zum Dokument hinzu
 Nachdem wir nun den Dokumentabschnitt haben, können wir den Absatzknoten mithilfe von zum Abschnitt hinzufügen`AppendChild` Methode auf dem Abschnitt`Body` Eigentum.

```csharp
section.Body.AppendChild(para);
```

## Schritt 6: Speichern Sie das Dokument
 Zum Speichern des Dokuments können Sie schließlich die Datei verwenden`Save` Methode durch Angabe des gewünschten Ausgabeformats, z. B. DOCX-Format.

```csharp
doc.Save("output.docx", SaveFormat.Docx);
```

### Beispielquellcode zum Erstellen und Hinzufügen eines Absatzknotens mit Aspose.Words für .NET

```csharp
Document doc = new Document();

Paragraph para = new Paragraph(doc);

Section section = doc.LastSection;
section.Body.AppendChild(para);

```

Dies ist ein vollständiges Codebeispiel zum Erstellen und Hinzufügen eines Absatzknotens mit Aspose.Words für .NET. Stellen Sie sicher, dass Sie die erforderlichen Referenzen importieren und die zuvor beschriebenen Schritte befolgen, um diesen Code in Ihr Projekt zu integrieren.