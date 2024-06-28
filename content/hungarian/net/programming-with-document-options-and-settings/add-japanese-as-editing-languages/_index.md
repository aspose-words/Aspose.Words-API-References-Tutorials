---
title: Japán hozzáadása szerkesztési nyelvként
linktitle: Japán hozzáadása szerkesztési nyelvként
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre a japán nyelv szerkesztési nyelvként való hozzáadásához az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

Ebben az oktatóanyagban lépésről lépésre elvezetjük Önt ahhoz, hogy megértse és megvalósítsa a japán nyelv szerkesztési nyelvként való hozzáadásának funkcióját az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a nyelvi beállítások megadását dokumentum betöltésekor, és a japán nyelv hozzáadását szerkesztési nyelvként.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum betöltése

Ebben a lépésben betöltjük azt a Word dokumentumot, amely nem tartalmaz alapértelmezett szerkesztési nyelvet, és amelyhez a japán nyelvet szeretnénk hozzáadni. A dokumentum betöltéséhez használja a következő kódot:

```csharp
LoadOptions loadOptions = new LoadOptions();

// Állítsa be a dokumentum betöltésekor használt nyelvi beállításokat.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## 3. lépés: Az alapértelmezett nyelv ellenőrzése

A dokumentum betöltése után ellenőrizzük, hogy az alapértelmezett szerkesztési nyelv helyesen lett-e beállítva japánra. A távol-keleti nyelvi azonosító beszerzéséhez használja a következő kódot:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

kód ellenőrzi, hogy a távol-keleti nyelv azonosítója megegyezik-e a japán nyelvével. Az eredménynek megfelelően egy megfelelő üzenetet jelenít meg.

### Példa forráskód a Japán hozzáadása szerkesztési nyelvként funkcióhoz az Aspose.Words for .NET használatával

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Állítsa be a dokumentum betöltésekor használt nyelvi beállításokat.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

