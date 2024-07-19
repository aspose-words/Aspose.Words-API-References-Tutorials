---
title: 페이지 번호 매기기 다시 시작
linktitle: 페이지 번호 매기기 다시 시작
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 결합하고 추가하는 동안 페이지 번호 매기기를 다시 시작하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/restart-page-numbering/
---
## 소개

각각 페이지 번호 1로 시작하는 별도의 섹션이 있는 세련된 문서를 만드는 데 어려움을 겪은 적이 있습니까? 장이 새로 시작되는 보고서나 요약 및 세부 부록을 위한 별도의 섹션이 있는 긴 제안을 상상해 보십시오. 강력한 문서 처리 라이브러리인 Aspose.Words for .NET을 사용하면 이를 정교하게 달성할 수 있습니다. 이 포괄적인 가이드는 페이지 번호 매기기를 다시 시작하는 비결을 공개하여 전문가 수준의 문서를 쉽게 만들 수 있도록 도와줍니다.

## 전제조건

이 여정을 시작하기 전에 다음 사항을 확인하세요.

1.  .NET용 Aspose.Words: 공식 웹사이트에서 라이브러리를 다운로드하세요.[다운로드 링크](https://releases.aspose.com/words/net/) . 무료 평가판을 탐색할 수 있습니다.[무료 평가판 링크](https://releases.aspose.com/) 또는 라이센스를 구매하세요[구매링크](https://purchase.aspose.com/buy) 귀하의 필요에 따라.
2. AC# 개발 환경: Visual Studio 또는 .NET 개발을 지원하는 모든 환경이 완벽하게 작동합니다.
3. 샘플 문서: 실험하고 싶은 Word 문서를 찾으세요.

## 필수 네임스페이스 가져오기

Aspose.Words 개체 및 기능과 상호 작용하려면 필요한 네임스페이스를 가져와야 합니다. 수행 방법은 다음과 같습니다.

```csharp
using Aspose.Words;
using Aspose.Words.Settings;
```

 이 코드 조각은`Aspose.Words` 핵심 문서 조작 클래스에 대한 액세스를 제공하는 네임스페이스입니다. 추가적으로, 우리는`Aspose.Words.Settings` 네임스페이스는 문서 동작을 사용자 정의하기 위한 옵션을 제공합니다.


이제 문서 내에서 페이지 번호 매기기를 다시 시작하는 것과 관련된 실제 단계를 살펴보겠습니다.

## 1단계: 소스 및 대상 문서 로드:

 문자열 변수 정의`dataDir` 문서 디렉토리의 경로를 저장합니다. "YOUR DOCUMENT DIRECTORY"를 실제 위치로 바꾸십시오.

 2개 생성`Document` 를 사용하는 객체`Aspose.Words.Document`건설자. 첫번째 (`srcDoc`)에는 추가할 콘텐츠가 포함된 소스 문서가 보관됩니다. 두번째 (`dstDoc`)는 다시 시작된 페이지 번호 매기기와 함께 소스 콘텐츠를 통합할 대상 문서를 나타냅니다.

```csharp
string dataDir = @"C:\MyDocuments\"; // 실제 디렉터리로 바꾸세요.
Document srcDoc = new Document(dataDir + "source.docx");
Document dstDoc = new Document(dataDir + "destination.docx");
```

## 2단계: 섹션 나누기 설정:

 액세스`FirstSection` 원본 문서의 속성(`srcDoc`) 초기 섹션을 조작합니다. 이 섹션에서는 페이지 번호 매기기가 다시 시작됩니다.

 활용`PageSetup` 섹션의 속성을 사용하여 레이아웃 동작을 구성합니다.

 설정`SectionStart` 의 자산`PageSetup` 에게`SectionStart.NewPage`. 이렇게 하면 소스 콘텐츠가 대상 문서에 추가되기 전에 새 페이지가 생성됩니다.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 3단계: 페이지 번호 매기기 다시 시작 활성화:

 같은 것 안에서`PageSetup` 소스 문서의 첫 번째 섹션 개체를 설정합니다.`RestartPageNumbering`재산`true`. 이 중요한 단계는 Aspose.Words가 추가된 콘텐츠에 대해 페이지 번호 매기기를 새로 시작하도록 지시합니다.

```csharp
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## 4단계: 원본 문서 추가:

이제 원하는 페이지 나누기 및 번호 매기기 구성으로 소스 문서가 준비되었으므로 이를 대상 문서에 통합할 차례입니다.

 고용하다`AppendDocument` 대상 문서의 방법(`dstDoc`) 소스 콘텐츠를 원활하게 추가합니다.

원본 문서를 전달합니다(`srcDoc` ) 그리고`ImportFormatMode.KeepSourceFormatting` 이 방법에 대한 주장. 이 인수는 추가 시 소스 문서의 원래 형식을 유지합니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5단계: 최종 문서 저장:

 마지막으로,`Save` 대상 문서의 방법(`dstDoc`) 페이지 번호 매기기를 다시 시작하여 결합된 문서를 저장합니다. 저장된 문서에 적합한 파일 이름과 위치를 지정하십시오.

```csharp
dstDoc.Save(dataDir + "final_document.docx");
```

## 결론

결론적으로 Aspose.Words for .NET에서 페이지 나누기와 번호 매기기를 마스터하면 세련되고 잘 구성된 문서를 만들 수 있습니다. 이 가이드에 설명된 기술을 구현하면 다시 시작되는 페이지 번호 매기기와 콘텐츠를 원활하게 통합하여 전문적이고 독자 친화적인 프레젠테이션을 보장할 수 있습니다. Aspose.Words는 문서 조작을 위한 풍부한 추가 기능을 제공한다는 점을 기억하십시오.

## FAQ

### 섹션 중간에 페이지 번호 매기기를 다시 시작할 수 있나요?

 안타깝게도 .NET용 Aspose.Words는 단일 섹션 내에서 페이지 번호 매기기 다시 시작을 직접 지원하지 않습니다. 하지만 원하는 지점에 새로운 단면을 생성하고 설정을 하면 비슷한 효과를 얻을 수 있습니다.`RestartPageNumbering` 에게`true` 그 섹션에 대해.

### 다시 시작한 후 시작 페이지 번호를 어떻게 사용자 정의할 수 있나요?

 제공된 코드는 1부터 번호 매기기를 시작하지만 사용자 정의할 수 있습니다. 활용`PageNumber` 의 재산`HeaderFooter` 새 섹션 내의 개체. 이 속성을 설정하면 시작 페이지 번호를 정의할 수 있습니다.

### 원본 문서의 기존 페이지 번호는 어떻게 되나요?

원본 문서의 기존 페이지 번호는 영향을 받지 않습니다. 대상 문서 내에 추가된 내용만 번호 매기기를 다시 시작합니다.

### 다른 번호 매기기 형식(예: 로마 숫자)을 적용할 수 있나요?

 전적으로! Aspose.Words는 페이지 번호 매기기 형식에 대한 광범위한 제어를 제공합니다. 탐색`NumberStyle` 의 재산`HeaderFooter` 로마 숫자, 문자 또는 사용자 정의 형식과 같은 다양한 번호 매기기 스타일 중에서 선택할 수 있습니다.

### 추가 리소스나 지원은 어디서 찾을 수 있나요?

 Aspose는 포괄적인 문서 포털을 제공합니다[문서 링크](https://reference.aspose.com/words/net/) 페이지 번호 매기기 기능과 기타 Aspose.Words 기능에 대해 더 자세히 살펴봅니다. 또한 활발한 포럼[지원 링크](https://forum.aspose.com/c/words/8) 개발자 커뮤니티와 연결하고 특정 문제에 대한 지원을 구할 수 있는 훌륭한 플랫폼입니다.