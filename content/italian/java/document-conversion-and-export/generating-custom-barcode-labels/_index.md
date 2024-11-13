---
title: Generazione di etichette di codici a barre personalizzate in Aspose.Words per Java
linktitle: Generazione di etichette con codice a barre personalizzate
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Genera etichette di codici a barre personalizzate in Aspose.Words per Java. Scopri come creare soluzioni di codici a barre personalizzate utilizzando Aspose.Words per Java in questa guida passo passo.
type: docs
weight: 10
url: /it/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Introduzione alla generazione di etichette di codici a barre personalizzate in Aspose.Words per Java

In questa guida completa, approfondiremo il processo di generazione di etichette di codici a barre personalizzate utilizzando Aspose.Words per Java. Aspose.Words per Java è una potente API che consente agli sviluppatori di manipolare i documenti Word a livello di programmazione. Una delle sue caratteristiche notevoli è la capacità di lavorare con etichette di codici a barre, rendendolo uno strumento prezioso per aziende e organizzazioni che richiedono soluzioni di codici a barre personalizzate.

## Prerequisiti

Prima di addentrarci nei dettagli della generazione di etichette con codice a barre personalizzate, assicuriamoci di disporre dei prerequisiti:

1. Ambiente di sviluppo Java: assicurati di avere Java e un ambiente di sviluppo integrato (IDE) installati sul tuo sistema.

2.  Aspose.Words per Java: Scarica e installa Aspose.Words per Java da[Qui](https://releases.aspose.com/words/java/).

3. Conoscenza di base di Java: la familiarità con la programmazione Java sarà utile poiché scriveremo codice Java per creare etichette con codici a barre personalizzate.

## Creazione di etichette con codice a barre personalizzate

Ora, iniziamo a creare etichette personalizzate con codice a barre usando Aspose.Words per Java. Suddivideremo il processo in passaggi e forniremo frammenti di codice Java per ogni passaggio.

## Impostazione dell'altezza del codice a barre

Per iniziare, dobbiamo impostare l'altezza del nostro codice a barre in twip (1/1440 pollici). Convertiremo quindi questo valore in millimetri (mm). Ecco il codice per ottenere questo risultato:

```java
	// Il valore di input è in 1/1440 pollici (twip)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Convertire in mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Conversione del colore dell'immagine del codice a barre

Successivamente, convertiremo il colore dell'immagine del codice a barre da Word ad Aspose.BarCode. Il colore di input dovrebbe essere nel formato "0xRRGGBB" (esadecimale). Ecco il codice per la conversione:

```java
/// <sommario>
/// Converte il colore dell'immagine del codice a barre da Word ad Aspose.BarCode.
/// </sommario>
/// <param name="inputColor"></param>
/// <ritorna></ritorna>
private static Color convertColor(String inputColor) throws Exception {
	// L'input dovrebbe essere compreso tra "0x000000" e "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Conversione del fattore di scala del codice a barre

Ora, convertiremo il fattore di scala del codice a barre da una percentuale a un valore float. Questo fattore di scala determina la dimensione del codice a barre. Ecco il codice per la conversione:

```java
/// <sommario>
/// Converte il fattore di scala del codice a barre da percentuale a float.
/// </sommario>
/// <param name="fattorediscala"></param>
/// <ritorna></ritorna>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## Implementazione del metodo GetBarCodeImage()

 In questa fase implementeremo il`getBarcodeImage`metodo, che genera l'immagine del codice a barre in base ai parametri forniti. Gestiremo diversi tipi di codice a barre, imposteremo i colori, regoleremo le dimensioni e altro ancora. Ecco il codice per questo metodo:

```java
/// <sommario>
/// Implementazione del metodo GetBarCodeImage() per l'interfaccia IBarCodeGenerator.
/// </sommario>
/// <param name="parametri"></param>
/// <ritorna></ritorna>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Controllare se sono forniti il tipo e il valore del codice a barre
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Crea un BarcodeGenerator in base al tipo di codice a barre
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Gestisci altri tipi di codici a barre qui
	}
	
	// Imposta il testo del codice a barre
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Imposta i colori del codice a barre
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Imposta l'altezza e le dimensioni del simbolo
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Personalizza la posizione del testo del codice
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Ulteriori modifiche per i codici QR
	final float SCALE = 2.4f; // Fattore di scala empirico per convertire il codice a barre di Word in Aspose.BarCode
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// Applica fattore di scala
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Genera e restituisci l'immagine del codice a barre
	return generator.generateBarCodeImage();
}
```

## Implementazione del metodo GetOldBarcodeImage()

 In questa fase implementeremo il`getOldBarcodeImage`metodo, che genera immagini di codici a barre per i vecchi codici a barre. Qui, gestiremo un tipo di codice a barre specifico, come POSTNET. Ecco il codice per questo metodo:

```java
/// <sommario>
/// Implementazione del metodo GetOldBarcodeImage() per l'interfaccia IBarCodeGenerator.
/// </sommario>
/// <param name="parametri"></param>
/// <ritorna></ritorna>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Tipo di codice rigido per il vecchio codice a barre
	return generator.generateBarCodeImage();
}
```

## Conclusione

In questo articolo, abbiamo esplorato il processo di generazione di etichette di codici a barre personalizzate utilizzando Aspose.Words per Java. Abbiamo trattato i passaggi essenziali, dall'impostazione dell'altezza del codice a barre all'implementazione di metodi per la generazione di codici a barre. Aspose.Words per Java consente agli sviluppatori di creare etichette di codici a barre dinamiche e personalizzate, rendendolo uno strumento prezioso per vari settori.

## Domande frequenti

### Come posso modificare la dimensione del codice a barre generato?

È possibile regolare la dimensione del codice a barre generato impostando l'altezza del simbolo del codice a barre e il fattore di scala nei frammenti di codice forniti. Questi parametri consentono di controllare le dimensioni del codice a barre in base alle proprie esigenze.

### Posso cambiare i colori del codice a barre?

Sì, puoi cambiare i colori del codice a barre specificando i colori di primo piano e di sfondo nel codice. Questa personalizzazione ti consente di adattare l'aspetto del codice a barre al design del tuo documento.

### Quali tipi di codici a barre sono supportati da Aspose.Words per Java?

Aspose.Words per Java supporta vari tipi di codici a barre, tra cui codici QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 e altri. Puoi scegliere il tipo di codice a barre più adatto alle esigenze della tua applicazione.

### Come posso integrare il codice a barre generato nel mio documento Word?

Per integrare il codice a barre generato nel tuo documento Word, puoi usare le capacità di manipolazione dei documenti di Aspose.Words for Java. Puoi inserire l'immagine del codice a barre nel tuo documento nella posizione desiderata.

### È disponibile un codice di esempio per ulteriori personalizzazioni?

 Sì, puoi trovare frammenti di codice di esempio e documentazione aggiuntiva sul sito di riferimento di Aspose.Words per Java:[Riferimento API Aspose.Words per Java](https://reference.aspose.com/words/java/).