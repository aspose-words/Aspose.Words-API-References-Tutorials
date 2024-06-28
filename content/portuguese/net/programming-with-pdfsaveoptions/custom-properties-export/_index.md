---
title: Exportar propriedades personalizadas em um documento PDF
linktitle: Exportar propriedades personalizadas em um documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exportar propriedades personalizadas ao converter documentos em PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Neste tutorial, orientaremos você nas etapas para exportar as propriedades personalizadas de um documento em um documento PDF usando Aspose.Words for .NET. A exportação de propriedades personalizadas permite incluir informações adicionais no documento PDF gerado. Siga os passos abaixo:

## Etapa 1: Criando um Documento e Adicionando Propriedades Personalizadas

Comece criando uma instância da classe Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Etapa 2: adicionar propriedades personalizadas
 Em seguida, adicione as propriedades personalizadas desejadas. Por exemplo, para adicionar uma propriedade "Empresa" com o valor "Apose", utilize o`Add` método da coleção CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Você pode adicionar quantas propriedades personalizadas forem necessárias.

## Passo 3: Definir opções de exportação de PDF

Crie uma instância da classe PdfSaveOptions e especifique como exportar propriedades customizadas:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Esta opção controla a exportação de propriedades personalizadas ao converter para PDF.

## Passo 4: Converter Documento em PDF

 Use o`Save` método para converter o documento em PDF especificando opções de conversão:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Certifique-se de especificar o caminho correto para salvar o PDF convertido.

### Exemplo de código-fonte para exportação de propriedades personalizadas usando Aspose.Words for .NET

Aqui está o código-fonte completo para exportar propriedades personalizadas de um documento usando Aspose.Words for .NET:


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Seguindo essas etapas, você pode exportar facilmente propriedades personalizadas de um documento ao converter para PDF com Aspose.Words for .NET.


## Conclusão

Neste tutorial, explicamos como exportar propriedades personalizadas de um documento para um documento PDF usando Aspose.Words for .NET. Seguindo as etapas descritas, você pode incluir facilmente informações adicionais no documento PDF gerado, exportando as propriedades personalizadas do documento. Aproveite os recursos do Aspose.Words for .NET para personalizar e enriquecer seus documentos PDF exportando propriedades personalizadas.

### perguntas frequentes

#### P: O que é exportar propriedades personalizadas para um documento PDF?
R: A exportação de propriedades personalizadas para um documento PDF permite que informações adicionais sejam incluídas no documento PDF gerado. Propriedades personalizadas são metadados específicos do seu documento, como tags, palavras-chave ou credenciais. Ao exportar essas propriedades personalizadas, você pode disponibilizá-las aos usuários ao visualizar o documento PDF.

#### P: Como posso exportar as propriedades personalizadas de um documento para um documento PDF usando Aspose.Words for .NET?
R: Para exportar as propriedades personalizadas de um documento para um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Crie uma instância do`Document` aula.

 Adicione as propriedades personalizadas desejadas usando o`CustomDocumentProperties` coleção. Por exemplo, use o`Add` método para adicionar uma propriedade "Empresa" com o valor "Apose".

 Crie uma instância do`PdfSaveOptions` classe e especifique como exportar propriedades customizadas usando o`CustomPropertiesExport` propriedade. O`PdfCustomPropertiesExport.Standard` value exporta propriedades personalizadas de acordo com as configurações padrão.

 Use o`Save` método do`Document` class para converter o documento em PDF especificando as opções de conversão.

#### P: Como posso acessar as propriedades personalizadas de um documento PDF?
R: Para acessar as propriedades personalizadas de um documento PDF, você pode usar um leitor de PDF compatível que suporte a visualização das propriedades do documento. Os leitores de PDF mais comuns, como o Adobe Acrobat Reader, fornecem acesso aos metadados e propriedades de um documento PDF. Geralmente você pode encontrar essas opções no menu “Arquivo” ou clicando com o botão direito no documento e selecionando “Propriedades”.