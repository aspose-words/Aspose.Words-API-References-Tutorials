---
title: 경고 소스 사용
linktitle: 경고 소스 사용
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 단계별 가이드를 통해 경고 소스를 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-markdown/use-warning-source/
---

이 예에서는 Aspose.Words for .NET에서 경고 소스를 사용하는 방법을 보여 드리겠습니다. 경고 소스는 콜백 함수를 사용할 때 경고의 출처를 나타냅니다.

## 1단계: 문서 로드

 다음을 사용하여 경고가 포함된 기존 문서를 로드합니다.`Load` 의 방법`Document` 수업.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## 3단계: 경고 소스 사용

 문서의`WarningCallback` 속성을 컬렉션으로`WarningInfo` 사물.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## 4단계: 문서 저장

마지막으로 원하는 형식으로 문서를 저장할 수 있습니다.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### .NET용 Aspose.Words와 함께 경고 소스를 사용하기 위한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

축하합니다! 이제 Aspose.Words for .NET에서 경고 소스를 사용하는 방법을 배웠습니다.

### FAQ

#### Q: "경고" 태그의 모양을 사용자 정의할 수 있습니까?

 A: "경고" 태그의 형식은 사용된 마크다운 렌더러에 따라 다릅니다. 대부분의 경우 CSS를 사용하여 디자인을 맞춤설정할 수 있습니다.`blockquote` 문서에 태그를 추가하세요.

#### Q: "경고" 태그에 아이콘을 추가할 수 있나요?

A: 예, Markdown 문서에서 HTML 코드를 사용하여 "경고" 태그에 아이콘을 추가할 수 있습니다. 다음을 삽입할 수 있습니다.`span` 경고 텍스트 옆에 아이콘을 표시하려면 적절한 클래스로 태그를 지정하세요.

#### Q: "경고" 태그는 모든 Markdown 리더와 호환됩니까?

 A: "경고" 태그의 호환성은 사용된 마크다운 렌더링에 따라 다릅니다. 대부분의 Markdown 리더는`blockquote` 태그를 사용하여 강조 표시된 텍스트를 표시할 수 있지만 정확한 모양은 다를 수 있습니다.