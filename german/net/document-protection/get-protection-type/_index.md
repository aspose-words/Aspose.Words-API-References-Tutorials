---
title: Holen Sie sich den Schutztyp in ein Word-Dokument
linktitle: Holen Sie sich den Schutztyp in ein Word-Dokument
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie die Funktion „Schutztyp in Word-Dokument abrufen“ von Aspose.Words für .NET verwenden, um den Schutztyp eines Dokuments zu ermitteln.
type: docs
weight: 10
url: /de/net/document-protection/get-protection-type/
---
Willkommen zu dieser Schritt-für-Schritt-Anleitung, die den C#-Quellcode für die Funktion „Get Protection Type“ von Aspose.Words für .NET erklärt. In diesem Artikel zeigen wir Ihnen, wie Sie diese leistungsstarke Funktion verwenden, um den Schutztyp eines Dokuments zu bestimmen. Der Dokumentenschutz ist unerlässlich, um die Vertraulichkeit und Integrität Ihrer Dateien zu gewährleisten. Wir führen Sie durch die Schritte, die zur Integration von Aspose.Words für .NET und zur Verwendung der Funktion „Schutztyp abrufen“ erforderlich sind.

## Schritt 1: Laden des Dokuments

Der erste Schritt zur Verwendung der Funktion „Schutztyp abrufen“ besteht darin, das Dokument hochzuladen, an dem Sie arbeiten möchten. Sie können dies mit der von Aspose.Words für .NET bereitgestellten Document-Klasse tun. Hier ist ein Beispielcode zum Laden eines Dokuments aus einer Datei:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

Stellen Sie sicher, dass Sie den korrekten Pfad zu Ihrer Dokumentdatei angeben.

## Schritt 2: Abrufen des Schutztyps

Nachdem das Dokument hochgeladen wurde, können Sie die ProtectionType-Eigenschaft des Document-Objekts verwenden, um den auf das Dokument angewendeten Schutztyp abzurufen. So können Sie es machen:

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### Beispielquellcode für „Get Protection Type“ mit Aspose.Words für .NET

Hier ist der vollständige Quellcode für die Funktion „Get Protection Type“ mit Aspose.Words für .NET:

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## Abschluss

In diesem Artikel haben wir erklärt, wie Sie die Funktion „Get Protection Type“ von Aspose.Words für .NET verwenden, um den Schutztyp eines Dokuments zu bestimmen. Wenn Sie die beschriebenen Schritte befolgen, können Sie diese Funktionalität problemlos in Ihre eigenen C#-Projekte integrieren und geschützte Dokumente effizient bearbeiten. Aspose.Words für .NET bietet große Flexibilität

### FAQs

#### F: Was ist die ProtectionType-Eigenschaft in Aspose.Words für .NET?

 A: Die`ProtectionType` -Eigenschaft in Aspose.Words für .NET ist eine Funktion, mit der Sie die Art des auf ein Word-Dokument angewendeten Schutzes bestimmen können. Es liefert Informationen über den Grad des Dokumentschutzes, z. B. ob das Dokument für Kommentare, Überarbeitungen, Formulare oder andere Arten von Einschränkungen geschützt ist.

#### F: Wie kann ich mit Aspose.Words für .NET den Schutztyp eines Dokuments abrufen?

A: Um den Schutztyp eines Dokuments mit Aspose.Words für .NET abzurufen, können Sie die folgenden Schritte ausführen:
1.  Laden Sie das Dokument mit`Document` Klasse.
2.  Greife auf ... zu`ProtectionType`Eigentum der`Document` Objekt zum Abrufen des Schutztyps.

#### F: Kann ich mithilfe der ProtectionType-Eigenschaft feststellen, ob ein Dokument für Formulare oder Formularfelder geschützt ist?

 A: Ja, Sie können mithilfe von feststellen, ob ein Dokument für Formulare oder Formularfelder geschützt ist`ProtectionType` Eigenschaft in Aspose.Words für .NET. Wenn der Schutztyp auf eingestellt ist`AllowOnlyFormFields`, zeigt es an, dass das Dokument geschützt ist und nur Formularfelder bearbeitet werden können.

#### F: Welche anderen Schutztypen kann die ProtectionType-Eigenschaft zurückgeben?

 A: Die`ProtectionType` Die Eigenschaft in Aspose.Words für .NET kann verschiedene Schutztypen zurückgeben, darunter:
- `NoProtection`: Das Dokument ist nicht geschützt.
- `AllowOnlyRevisions`: Das Dokument ist geschützt und es können nur Änderungen vorgenommen werden.
- `AllowOnlyComments`: Das Dokument ist geschützt und es können nur Kommentare hinzugefügt werden.
- `AllowOnlyFormFields`: Das Dokument ist geschützt und nur Formularfelder können bearbeitet werden.
- `ReadOnly`: Das Dokument ist geschützt und schreibgeschützt.

#### F: Kann ich den Schutztyp eines Dokuments mithilfe der ProtectionType-Eigenschaft ändern?

 A: Nein, das`ProtectionType`Die Eigenschaft in Aspose.Words für .NET ist eine schreibgeschützte Eigenschaft. Es ermöglicht Ihnen, den aktuellen Schutztyp eines Dokuments abzurufen, bietet jedoch keine direkte Möglichkeit, den Schutztyp zu ändern. Um den Schutztyp zu ändern, müssen Sie andere Methoden und Eigenschaften verwenden, die im verfügbar sind`Document` Klasse, wie z`Protect` oder`Unprotect`.

#### F: Ist es möglich, ein Dokument mit mehreren Schutztypen gleichzeitig zu schützen?

A: Nein, mit Aspose.Words für .NET kann jeweils nur ein Schutztyp auf ein Dokument angewendet werden. Sie können jedoch verschiedene Schutztypen kombinieren, indem Sie den Schutz aktivieren, einen Typ festlegen, den Schutz deaktivieren und ihn dann mit einem anderen Typ erneut aktivieren.

