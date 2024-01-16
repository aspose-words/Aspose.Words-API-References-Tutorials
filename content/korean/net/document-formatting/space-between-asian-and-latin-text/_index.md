---
title: Word 문서에서 아시아 텍스트와 라틴 텍스트 사이의 공간
linktitle: Word 문서에서 아시아 텍스트와 라틴 텍스트 사이의 공간
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 아시아어와 라틴어 텍스트 사이의 간격을 자동으로 조정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/document-formatting/space-between-asian-and-latin-text/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 단어 문서 기능에서 아시아어와 라틴어 텍스트 사이의 공백 기능을 사용하는 방법을 보여 드리겠습니다. 소스 코드를 이해하고 변경 사항을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서 만들기 및 구성

시작하려면 새 문서와 관련 DocumentBuilder 개체를 만듭니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 아시아어와 라틴어 텍스트 사이의 간격 설정

이제 ParagraphFormat 개체의 속성을 사용하여 아시아 텍스트와 라틴 텍스트 사이의 간격을 구성하겠습니다. 방법은 다음과 같습니다.

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## 3단계: 문서 저장

 텍스트 입력 양식 필드를 삽입한 후,`Save` 방법. 적절한 파일 경로를 제공해야 합니다.

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### .NET용 Aspose.Words를 사용하는 아시아 텍스트와 라틴 텍스트 사이의 공백에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하는 아시아 텍스트와 라틴 텍스트 사이의 공백 기능에 대한 전체 소스 코드입니다.


```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

이 코드를 사용하면 .NET용 Aspose.Words를 사용하여 문서에서 아시아 텍스트와 라틴 텍스트 사이의 간격을 자동으로 조정할 수 있습니다.

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 아시아어와 라틴어 텍스트 사이의 간격을 조정하기 위해 Space 기능을 사용하는 프로세스를 살펴보았습니다. 설명된 단계를 따르면 적절한 간격과 정렬을 보장할 수 있으며, 특히 혼합된 아시아 및 라틴 콘텐츠를 처리할 때 유용합니다.

### FAQ

#### Q: Word 문서에서 아시아어와 라틴어 텍스트 사이의 공백 기능은 무엇입니까?

A: Word 문서에서 아시아어와 라틴어 텍스트 사이의 공백 기능은 아시아어(예: 중국어, 일본어) 및 라틴어(예: 영어)와 같은 다양한 스크립트로 작성된 텍스트 사이의 간격을 자동으로 조정하는 기능을 의미합니다.

#### Q: 아시아어와 라틴어 텍스트 사이의 간격을 조정하는 것이 왜 중요한가요?

A: 문서 내에서 다양한 스크립트가 조화롭게 혼합되도록 하려면 아시아 텍스트와 라틴 텍스트 사이의 공간을 조정하는 것이 중요합니다. 적절한 간격은 가독성과 전반적인 시각적 모양을 향상시켜 텍스트가 너무 비좁거나 퍼지는 것을 방지합니다.

#### Q: 서로 다른 스크립트 간의 공간 조정을 사용자 정의할 수 있습니까?

 A: 예.`AddSpaceBetweenFarEastAndAlpha` 그리고`AddSpaceBetweenFarEastAndDigit` 속성. 이러한 속성을 활성화하거나 비활성화하면 아시아어와 라틴 문자 사이는 물론 아시아어 텍스트와 숫자 사이의 간격도 제어할 수 있습니다.

#### Q: .NET용 Aspose.Words는 다른 문서 서식 기능을 지원합니까?

A: 예, Aspose.Words for .NET은 다양한 문서 서식 기능에 대한 광범위한 지원을 제공합니다. 여기에는 글꼴 스타일, 단락, 표, 이미지 등에 대한 기능이 포함되어 있습니다. 프로그래밍 방식으로 Word 문서를 효과적으로 조작하고 서식을 지정할 수 있습니다.

#### Q: Aspose.Words for .NET에 대한 추가 리소스와 문서는 어디서 찾을 수 있나요?

 A: .NET용 Aspose.Words 사용에 대한 포괄적인 리소스와 문서를 보려면 다음을 방문하세요.[Aspose.Words API 참조](https://reference.aspose.com/words/net/). 여기에서 Aspose.Words for .NET의 강력한 기능을 효과적으로 활용하는 데 도움이 되는 자세한 가이드, 튜토리얼, 코드 예제 및 API 참조를 찾을 수 있습니다.