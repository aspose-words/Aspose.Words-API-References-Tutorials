---
title: 각 섹션에서 목록 다시 시작
linktitle: 각 섹션에서 목록 다시 시작
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 각 섹션에 번호 매기기 목록을 재설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-list/restart-list-at-each-section/
---

이 단계별 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서의 각 섹션에 번호 매기기 목록을 재설정하는 방법을 보여줍니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 구성되어 있는지 확인하세요. 아직 설치하지 않았다면 다음에서 라이브러리를 다운로드하여 설치하세요.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 문서 및 목록 만들기

먼저 새 문서를 만들고 기본 번호 매기기 목록을 추가합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## 2단계: 목록에 항목 추가하기

 그런 다음`DocumentBuilder` 목록에 항목을 추가하려면 루프를 사용하여 목록에 여러 항목을 추가할 수 있습니다.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

이 예에서는 번호 다시 매기기를 설명하기 위해 15번째 목록 항목 뒤에 구역 나누기를 삽입합니다.

## 3단계: 수정된 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

그래서 ! .NET용 Aspose.Words를 사용하여 Word 문서의 각 섹션에 대한 번호 매기기 목록을 성공적으로 재설정했습니다.

### 각 섹션의 목록을 재설정하는 예제 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 맞게 수정하십시오.

### FAQ

#### Q: Aspose.Words의 모든 섹션에서 목록을 어떻게 다시 시작할 수 있나요?

 A: Aspose.Words의 모든 섹션에서 목록을 다시 시작하려면`List` 수업을 하고 번호가 매겨진 목록을 할당하세요. 그런 다음`List.IsRestartAtEachSection` 속성을 사용하여 각 섹션에서 번호 매기기를 다시 시작하도록 지정합니다. 각 섹션에서 번호 매기기가 올바르게 다시 시작되도록 이 목록을 문서의 하나 이상의 섹션과 연결할 수 있습니다.

#### Q: Aspose.Words에서 목록의 번호 매기기 형식을 사용자 정의할 수 있나요?

A: 예, Aspose.Words에서 목록의 번호 매기기 형식을 사용자 정의할 수 있습니다. 그만큼`List` 클래스는 이에 대한 여러 속성을 제공합니다.`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`등. 이러한 속성을 사용하여 목록 유형(번호 매기기, 글머리 기호 등), 번호 매기기 형식(아라비아 숫자, 로마 숫자, 문자 등) 및 기타 번호 매기기 형식 옵션을 설정할 수 있습니다.

#### Q: Aspose.Words의 번호 매기기 목록에 추가 레벨을 추가할 수 있습니까?

 A: 예, Aspose.Words의 번호 목록에 추가 수준을 추가하는 것이 가능합니다. 그만큼`ListLevel` 클래스를 사용하면 목록의 각 수준에 대한 서식 속성을 설정할 수 있습니다. 접두사, 접미사, 정렬, 들여쓰기 등과 같은 옵션을 설정할 수 있습니다. 이를 통해 여러 수준의 계층 구조로 목록을 만들 수 있습니다.