---
title: Especifique a fonte padrão ao renderizar
linktitle: Especifique a fonte padrão ao renderizar
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para especificar a fonte padrão ao renderizar um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/specify-default-font-when-rendering/
---

Neste tutorial, orientaremos você no processo passo a passo para especificar a fonte padrão ao renderizar um documento usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como especificar uma fonte padrão para usar ao renderizar seus documentos usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento renderizado editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Carregue o documento para renderizar
 Em seguida, você precisa carregar o documento para renderizar usando o`Document` aula. Certifique-se de especificar o caminho correto do documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: definir a fonte padrão
 Agora você pode especificar a fonte padrão a ser usada durante a renderização criando uma instância do`FontSettings` classe e definir o`DefaultFontName` propriedade do`DefaultFontSubstitution` opor-se ao`DefaultFontSubstitution` objeto`SubstitutionSettings` de`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Etapa 4: salve o documento renderizado
 Finalmente, você pode salvar o documento renderizado em um arquivo usando o`Save()` método do`Document` aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Exemplo de código-fonte para especificar fonte padrão ao renderizar usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Se a fonte padrão definida aqui não puder ser encontrada durante a renderização, então
// a fonte mais próxima da máquina é usada.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusão
Neste tutorial, aprendemos como especificar a fonte padrão ao renderizar um documento usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode definir facilmente uma fonte padrão para usar ao renderizar seus documentos. Aspose.Words oferece uma API poderosa e flexível para processamento de palavras com fontes em seus documentos. Com esse conhecimento, você pode controlar e personalizar a renderização de seus documentos de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso especificar uma fonte padrão ao converter para PDF no Aspose.Words?

 R: Para especificar uma fonte padrão ao converter para PDF no Aspose.Words, você pode usar o`PdfOptions` classe e definir o`DefaultFontName` propriedade ao nome da fonte desejada.

#### P: E se a fonte padrão não estiver disponível durante a conversão para PDF?

R: Se a fonte padrão especificada não estiver disponível durante a conversão para PDF, o Aspose.Words usará uma fonte substituta para exibir o texto no documento convertido. Isso pode causar uma ligeira diferença na aparência da fonte original.

#### P: Posso especificar uma fonte padrão para outros formatos de saída, como DOCX ou HTML?

R: Sim, você pode especificar uma fonte padrão para outros formatos de saída, como DOCX ou HTML, usando as opções de conversão apropriadas e definindo a propriedade correspondente para cada formato.

#### P: Como posso verificar a fonte padrão especificada em Aspose.Words?

 R: Para verificar a fonte padrão especificada em Aspose.Words, você pode usar o`DefaultFontName` propriedade do`PdfOptions` class e recupere o nome da fonte configurada.

#### P: É possível especificar uma fonte padrão diferente para cada seção do documento?

R: Sim, é possível especificar uma fonte padrão diferente para cada seção do documento usando opções de formatação específicas para cada seção. No entanto, isso exigiria uma manipulação mais avançada do documento usando os recursos do Aspose.Words.