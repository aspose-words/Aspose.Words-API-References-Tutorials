---
title: Manter caracteres de controle legados
linktitle: Manter caracteres de controle legados
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como preservar caracteres de controle herdados ao salvar um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Neste tutorial, exploraremos o código-fonte C# fornecido para preservar caracteres de controle legados ao salvar um documento usando Aspose.Words for .NET. Este recurso permite preservar caracteres de controle especiais ao converter ou salvar um documento.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.Words for .NET. Certifique-se de ter adicionado as referências necessárias e importado os namespaces apropriados.

## Passo 2: Carregando o documento

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Nesta etapa, carregamos o documento usando o`Document` método e passando o caminho para o arquivo que contém os caracteres de controle herdados.

## Etapa 3: configurar opções de backup OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 Nesta etapa, configuramos as opções de salvamento do OOXML criando um novo`OoxmlSaveOptions` objeto. Especificamos o formato de salvamento desejado (aqui,`FlatOpc` ) e ative o`KeepLegacyControlChars` opção para manter caracteres de controle legados.

## Etapa 4: Salvar o documento com caracteres de controle herdados

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Nesta última etapa, salvamos o documento usando o`Save` método e passando o caminho para o arquivo de saída com o`.docx` extensão, junto com as opções de salvamento especificadas.

Agora você pode executar o código-fonte para preservar os caracteres de controle herdados ao salvar um documento. O arquivo resultante será salvo no diretório especificado com o nome "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Exemplo de código-fonte para Keep Legacy Control Chars usando Aspose.Words for .NET 
```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusão

Neste tutorial, exploramos a funcionalidade de preservar caracteres de controle legados ao salvar um documento usando Aspose.Words for .NET. Aprendemos como preservar os caracteres especiais que podem ser importantes para a formatação ou exibição adequada do documento.

 Preservar caracteres de controle herdados é especialmente útil no processamento de texto com documentos que usam recursos mais antigos ou específicos, como caracteres de controle especiais. Ao ativar o`KeepLegacyControlChars` opção ao salvar o documento, você garante que esses caracteres sejam preservados.

Aspose.Words for .NET oferece uma variedade de opções de backup flexíveis e poderosas para atender às suas necessidades de manipulação de documentos. Ao usar as opções apropriadas, você pode personalizar o processo de backup para preservar as características específicas dos seus documentos.

Sinta-se à vontade para incorporar essa funcionalidade em seus projetos Aspose.Words for .NET para garantir a integridade e preservação dos caracteres de controle legados em seus documentos.