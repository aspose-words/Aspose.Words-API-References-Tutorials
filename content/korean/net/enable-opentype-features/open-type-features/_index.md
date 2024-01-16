---
title: 개방형 특징
linktitle: 개방형 특징
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET에서 개방형 기능을 활성화하고 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/enable-opentype-features/open-type-features/
---

이 포괄적인 튜토리얼에서는 Aspose.Words for .NET에서 개방형 기능을 활성화하고 활용하는 방법을 배웁니다. 우리는 프로세스를 안내하고 필요한 C# 코드 조각을 제공할 것입니다. 이 가이드가 끝나면 Word 문서에서 Open Type 기능을 사용할 수 있게 됩니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 문서 로드
시작하려면 Document 클래스를 사용하여 문서를 로드합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## 2단계: 개방형 기능 활성화
개방형 기능을 활성화하려면 LayoutOptions 클래스의 TextShaperFactory 속성을 원하는 텍스트 셰이퍼 팩토리의 인스턴스로 설정하세요. 이 예에서는 HarfBuzzTextShaperFactory를 사용합니다.

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## 3단계: 문서 저장
Open Type 기능을 활성화한 후 PDF와 같은 원하는 출력 형식으로 문서를 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### .NET용 Aspose.Words를 사용하는 개방형 기능의 예제 소스 코드
다음은 .NET용 Aspose.Words의 개방형 기능을 사용하기 위한 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## 결론
축하해요! Aspose.Words for .NET에서 개방형 기능을 활성화하고 활용하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 Word 문서에서 Open Type 기능을 사용할 수 있습니다.

개방형 기능은 향상된 타이포그래피 및 텍스트 모양 기능을 제공하므로 시각적으로 매력적이고 전문적인 문서를 만들 수 있습니다. 다양한 텍스트 셰이퍼 팩토리를 실험하고 프로젝트에서 개방형 기능의 가능성을 탐색해 보세요.

### FAQ

#### Q: .NET용 Aspose.Words에서 OpenType 기능을 어떻게 활성화합니까?

A: .NET용 Aspose.Words에서 OpenType 기능을 활성화하려면 튜토리얼에 언급된 단계를 따라야 합니다.

#### Q: .NET용 Aspose.Words에서는 어떤 OpenType 기능이 지원됩니까?

A: Aspose.Words for .NET은 합자, 문자 변형, 문맥 대체 등과 같은 여러 OpenType 기능을 지원합니다.

#### Q: 특정 글꼴에서 OpenType 기능이 지원되는지 어떻게 확인할 수 있나요?

A: 다음을 사용하여 특정 글꼴에서 OpenType 기능이 지원되는지 확인할 수 있습니다.`Font.OpenTypeFeatures` .NET용 Aspose.Words의 메서드입니다.

#### Q: .NET용 Aspose.Words가 지원하는 다른 텍스트 서식 지정 기능은 무엇입니까?

A: OpenType 기능 외에도 Aspose.Words for .NET은 단락 서식 지정, 표 생성, 이미지 추가 등과 같은 다른 텍스트 서식 지정 기능도 지원합니다.

#### Q: .NET용 Aspose.Words의 모든 버전에서 OpenType 기능을 사용할 수 있습니까?

A: OpenType 기능은 .NET용 Aspose.Words의 최신 버전에서 지원됩니다. 이러한 기능을 활용하려면 호환되는 버전을 사용하고 있는지 확인하세요.