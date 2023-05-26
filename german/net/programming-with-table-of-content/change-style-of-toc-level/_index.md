---
title: Ändern Sie den Stil der Toc-Ebene
linktitle: Ändern Sie den Stil der Toc-Ebene
second_title: Aspose.Words für .NET API-Referenz
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET ganz einfach den Stil einer Inhaltsverzeichnisebene in einem Word-Dokument ändern.
type: docs
weight: 10
url: /de/net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words für .NET ist eine leistungsstarke Bibliothek zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten in einer C#-Anwendung. Zu den von Aspose.Words angebotenen Funktionen gehört die Möglichkeit, den Stil einer bestimmten Ebene des Inhaltsverzeichnisses eines Dokuments zu ändern. In dieser Anleitung zeigen wir Ihnen, wie Sie den C#-Quellcode von Aspose.Words für .NET verwenden, um den Stil einer Ebene des Inhaltsverzeichnisses eines Word-Dokuments zu ändern.

## Grundlegendes zur Aspose.Words-Bibliothek

Bevor Sie in den Code eintauchen, ist es wichtig, die Aspose.Words-Bibliothek für .NET zu verstehen. Aspose.Words ist eine beliebte Bibliothek, die die Arbeit mit Word-Dokumenten einfach und effizient macht. Es bietet zahlreiche Funktionen zum Erstellen, Bearbeiten und Bearbeiten von Word-Dokumenten, einschließlich der Änderung des Inhaltsverzeichnisstils.

## Erstellen eines neuen Dokuments

Der erste Schritt besteht darin, ein neues Word-Dokument zu erstellen, dessen Inhaltsverzeichnisstil Sie ändern möchten. Verwenden Sie die Document-Klasse, um ein neues Dokument zu erstellen. Hier ist ein Beispiel :

```csharp
Document doc = new Document();
```

In diesem Beispiel erstellen wir ein neues leeres Dokument.

## Ändern des Stils einer Inhaltsverzeichnisebene

Sobald das Dokument erstellt wurde, können Sie auf Dokumentstile zugreifen und den Stil ändern, der für eine bestimmte Ebene des Inhaltsverzeichnisses verwendet wird. In diesem Beispiel ändern wir den Stil, der für die erste Ebene des Inhaltsverzeichnisses verwendet wird. Hier ist wie:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

In diesem Beispiel verwenden wir die Styles-Eigenschaft der Document-Klasse, um auf Dokumentstile zuzugreifen. Als Nächstes verwenden wir die Stilkennung StyleIdentifier.Toc1, um auf den Stil zuzugreifen, der für die erste Ebene des Inhaltsverzeichnisses verwendet wird. Schließlich ändern wir die Font.Bold-Eigenschaft des Stils, um ihn fett zu machen.

## Geändertes Dokument speichern

Nachdem Sie die erforderlichen Änderungen am Stil des Inhaltsverzeichnisses vorgenommen haben, können Sie das geänderte Dokument mit der Save-Methode der Document-Klasse speichern. Hier ist ein Beispiel :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

In diesem Beispiel speichern wir das geänderte Dokument als „WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx“.

## Beispielquellcode für die Funktion „Ändern des Stils einer Inhaltsverzeichnisebene“ mit Aspose.Words für .NET

```csharp
// Pfad zu Ihrem Dokumentenverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Erstellen Sie ein neues Dokument
Document doc = new Document();

// Änderung des Stils der ersten Ebene des Inhaltsverzeichnisses
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Speichern Sie das geänderte Dokument
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Abschluss

In diesem Handbuch haben wir erklärt, wie Sie Aspose.Words für .NET verwenden, um den Stil einer Ebene des Inhaltsverzeichnisses eines Word-Dokuments mithilfe des bereitgestellten C#-Quellcodes zu ändern. Indem Sie die bereitgestellten Schritte befolgen, können Sie den Stil des Inhaltsverzeichnisses in Ihren Word-Dokumenten in Ihrer C#-Anwendung ganz einfach anpassen. Aspose.Words bietet enorme Flexibilität und Möglichkeiten, mit den Stilen und Formatierungen Ihrer Dokumente zu arbeiten, sodass Sie attraktive und professionelle Word-Dokumente erstellen können.