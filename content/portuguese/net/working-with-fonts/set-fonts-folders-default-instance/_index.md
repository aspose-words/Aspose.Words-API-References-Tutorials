---
title: Definir instância padrão das pastas de fontes
linktitle: Definir instância padrão das pastas de fontes
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir a pasta de fontes padrão ao renderizar um documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-fonts-folders-default-instance/
---

Neste tutorial, orientaremos você no processo passo a passo para definir a pasta de fontes padrão ao renderizar um documento usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como definir a pasta de fontes padrão a ser usada ao renderizar seus documentos usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento renderizado editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: definir a pasta de fontes padrão
 Então você pode definir a pasta de fontes padrão usando o`FontSettings.DefaultInstance` classe e o`SetFontsFolder()`método. Especifique o caminho para a pasta de fontes que deseja usar como pasta padrão.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Etapa 3: carregue o documento para renderizar
 Agora você pode carregar o documento para renderizar usando o`Document` aula. Certifique-se de especificar o caminho correto do documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 4: salve o documento renderizado
 Finalmente, você pode salvar o documento renderizado em um arquivo usando o`Save()` método do`Document` aula. Certifique-se de especificar o caminho e o nome do arquivo corretos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Exemplo de código-fonte para definir instância padrão de pastas de fontes usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Conclusão
Neste tutorial, aprendemos como definir a pasta de fontes padrão ao renderizar um documento usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode especificar facilmente qual pasta de fontes usar como pasta padrão ao renderizar seus documentos. Aspose.Words oferece uma API poderosa e flexível para processamento de palavras com fontes em seus documentos. Com esse conhecimento, você pode controlar e personalizar as fontes de fontes usadas ao renderizar seus documentos de acordo com suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso definir pastas de fontes padrão em Aspose.Words?

 R: Para definir pastas de fontes padrão em Aspose.Words, você deve usar o`Fonts` classe e o`SetFontsFolders` método para especificar locais de pastas de fontes personalizadas.

#### P: A configuração de pastas de fontes padrão afeta todos os documentos do Word processados com Aspose.Words?

R: Sim, a configuração de pastas de fontes padrão afeta todos os documentos do Word processados com Aspose.Words. Depois de definir as pastas de fontes padrão, o Aspose.Words usará esses locais para procurar fontes em todos os documentos.

#### P: Posso definir várias pastas de fontes padrão em Aspose.Words?

 R: Sim, você pode definir várias pastas de fontes padrão em Aspose.Words. Você só precisa especificar os locais das pastas de fontes personalizadas usando o`SetFontsFolders` método do`Fonts` aula.

#### P: Como posso verificar as pastas de fontes padrão atualmente definidas no Aspose.Words?

 R: Para verificar as pastas de fontes padrão atualmente definidas no Aspose.Words, você pode usar o`GetFolders` método do`Fonts` class para obter os locais das pastas de fontes configuradas.

#### P: A configuração de pastas de fontes padrão permite que eu use fontes personalizadas em meus documentos do Word?

R: Sim, ao definir pastas de fontes padrão, você pode usar fontes personalizadas em seus documentos do Word. Você só precisa colocar as fontes nas pastas especificadas e Aspose.Words as utilizará ao gerar ou manipular os documentos.