---
title: Salvando documentos como formato OOXML no Aspose.Words para Java
linktitle: Salvando documentos como formato OOXML
second_title: API de processamento de documentos Java Aspose.Words
description: Aprenda a salvar documentos no formato OOXML com Aspose.Words para Java. Proteja, otimize e personalize seus arquivos sem esforço.
type: docs
weight: 20
url: /pt/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## Introdução ao salvamento de documentos como formato OOXML no Aspose.Words para Java

Neste guia, exploraremos como salvar documentos no formato OOXML usando o Aspose.Words para Java. OOXML (Office Open XML) é um formato de arquivo usado pelo Microsoft Word e outros aplicativos de escritório. Abordaremos várias opções e configurações para salvar documentos no formato OOXML.

## Pré-requisitos

Antes de começar, certifique-se de ter a biblioteca Aspose.Words para Java configurada em seu projeto.

## Salvando um documento com criptografia de senha

Você pode criptografar seu documento com uma senha enquanto o salva no formato OOXML. Veja como você pode fazer isso:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Carregue o documento
Document doc = new Document("Document.docx");

// Crie OoxmlSaveOptions e defina a senha
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// Salvar o documento com criptografia
doc.save("EncryptedDoc.docx", saveOptions);
```

## Configurando a conformidade com OOXML

Você pode especificar o nível de conformidade do OOXML ao salvar o documento. Por exemplo, você pode defini-lo como ISO 29500:2008 (Strict). Veja como:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// Carregue o documento
Document doc = new Document("Document.docx");

// Otimizar para Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// Crie OoxmlSaveOptions e defina o nível de conformidade
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// Salvar o documento com a configuração de conformidade
doc.save("ComplianceDoc.docx", saveOptions);
```

## Atualizando a última propriedade de tempo salva

Você pode escolher atualizar a propriedade "Último horário salvo" do documento ao salvá-lo. Veja como:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// Carregue o documento
Document doc = new Document("Document.docx");

// Crie OoxmlSaveOptions e habilite a atualização da propriedade Last Saved Time
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// Salve o documento com a propriedade atualizada
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## Mantendo personagens de controle legados

Se o seu documento contiver caracteres de controle legados, você pode escolher mantê-los ao salvar. Veja como:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

//Carregar um documento com caracteres de controle legados
Document doc = new Document("LegacyControlChars.doc");

// Crie OoxmlSaveOptions com o formato FLAT_OPC e habilite a manutenção de caracteres de controle legados
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setKeepLegacyControlChars(true);

// Salve o documento com caracteres de controle legados
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## Definindo o nível de compressão

Você pode ajustar o nível de compressão ao salvar o documento. Por exemplo, você pode defini-lo como SUPER_FAST para compressão mínima. Veja como:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// Carregue o documento
Document doc = new Document("Document.docx");

// Crie OoxmlSaveOptions e defina o nível de compressão
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// Salve o documento com o nível de compactação especificado
doc.save("FastCompressionDoc.docx", saveOptions);
```

Estas são algumas das principais opções e configurações que você pode usar ao salvar documentos no formato OOXML usando o Aspose.Words para Java. Sinta-se à vontade para explorar mais opções e personalizar seu processo de salvamento de documentos conforme necessário.

## Código fonte completo para salvar documentos como formato OOXML em Aspose.Words para Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## Conclusão

Neste guia abrangente, exploramos como salvar documentos no formato OOXML usando o Aspose.Words para Java. Se você precisa criptografar seus documentos com senhas, garantir a conformidade com padrões OOXML específicos, atualizar propriedades do documento, preservar caracteres de controle legados ou ajustar níveis de compactação, o Aspose.Words fornece um conjunto versátil de ferramentas para atender às suas necessidades.

## Perguntas frequentes

### Como faço para remover a proteção por senha de um documento protegido por senha?

Para remover a proteção por senha de um documento protegido por senha, você pode abrir o documento com a senha correta e salvá-lo sem especificar uma senha nas opções de salvamento. Isso salvará o documento sem proteção por senha.

### Posso definir propriedades personalizadas ao salvar um documento no formato OOXML?

 Sim, você pode definir propriedades personalizadas para um documento antes de salvá-lo no formato OOXML. Use o`BuiltInDocumentProperties` e`CustomDocumentProperties` classes para definir várias propriedades, como autor, título, palavras-chave e propriedades personalizadas.

### Qual é o nível de compactação padrão ao salvar um documento no formato OOXML?

 O nível de compressão padrão ao salvar um documento no formato OOXML usando Aspose.Words para Java é`NORMAL` . Você pode alterar o nível de compressão para`SUPER_FAST` ou`MAXIMUM` conforme necessário.