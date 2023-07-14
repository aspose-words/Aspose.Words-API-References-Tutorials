---
title: Uppdatera sidlayout
linktitle: Uppdatera sidlayout
second_title: Aspose.Words Document Processing API
description: Lär dig hur du uppdaterar sidlayouten när du går med i och lägger till Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/update-page-layout/
---

Denna handledning guidar dig genom processen att använda funktionen Uppdatera sidlayout i Aspose.Words för .NET. Den här funktionen säkerställer att sidlayouten uppdateras korrekt när du ansluter och lägger till Word-dokument.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.Words för .NET installerat. Du kan ladda ner den från Asposes webbplats eller installera den via NuGet.
2. Visual Studio eller någon annan C#-utvecklingsmiljö.

## Steg 1: Initiera dokumentkatalogerna

 Först måste du ställa in sökvägen till din dokumentkatalog. Ändra värdet på`dataDir`variabel till sökvägen där dina dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll- och måldokumenten

 Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words`Document` klass. Uppdatera filnamnen i`Document` konstruktor enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Steg 3: Uppdatera sidlayout för destinationsdokumentet

 För att säkerställa att sidlayouten uppdateras korrekt innan du lägger till källdokumentet kan du anropa`UpdatePageLayout` metod på måldokumentet.

```csharp
dstDoc.UpdatePageLayout();
```

## Steg 4: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.KeepSourceFormatting` parametern säkerställer att källformateringen bevaras under tilläggsåtgärden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Steg 5: Uppdatera sidlayout igen

 När du har lagt till källdokumentet måste du ringa till`UpdatePageLayout` metod på måldokumentet igen för att säkerställa att eventuella ändringar som görs efter tilläggsåtgärden återspeglas i den renderade utdata.

```csharp
dstDoc.UpdatePageLayout();
```

## Steg 6: Spara det slutliga dokumentet

 Slutligen, spara det sammanslagna dokumentet med funktionen Uppdatera sidlayout aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Exempel på källkod för Update Page Layout med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen "Uppdatera sidlayout" i C# med Aspose.Words för .NET:

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Om måldokumentet renderas till PDF, bild etc.
	// eller UpdatePageLayout anropas före källdokumentet. Bifogas,
	// då kommer alla ändringar som görs efter inte att återspeglas i den renderade utdata
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// För att ändringarna ska uppdateras till renderad utdata måste UpdatePageLayout anropas igen.
	// Om det inte anropas igen, kommer det bifogade dokumentet inte att visas i utgången av nästa rendering.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Update Page Layout med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med sidlayouten korrekt uppdaterad.