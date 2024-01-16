---
title: Definir configurações de substituição de fonte
linktitle: Definir configurações de substituição de fonte
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir configurações de substituição de fonte em Aspose.Words for .NET e personalizar a substituição de fonte em seus documentos do Word.
type: docs
weight: 10
url: /pt/net/working-with-fonts/set-font-fallback-settings/
---
Neste tutorial, mostraremos como definir configurações de substituição de fonte em um documento do Word usando Aspose.Words for .NET. As configurações de substituição de fontes permitem especificar fontes de substituição a serem usadas quando as fontes especificadas não estiverem disponíveis.

## Pré-requisitos
Antes de começar, certifique-se de ter os seguintes itens:
- Conhecimento prático da linguagem de programação C#
- A biblioteca Aspose.Words para .NET instalada em seu projeto

## Passo 1: Defina o diretório do documento
 Comece definindo o caminho do diretório para o local do seu documento do Word. Substituir`"YOUR DOCUMENT DIRECTORY"` no código com o caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: carregar as configurações de substituição de fonte
 Crie uma instância do`FontSettings` classe e use o`Load` método para carregar configurações de substituição de fonte de um arquivo XML. O arquivo XML especificado deve conter as regras de substituição de fonte a serem usadas.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Etapa 3: aplicar configurações de substituição de fonte
 Associe as configurações de substituição de fonte ao documento, atribuindo-as ao documento`FontSettings` propriedade.

```csharp
doc.FontSettings = fontSettings;
```

## Etapa 4: salve o documento
 Salve o documento usando o`Save` método do`Document` com o caminho e nome de arquivo apropriados.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Exemplo de código-fonte para definir configurações de fallback de fonte usando Aspose.Words for .NET 
```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Conclusão
Neste tutorial, você aprendeu como definir configurações de substituição de fonte em um documento do Word usando Aspose.Words for .NET. Experimente diferentes regras de substituição de fontes para garantir que seu documento pareça consistente, mesmo quando as fontes especificadas não estiverem disponíveis.

### Perguntas frequentes

#### P: Como posso definir configurações de substituição de fonte em um documento do Word com Aspose.Words?

R: Para definir configurações de substituição de fonte em um documento do Word com Aspose.Words, você pode usar a API para especificar fontes substitutas a serem usadas quando as fontes necessárias não estiverem disponíveis. Isso garante uma visualização consistente do texto, mesmo sem as fontes originais.

#### P: É possível lidar com fontes substitutas ao substituir um documento do Word por Aspose.Words?

R: Sim, com Aspose.Words você pode gerenciar fontes substitutas ao substituí-las em um documento do Word. A API permite detectar fontes ausentes e especificar fontes substitutas apropriadas para manter a aparência consistente do texto mesmo quando as fontes são substituídas.

#### P: Por que é importante definir corretamente as configurações de substituição de fonte em um documento do Word?

R: É importante definir corretamente as configurações de substituição de fonte em um documento do Word para manter a integridade visual do texto. Ao definir as fontes substitutas apropriadas com Aspose.Words, você garante que o texto será exibido de forma consistente, mesmo que as fontes necessárias não estejam disponíveis.

#### P: Como posso detectar fontes ausentes ao substituí-las em um documento do Word por Aspose.Words?

R: Aspose.Words permite detectar fontes ausentes durante a substituição em um documento do Word usando a API. Você pode usar métodos fornecidos por Aspose.Words para verificar a disponibilidade das fontes necessárias e tomar as medidas apropriadas em caso de falta de fontes.

#### P: A substituição de fontes afeta o layout do meu documento do Word?

R: A substituição de fontes pode afetar o layout do seu documento do Word se as fontes substitutas tiverem dimensões diferentes das fontes originais. No entanto, escolhendo fontes substitutas com sabedoria e definindo as configurações de substituição de fontes com Aspose.Words, você pode minimizar os impactos no layout.