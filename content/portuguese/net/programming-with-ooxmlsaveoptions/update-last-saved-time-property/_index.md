---
title: Atualizar propriedade do último horário salvo
linktitle: Atualizar propriedade do último horário salvo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como atualizar automaticamente a propriedade Last Saved Time ao salvar um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
Neste tutorial, exploraremos o código-fonte C# fornecido para atualizar a propriedade last save time ao salvar um documento usando Aspose.Words for .NET. Este recurso permite atualizar automaticamente a propriedade do último horário de salvamento do documento gerado.

## Passo 1: Configurando o ambiente

Antes de começar, certifique-se de configurar seu ambiente de desenvolvimento com Aspose.Words for .NET. Certifique-se de ter adicionado as referências necessárias e importado os namespaces apropriados.

## Passo 2: Carregando o documento

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Nesta etapa, carregamos o documento usando o`Document` método e passando o caminho para o arquivo DOCX a ser carregado.

## Etapa 3: configurar opções de backup OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 Nesta etapa, configuramos as opções de salvamento OOXML usando o`OoxmlSaveOptions` aula. Ativamos a atualização automática da última propriedade de tempo salvo definindo`UpdateLastSavedTimeProperty` para`true`.

## Passo 4: Salve o documento com propriedade atualizada

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Nesta última etapa, salvamos o documento usando o`Save` método e passando o caminho para o arquivo de saída com o`.docx` extensão, junto com as opções de salvamento especificadas.

Agora você pode executar o código-fonte para atualizar automaticamente a propriedade do último horário de salvamento ao salvar um documento. O arquivo resultante será salvo no diretório especificado com o nome "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Exemplo de código-fonte para atualizar a propriedade do último horário salvo usando Aspose.Words for .NET 

```csharp

// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusão

Neste tutorial, exploramos o recurso de atualização automática da propriedade do último horário de salvamento ao salvar um documento usando Aspose.Words for .NET. Ao ativar esse recurso com opções de salvamento OOXML, você pode garantir que a última propriedade de horário de salvamento seja atualizada automaticamente no documento gerado.

Atualizar a propriedade do último horário salvo pode ser útil para rastrear alterações e versões de um documento. Ele também controla quando o documento foi salvo pela última vez, o que pode ser útil em vários cenários.

Aspose.Words for .NET facilita a atualização automática da propriedade Last Backup Time, fornecendo opções de backup flexíveis e poderosas. Você pode integrar esse recurso em seus projetos para garantir que os documentos gerados tenham informações de backup precisas.