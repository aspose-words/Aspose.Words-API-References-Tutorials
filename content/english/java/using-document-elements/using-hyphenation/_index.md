---
title: Using Hyphenation in Aspose.Words for Java
linktitle: Using Hyphenation in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 17
url: /java/using-document-elements/using-hyphenation/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "German text.docx");
        Hyphenation.registerDictionary("en-US", getMyDir() + "hyph_en_US.dic");
        Hyphenation.registerDictionary("de-CH", getMyDir() + "hyph_de_CH.dic");
        doc.save(getArtifactsDir() + "WorkingWithHyphenation.HyphenateWordsOfLanguages.pdf");
    }
    @Test
    public void loadHyphenationDictionaryForLanguage() throws Exception
    {
        Document doc = new Document(getMyDir() + "German text.docx");
        FileInputStream stream = new FileInputStream(getMyDir() + "hyph_de_CH.dic");
        Hyphenation.registerDictionary("de-CH", stream);
        doc.save(getArtifactsDir() + "WorkingWithHyphenation.LoadHyphenationDictionaryForLanguage.pdf");
    }
    @Test 
    public void hyphenationCallback() throws Exception
    {
        try
        {
            // Register hyphenation callback.
            Hyphenation.setCallback(new CustomHyphenationCallback());
            Document document = new Document(getMyDir() + "German text.docx");
            document.save(getArtifactsDir() + "WorkingWithHyphenation.HyphenationCallback.pdf");
        }
        catch (Exception e)
        {
            if (e.getMessage().startsWith("Missing hyphenation dictionary")) {
            System.out.println(e.getMessage());
        }
        }
        finally
        {
            Hyphenation.setCallback(null);
        }
    }
    public static class CustomHyphenationCallback implements IHyphenationCallback
    {
        public void requestDictionary(String language) throws Exception
        {
            String dictionaryFolder = getMyDir();
            String dictionaryFullFileName;
            switch (language)
            {
                case "en-US":
                    dictionaryFullFileName = Paths.get(dictionaryFolder, "hyph_en_US.dic").toString();
                    break;
                case "de-CH":
                    dictionaryFullFileName = Paths.get(dictionaryFolder, "hyph_de_CH.dic").toString();
                    break;
                default:
                    throw new Exception(MessageFormat.format("Missing hyphenation dictionary for {0}.", language));
            }
            // Register dictionary for requested language.
            Hyphenation.registerDictionary(language, dictionaryFullFileName);
        }
```
