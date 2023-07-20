---
title: Legen Sie die MS Word-Version fest
linktitle: Legen Sie die MS Word-Version fest
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ein Dokument mit einer bestimmten Version von MS Word laden.
type: docs
weight: 10
url: /de/net/programming-with-loadoptions/set-ms-word-version/
---
Bei der Textverarbeitung mit Word-Dokumenten in einer C#-Anwendung kann es erforderlich sein, beim Laden des Dokuments die Version von Microsoft Word anzugeben, die verwendet werden soll. Mit der Aspose.Words-Bibliothek für .NET können Sie mithilfe von LoadOptions ganz einfach festlegen, welche Version von MS Word verwendet werden soll. In dieser Schritt-für-Schritt-Anleitung führen wir Sie durch die Verwendung von Aspose.Words für .NET C#-Quellcode zum Laden eines Dokuments mit einer bestimmten Version von MS Word mithilfe der LoadOptions-Ladeoptionen.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten, Konvertieren und Schützen von Word-Dokumenten auf verschiedenen Plattformen, einschließlich .NET. Es bietet viele Funktionen zum Bearbeiten von Dokumenten, wie zum Beispiel das Einfügen von Text, das Ändern von Formatierungen, das Hinzufügen von Abschnitten und vieles mehr.

## Ladeoptionen konfigurieren

Der erste Schritt besteht darin, die Ladeoptionen für unser Dokument zu konfigurieren. Verwenden Sie die LoadOptions-Klasse, um Ladeparameter anzugeben. In unserem Fall müssen wir die Eigenschaft MswVersion auf die gewünschte Version von MS Word setzen. Wir verwenden beispielsweise die Version Microsoft Word 2010. So geht's:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Wir erstellen ein neues LoadOptions-Objekt und setzen die MswVersion-Eigenschaft auf MsWordVersion.Word2010, um die Version von MS Word 2010 anzugeben.

## Laden von Dokumenten mit der angegebenen Version von MS Word

Nachdem wir nun die Ladeoptionen konfiguriert haben, können wir das Dokument mithilfe der Document-Klasse laden und die Ladeoptionen angeben. Hier ist ein Beispiel :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

In diesem Beispiel laden wir das Dokument „Document.docx“, das sich im Dokumentenverzeichnis befindet, mit den angegebenen Ladeoptionen.

### Beispielquellcode für LoadOptions mit der Funktionalität „MS Word-Version festlegen“ unter Verwendung von Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Konfigurieren Sie Ladeoptionen mit der Funktion „MS Word-Version festlegen“.
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Laden Sie das Dokument mit der angegebenen Version von MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Speichern Sie das Dokument
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Abschluss

In dieser Anleitung haben wir erklärt, wie Sie mithilfe der Aspose.Words-Bibliothek für .NET ein Dokument hochladen, das eine bestimmte Version von MS Word angibt. Indem Sie die bereitgestellten Schritte befolgen und die bereitgestellte Code-C#-Quelle verwenden, können Sie diese Funktionalität problemlos in Ihrer C#-Anwendung anwenden. Durch das Laden eines Dokuments mit einer bestimmten Version von MS Word können Sie die ordnungsgemäße Kompatibilität und Verarbeitung des Dokuments in Ihrer Anwendung sicherstellen.


### FAQs

#### F: Warum muss ich beim Laden eines Dokuments in eine C#-Anwendung die Version von MS Word angeben?

Durch die Angabe der MS Word-Version wird sichergestellt, dass das Dokument korrekt geladen und verarbeitet wird, insbesondere wenn es um bestimmte Formatierungen oder Funktionen geht, die zwischen verschiedenen Versionen variieren können.

#### F: Welche Versionen von MS Word unterstützt Aspose.Words?

A: Aspose.Words für .NET unterstützt verschiedene Versionen von MS Word, darunter Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 und mehr.

#### F: Kann ich ein Dokument mit einer anderen Version von MS Word laden als der, die auf meinem System installiert ist?

A: Ja, mit Aspose.Words können Sie beim Laden des Dokuments eine andere Version von MS Word angeben und so die Kompatibilität auch dann gewährleisten, wenn das Zielsystem über eine andere MS Word-Version verfügt.

#### F: Welchen Nutzen hat die Einstellung der MS Word-Version für meine C#-Anwendung?

A: Durch Festlegen der MS Word-Version wird sichergestellt, dass das Dokument gemäß der beabsichtigten Formatierung und den Funktionen dieser spezifischen Version verarbeitet wird und eine konsistente Ausgabe bereitgestellt wird.

#### F: Ist Aspose.Words auf die Verarbeitung nur von DOCX-Dokumenten beschränkt?

A: Nein, Aspose.Words unterstützt verschiedene Dokumentformate, darunter DOC, RTF, HTML, PDF und mehr, was es zu einem vielseitigen Tool für die Verarbeitung verschiedener Dokumenttypen macht.