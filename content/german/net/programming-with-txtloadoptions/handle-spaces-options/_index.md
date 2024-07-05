---
title: Optionen für Handle-Leerzeichen
linktitle: Optionen für Handle-Leerzeichen
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Leerzeichen in Ihren TXT-Dokumenten verwalten. Entfernen Sie unnötige Leerzeichen und verbessern Sie die Lesbarkeit.
type: docs
weight: 10
url: /de/net/programming-with-txtloadoptions/handle-spaces-options/
---

In diesem Tutorial werden wir den C#-Quellcode untersuchen, der für die Funktion „Verwalten von Leerzeichen mit TXT-Ladeoptionen“ mit Aspose.Words für .NET bereitgestellt wird. Mit dieser Funktion können Sie das Verhalten bei der Behandlung von Leerzeichen beim Laden eines TXT-Dokuments festlegen.

## Schritt 1: Einrichten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass Sie Ihre Entwicklungsumgebung mit Aspose.Words für .NET eingerichtet haben. Stellen Sie sicher, dass Sie die erforderlichen Referenzen hinzugefügt und die entsprechenden Namespaces importiert haben.

## Schritt 2: Erstellen des Textdokuments

```csharp
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

In diesem Schritt erstellen wir eine Textzeichenfolge, die ein Textdokument simuliert, das Zeilen mit führenden und nachfolgenden Leerzeichen enthält.

## Schritt 3: Upload-Optionen konfigurieren

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

 In diesem Schritt konfigurieren wir die Optionen zum Laden des TXT-Dokuments. Wir erstellen ein neues`TxtLoadOptions` Objekt und setzen Sie den`LeadingSpacesOptions` Und`TrailingSpacesOptions` Eigenschaften zu`TxtLeadingSpacesOptions.Trim` Und`TxtTrailingSpacesOptions.Trim` Dies weist Aspose.Words an, beim Laden des Dokuments führende und nachfolgende Leerzeichen aus den Zeilen zu entfernen.

## Schritt 4: Dokument einlegen

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

 In diesem Schritt laden wir das Dokument mit dem`Document` Methode und Übergabe des Speicherstroms, der die angegebene Textzeichenfolge und die Ladeoptionen enthält.

## Schritt 5: Speichern Sie das Dokument

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

 In diesem letzten Schritt speichern wir das resultierende Dokument im .docx-Format mit dem`Save` Methode und Übergabe des Pfads an die Ausgabedatei.

Jetzt können Sie den Quellcode ausführen, um das Textdokument zu laden, indem Sie Optionen zur Behandlung von Leerzeichen angeben. Das resultierende Dokument wird im angegebenen Verzeichnis unter dem Namen „WorkingWithTxtLoadOptions.HandleSpacesOptions.docx“ gespeichert.

### Beispiel-Quellcode für die Speicherverwaltungsfunktion mit TXT-Ladeoptionen mit Aspose.Words für .NET*

```csharp

            
// Pfad zu Ihrem Dokumentverzeichnis
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## Abschluss

In diesem Tutorial haben wir die Funktionalität zum Verwalten von Leerzeichen mit TXT-Ladeoptionen in Aspose.Words für .NET untersucht. Wir haben gelernt, wie man das Verhalten bei der Behandlung von Leerzeichen beim Laden eines TXT-Dokuments angibt.

Diese Funktion ist sehr nützlich, um unnötige Leerzeichen links und rechts von Zeilen in einem Dokument zu beseitigen. Durch die Konfiguration der entsprechenden Ladeoptionen können Sie diese unerwünschten Leerzeichen problemlos entfernen, wodurch der Dokumentinhalt übersichtlicher und lesbarer wird.

Aspose.Words für .NET bietet viele erweiterte Funktionen zur Dokumentbearbeitung und -erstellung. Die Verwaltung von Leerzeichen beim Laden eines TXT-Dokuments ist eines der vielen leistungsstarken Tools, die Ihnen zur Verfügung stehen.

 Es ist wichtig, die Speicherverwaltungsoptionen auszuwählen, die am besten zu Ihrem spezifischen Szenario passen. In diesem Beispiel haben wir die`Trim`Optionen zum Entfernen unnötiger Leerzeichen am Zeilenanfang und -ende. Aspose.Words bietet jedoch auch andere Optionen zum Beibehalten, vollständigen Entfernen oder Beibehalten von Leerzeichen.

Vergessen Sie nicht, diese Optionen an Ihre spezifischen Anforderungen und die Struktur Ihrer TXT-Dokumente anzupassen.

Mit Aspose.Words für .NET können Sie Leerzeichen in Ihren Dokumenten einfach bearbeiten und so die Layoutqualität und Lesbarkeit des Inhalts verbessern.

Zögern Sie also nicht, die Leerzeichenverwaltung mit TXT-Ladeoptionen in Ihre Aspose.Words für .NET-Projekte zu integrieren und nutzen Sie die Vorteile, um gut formatierte und leicht lesbare Dokumente zu erstellen.