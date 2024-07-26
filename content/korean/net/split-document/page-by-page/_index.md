---
title: Word 문서를 페이지별로 분할
linktitle: Word 문서를 페이지별로 분할
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 개별 페이지로 분할하는 방법을 알아보세요. 이 강력한 API는 문서 분할 프로세스를 단순화하여 효율적이고 편리하게 만듭니다.
type: docs
weight: 10
url: /ko/net/split-document/page-by-page/
---

이 튜토리얼에서는 Aspose.Words for .NET의 문서 처리 기능을 사용하여 Word 문서를 개별 페이지로 분할하는 방법을 안내합니다. 소스 코드를 이해하고 각 페이지에 대한 별도의 문서를 얻으려면 아래 단계를 따르십시오.

## 1단계: 문서 로드

시작하려면 문서의 디렉터리를 지정하고 문서를 Document 객체에 로드하세요. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## 2단계: 문서를 페이지별로 분할

이제 문서의 각 페이지를 반복하고 문서를 개별 페이지로 나누겠습니다. 방법은 다음과 같습니다.

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// 각 페이지를 별도의 문서로 저장합니다.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### .NET용 Aspose.Words를 사용하는 Page By Page의 예제 소스 코드

다음은 .NET용 Aspose.Words의 페이지별 기능에 대한 전체 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// 각 페이지를 별도의 문서로 저장합니다.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

이 코드를 사용하면 .NET용 Aspose.Words를 사용하여 Word 문서를 개별 페이지로 분할할 수 있습니다. 필요한 경우 별도의 문서를 병합할 수도 있습니다.

## 결론

축하해요! Aspose.Words for .NET의 페이지별 기능을 사용하여 Word 문서를 개별 페이지로 분할하는 방법을 배웠습니다. 제공된 소스코드를 따라가면 문서의 각 페이지를 추출하여 별도의 문서로 저장할 수 있습니다.

페이지별로 문서를 분할하는 것은 특정 페이지로 작업하거나 콘텐츠를 세부적으로 배포해야 할 때 유용할 수 있습니다. Aspose.Words for .NET은 문서 분할 프로세스를 단순화하여 효율적이고 편리하게 만드는 강력한 API를 제공합니다.

문서 처리 기능을 향상하고 작업 흐름을 간소화하기 위해 Aspose.Words for .NET에서 제공하는 다른 기능을 자유롭게 탐색해 보세요.

### 자주 묻는 질문

#### .NET용 Aspose.Words를 사용하여 문서를 여러 페이지로 분할하려면 어떻게 해야 합니까?

 문서를 여러 페이지로 분할하려면`ExtractPages` Aspose.Words API의 메소드를 사용하여 페이지 범위를 가져옵니다. 시작 페이지와 추출할 페이지 수를 지정하면 각 페이지마다 별도의 문서를 생성할 수 있습니다.

#### 문서를 페이지별로 분할할 때 출력 형식을 사용자 정의할 수 있나요?

예, Aspose.Words for .NET은 문서를 페이지별로 분할할 때 다양한 출력 형식을 지원합니다. 요구 사항에 따라 각 페이지를 DOCX, PDF, HTML 등과 같은 형식의 별도 문서로 저장할 수 있습니다.

#### 특정 페이지 범위로 문서를 분할할 수 있나요?

전적으로! .NET용 Aspose.Words를 사용하면 특정 페이지 범위로 문서를 분할할 수 있습니다. 시작 페이지와 추출할 페이지 수를 조정하여 문서 분할 페이지 범위를 정확하게 정의할 수 있습니다.

#### 분할된 문서를 다시 하나의 문서로 병합할 수 있나요?

예, Aspose.Words for .NET에서 제공하는 병합 기능을 사용하여 분할된 문서를 다시 단일 문서로 병합할 수 있습니다. 필요에 따라 별도의 문서를 결합하여 원본 문서를 다시 만들거나 다른 구조로 새 문서를 만들 수 있습니다.