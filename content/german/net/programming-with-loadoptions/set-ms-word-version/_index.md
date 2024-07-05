---
title: MS Word-Version festlegen
linktitle: MS Word-Version festlegen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument mit einer bestimmten Version von MS Word laden.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/set-ms-word-version/
---
Bei der Textverarbeitung mit Word-Dokumenten in einer C#-Anwendung kann es erforderlich sein, die Version von Microsoft Word anzugeben, die beim Laden des Dokuments verwendet werden soll. Mit der Aspose.Words-Bibliothek für .NET können Sie mithilfe von LoadOptions ganz einfach festlegen, welche Version von MS Word verwendet werden soll. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen Schritt für Schritt, wie Sie mit dem C#-Quellcode von Aspose.Words für .NET ein Dokument mit einer angegebenen Version von MS Word mithilfe der Ladeoptionen von LoadOptions laden.

## Die Aspose.Words-Bibliothek verstehen

Bevor Sie sich in den Code vertiefen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Sie bietet viele Funktionen zum Bearbeiten von Dokumenten, z. B. zum Einfügen von Text, Ändern der Formatierung, Hinzufügen von Abschnitten und vieles mehr.

## Konfigurieren der Ladeoptionen

Der erste Schritt besteht darin, die Ladeoptionen für unser Dokument zu konfigurieren. Verwenden Sie die Klasse LoadOptions, um Ladeparameter anzugeben. In unserem Fall müssen wir die Eigenschaft MswVersion auf die gewünschte Version von MS Word einstellen. Wir verwenden beispielsweise die Version von Microsoft Word 2010. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die MswVersion-Eigenschaft auf MsWordVersion.Word2010, um die Version von MS Word 2010 anzugeben.

## Dokument wird mit der angegebenen Version von MS Word geladen

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel:

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

In diesem Beispiel laden wir das im Dokumentenverzeichnis liegende Dokument „Document.docx“ mit den angegebenen Ladeoptionen.

### Beispielquellcode für LoadOptions mit der Funktion „MS Word-Version festlegen“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladeoptionen mit der Funktion „MS Word-Version festlegen“ konfigurieren
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Laden Sie das Dokument mit der angegebenen Version von MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Speichern des Dokuments
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET ein Dokument hochladen, das eine bestimmte Version von MS Word angibt. Indem Sie die angegebenen Schritte befolgen und den bereitgestellten C#-Quellcode verwenden, können Sie diese Funktion problemlos in Ihrer C#-Anwendung anwenden. Durch das Laden eines Dokuments mit einer angegebenen Version von MS Word können Sie die ordnungsgemäße Kompatibilität und Verarbeitung des Dokuments in Ihrer Anwendung sicherstellen.


### Häufig gestellte Fragen

#### F: Warum muss ich beim Laden eines Dokuments in einer C#-Anwendung die Version von MS Word angeben?

Durch die Angabe der MS Word-Version wird sichergestellt, dass das Dokument korrekt geladen und verarbeitet wird, insbesondere beim Umgang mit bestimmten Formatierungen oder Funktionen, die zwischen verschiedenen Versionen variieren können.

#### F: Welche Versionen von MS Word unterstützt Aspose.Words?

A: Aspose.Words für .NET unterstützt verschiedene Versionen von MS Word, darunter Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 und mehr.

#### F: Kann ich ein Dokument mit einer anderen Version von MS Word laden als der, die auf meinem System installiert ist?

A: Ja, Aspose.Words ermöglicht Ihnen, beim Laden des Dokuments eine andere Version von MS Word anzugeben. Dadurch wird die Kompatibilität sichergestellt, auch wenn das Zielsystem über eine andere MS Word-Version verfügt.

#### F: Welche Vorteile bietet das Festlegen der MS Word-Version für meine C#-Anwendung?

A: Durch das Festlegen der MS Word-Version wird sichergestellt, dass das Dokument entsprechend der beabsichtigten Formatierung und den Funktionen dieser bestimmten Version verarbeitet wird, wodurch eine konsistente Ausgabe gewährleistet wird.

#### F: Ist die Verarbeitung von Aspose.Words auf die Verarbeitung von DOCX-Dokumenten beschränkt?

A: Nein, Aspose.Words unterstützt verschiedene Dokumentformate, darunter DOC, RTF, HTML, PDF und mehr, und ist damit ein vielseitiges Tool für die Handhabung verschiedener Dokumenttypen.