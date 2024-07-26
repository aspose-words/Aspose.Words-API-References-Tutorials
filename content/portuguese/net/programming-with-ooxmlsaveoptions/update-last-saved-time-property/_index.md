---
title: Atualizar propriedade do último horário salvo
linktitle: Atualizar propriedade do último horário salvo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como atualizar a última propriedade de hora salva em documentos do Word usando Aspose.Words for .NET. Siga nosso guia passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
## Introdução

Já se perguntou como controlar programaticamente a última propriedade de tempo salva em seus documentos do Word? Se você estiver lidando com vários documentos e precisar manter seus metadados, atualizar a última propriedade de horário salvo pode ser bastante útil. Hoje, vou orientá-lo nesse processo usando Aspose.Words for .NET. Então, aperte o cinto e vamos mergulhar!

## Pré-requisitos

Antes de entrarmos no guia passo a passo, há algumas coisas que você precisa:

1.  Aspose.Words for .NET: Certifique-se de ter o Aspose.Words for .NET instalado. Se ainda não o fez, você pode[baixe aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: um ambiente de desenvolvimento como o Visual Studio.
3. Conhecimento básico de C#: Compreender os fundamentos da programação C# será útil.

## Importar namespaces

Para começar, certifique-se de importar os namespaces necessários para o seu projeto. Isso permitirá que você acesse as classes e métodos necessários para manipular documentos do Word.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Agora, vamos dividir o processo em etapas simples. Cada etapa irá guiá-lo através do processo de atualização da última propriedade de horário salva em seu documento do Word.

## Etapa 1: configure seu diretório de documentos

Primeiro, você precisa especificar o caminho para o diretório do seu documento. É aqui que o documento existente é armazenado e onde o documento atualizado será salvo.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o seu diretório.

## Etapa 2: carregue seu documento do Word

 Em seguida, carregue o documento do Word que deseja atualizar. Você pode fazer isso criando uma instância do`Document` class e passando o caminho do seu documento.

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

 Certifique-se de que o documento nomeado`Document.docx` está presente no diretório especificado.

## Etapa 3: configurar opções de salvamento

 Agora, crie uma instância do`OoxmlSaveOptions` aula. Esta classe permite especificar opções para salvar seu documento no formato Office Open XML (OOXML). Aqui, você definirá o`UpdateLastSavedTimeProperty` para`true`.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions
{
    UpdateLastSavedTimeProperty = true
};
```

Isso diz ao Aspose.Words para atualizar a última propriedade de hora salva do documento.

## Etapa 4: salve o documento atualizado

 Por fim, salve o documento usando o`Save` método do`Document` class, passando o caminho onde deseja salvar o documento atualizado e as opções de salvamento.

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

Isso salvará o documento com a propriedade atualizada da última hora salva.

## Conclusão

E aí está! Seguindo essas etapas, você pode atualizar facilmente a última propriedade de hora salva de seus documentos do Word usando Aspose.Words for .NET. Isto é especialmente útil para manter metadados precisos em seus documentos, o que pode ser crucial para sistemas de gerenciamento de documentos e vários outros aplicativos.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e converter documentos Word em aplicativos .NET.

### Por que devo atualizar a última propriedade de horário salva?
Atualizar a última propriedade de hora salva ajuda a manter metadados precisos, o que é essencial para rastreamento e gerenciamento de documentos.

### Posso atualizar outras propriedades usando Aspose.Words for .NET?
Sim, Aspose.Words for .NET permite atualizar várias propriedades do documento, como título, autor e assunto.

### O Aspose.Words para .NET é gratuito?
 Aspose.Words for .NET oferece uma avaliação gratuita, mas para funcionalidade completa é necessária uma licença. Você pode obter uma licença[aqui](https://purchase.aspose.com/buy).

### Onde posso encontrar mais tutoriais sobre Aspose.Words for .NET?
Você pode encontrar mais tutoriais e documentação[aqui](https://reference.aspose.com/words/net/).
