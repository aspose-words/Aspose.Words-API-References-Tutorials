---
title: 도형을 Office 수학으로 변환
linktitle: 도형을 Office 수학으로 변환
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서를 업로드할 때 도형을 Office 수학 공식으로 변환하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-loadoptions/convert-shape-to-office-math/
---
C# 응용 프로그램에서 수학 모양이 포함된 문서로 단어를 처리할 때 더 나은 호환성과 표현을 위해 Office 수학 공식으로 변환해야 할 수도 있습니다. .NET용 Aspose.Words 라이브러리를 사용하면 문서를 로드하는 동안 도형을 Office 수학 공식으로 쉽게 변환할 수 있습니다. 이 단계별 가이드에서는 .NET C# 소스 코드용 Aspose.Words를 사용하여 LoadOptions를 사용하여 도형을 Office 수학 공식으로 변환하는 문서를 로드하는 방법을 안내합니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 .NET을 포함한 다양한 플랫폼에서 Word 문서를 생성, 편집, 변환 및 보호하는 강력한 라이브러리입니다. 텍스트 삽입, 서식 변경, 섹션 추가 등과 같은 문서 조작을 위한 다양한 기능을 제공합니다.

## 로드 옵션 구성

첫 번째 단계는 문서의 로드 옵션을 구성하는 것입니다. LoadOptions 클래스를 사용하여 로딩 매개변수를 지정합니다. 우리의 경우에는 도형을 Office 수학 공식으로 변환하려고 하므로 ConvertShapeToOfficeMath 속성을 true로 설정해야 합니다. 수행 방법은 다음과 같습니다.

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

새 LoadOptions 개체를 만들고 ConvertShapeToOfficeMath 속성을 true로 설정하여 문서를 로드할 때 도형을 Office 수학 공식으로 변환할 수 있도록 합니다.

## 도형을 Office 수학 공식으로 변환하여 문서 로드

이제 로드 옵션을 구성했으므로 Document 클래스를 사용하여 문서를 로드하고 로드 옵션을 지정할 수 있습니다. 예는 다음과 같습니다.

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

이 예에서는 지정된 로드 옵션을 사용하여 문서 디렉터리에 있는 "Office math.docx" 문서를 로드합니다.

## 문서 등록

도형을 Office 수학 공식으로 변환하여 문서를 로드한 후 Document 클래스의 Save 메서드를 사용하여 원하는 형식으로 저장할 수 있습니다. 예를 들어 문서를 .docx 형식으로 저장하려면 다음을 수행하세요.

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

"dataDir"을 문서의 디렉터리 경로로 바꿔야 합니다.

### .NET용 Aspose.Words를 사용하여 "Shape를 Office Math로 변환" 기능을 갖춘 LoadOptions의 예제 소스 코드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// "모양 변환" 기능을 사용하여 로딩 옵션 구성

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// 지정된 옵션으로 문서를 로드합니다.
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

// 원하는 형식으로 문서를 저장하세요
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## 결론

이 가이드에서는 .NET용 Aspose.Words 라이브러리를 사용하여 도형을 Office 수학 공식으로 변환하여 문서를 로드하는 방법을 설명했습니다. 제공된 단계를 따르고 제공된 C# 소스 코드를 사용하면 C# 애플리케이션에 이 기능을 쉽게 적용할 수 있습니다. 도형을 Office 수학 공식으로 변환하면 수학 요소가 포함된 문서의 호환성과 프레젠테이션이 향상됩니다.


### FAQ

#### Q: 도형을 Office 수학 수식으로 변환해야 하는 이유는 무엇입니까?

A: C# 응용 프로그램의 Word 문서 내에서 호환성을 향상하고 수학적 요소를 더 잘 표현하려면 도형을 Office 수학 공식으로 변환하는 것이 필수적입니다.

#### Q: Aspose.Words는 복잡한 수학적 표현을 처리할 수 있나요?

답: 물론이죠! Aspose.Words는 광범위한 수학적 표현과 공식을 처리할 수 있으므로 복잡한 수학적 콘텐츠를 처리하는 데 적합한 도구입니다.

#### Q: Aspose.Words는 .NET 플랫폼에만 제한됩니까?

A: Aspose.Words는 .NET에 최적화되어 있지만 Java 및 Android를 포함한 다른 플랫폼도 지원하므로 문서 처리를 위한 다목적 솔루션이 됩니다.

#### Q: 다른 목적으로 로딩 옵션을 사용자 정의할 수 있나요?

A: 그렇죠! Aspose.Words는 특정 요구 사항에 맞게 사용자 정의할 수 있는 다양한 로딩 옵션을 제공하여 라이브러리를 응용 프로그램에 원활하게 통합할 수 있도록 합니다.

#### Q: Aspose.Words는 Word 외에 다른 문서 형식을 지원합니까?

A: 예, Aspose.Words는 Word 문서 외에도 PDF, HTML, EPUB 등과 같은 다양한 형식을 지원하므로 문서 조작을 위한 포괄적인 솔루션입니다.