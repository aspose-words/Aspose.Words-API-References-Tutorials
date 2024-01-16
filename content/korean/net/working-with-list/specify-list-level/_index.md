---
title: 목록 수준 지정
linktitle: 목록 수준 지정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 목록 수준을 지정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-list/specify-list-level/
---

이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 목록 수준을 지정하는 방법을 보여줍니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 구성되어 있는지 확인하세요. 아직 설치하지 않았다면 다음에서 라이브러리를 다운로드하여 설치하세요.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 문서 및 문서 생성기 만들기

먼저 새 문서와 관련 문서 생성기를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 번호 매기기 목록 만들기 및 적용

다음으로, Microsoft Word의 목록 템플릿 중 하나를 기반으로 번호 매기기 목록을 만들고 이를 문서 작성기의 현재 단락에 적용합니다.

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## 3단계: 목록 수준 사양

 문서 작성기의 사용`ListLevelNumber` 목록 수준을 지정하고 단락에 텍스트를 추가하는 속성:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

목록 수준을 지정하고 각 수준에 텍스트를 추가하려면 이 단계를 반복하세요.

## 4단계: 글머리 기호 목록 생성 및 적용

Microsoft Word의 목록 템플릿 중 하나를 사용하여 글머리 기호 목록을 만들고 적용할 수도 있습니다.

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## 5단계: 글머리 기호 목록 수준에 텍스트 추가

 사용`ListLevelNumber` 속성을 다시 사용하여 글머리 기호 목록 수준을 지정하고 텍스트를 추가합니다.

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## 6단계: 목록 서식 지정 중지

 목록 서식 지정을 중지하려면 다음을 설정하세요.`null` ~로`List` 문서 생성기의 속성:

```csharp
builder. ListFormat. List = null;
```

## 7단계: 수정된 문서 저장

수정된 문서를 저장합니다.

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

그래서 ! .NET용 Aspose.Words를 사용하여 Word 문서에서 목록 수준을 성공적으로 지정했습니다.

### 목록 수준을 지정하는 샘플 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Microsoft Word 목록 템플릿 중 하나를 기반으로 번호 매기기 목록 만들기
//문서 작성기의 현재 단락에 적용합니다.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// 이 목록에는 9개의 레벨이 있습니다. 모두 시도해 보겠습니다.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Microsoft Word 목록 템플릿 중 하나를 기반으로 글머리 기호 목록 만들기
//문서 작성기의 현재 단락에 적용합니다.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// 이는 목록 형식 지정을 중지하는 방법입니다.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### FAQ

#### Q: Aspose.Words에서 목록 수준을 어떻게 지정합니까?

 A: Aspose.Words에서 목록 수준을 지정하려면`List` 수업을 듣고 번호가 매겨진 목록을 제공하세요. 그런 다음`Paragraph.ListFormat.ListLevelNumber` 각 목록 항목의 수준을 지정하는 속성입니다. 목록 항목이 원하는 수준을 갖도록 이 목록을 문서의 섹션과 연결할 수 있습니다.

#### Q: Aspose.Words에서 목록 항목의 번호 매기기 형식을 변경할 수 있나요?

 A: 예, Aspose.Words에서 목록 항목의 번호 매기기 형식을 변경할 수 있습니다. 그만큼`ListLevel` 클래스는 이에 대한 여러 속성을 제공합니다.`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`등. 이러한 속성을 사용하여 아라비아 숫자, 로마 숫자, 문자 등과 같은 목록 항목의 번호 매기기 형식을 설정할 수 있습니다.

#### Q: Aspose.Words의 번호 목록에 추가 레벨을 추가할 수 있나요?

 A: 예, Aspose.Words의 번호 목록에 추가 수준을 추가하는 것이 가능합니다. 그만큼`ListLevel` 클래스를 사용하면 목록의 각 수준에 대한 서식 속성을 설정할 수 있습니다. 접두사, 접미사, 정렬, 들여쓰기 등과 같은 옵션을 설정할 수 있습니다. 이를 통해 여러 수준의 계층 구조로 목록을 만들 수 있습니다.


