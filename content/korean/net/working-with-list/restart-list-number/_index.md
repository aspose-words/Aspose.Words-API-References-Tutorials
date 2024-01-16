---
title: 목록 번호 다시 시작
linktitle: 목록 번호 다시 시작
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 목록 수를 재설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-list/restart-list-number/
---
이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 목록 수를 재설정하는 방법을 보여줍니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 구성되어 있는지 확인하세요. 아직 설치하지 않았다면 다음에서 라이브러리를 다운로드하여 설치하세요.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 문서 및 문서 생성기 만들기

먼저 새 문서와 관련 문서 생성기를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 첫 번째 목록 생성 및 사용자 정의

다음으로, 기존 템플릿을 기반으로 목록을 만든 후 해당 수준을 사용자 정의합니다.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## 3단계: 첫 번째 목록에 항목 추가

문서 작성기를 사용하여 첫 번째 목록에 항목을 추가하고 목록 번호를 제거합니다.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 4단계: 두 번째 목록 생성 및 사용자 정의

번호를 재설정하여 첫 번째 목록을 재사용하려면 원본 목록 레이아웃의 복사본을 만듭니다.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

필요한 경우 두 번째 목록을 추가로 변경할 수도 있습니다.

## 5단계: 두 번째 목록에 항목 추가

문서 작성기를 다시 사용하여 두 번째 목록에 항목을 추가하고 목록 번호를 제거합니다.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 6단계: 수정된 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

그래서 ! .NET용 Aspose.Words를 사용하여 Word 문서의 목록 번호를 성공적으로 재설정했습니다.

### 목록 번호 재설정을 위한 샘플 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 템플릿을 기반으로 목록을 만듭니다.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// 첫 번째 목록을 재사용하려면 원래 목록 형식의 복사본을 만들어 번호 매기기를 다시 시작해야 합니다.
List list2 = doc.Lists.AddCopy(list1);

// 새 시작 번호 설정을 포함하여 어떤 방식으로든 새 목록을 수정할 수 있습니다.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### FAQ

#### Q: Aspose.Words에서 목록 번호 매기기를 어떻게 다시 시작할 수 있나요?

 A: Aspose.Words에서 목록 번호 매기기를 다시 시작하려면 다음을 사용할 수 있습니다.`ListRestartAtNumber` 의 방법`List` 수업. 이 방법을 사용하면 목록을 다시 시작해야 하는 새 다이얼 값을 설정할 수 있습니다. 예를 들어 다음을 사용할 수 있습니다.`list.ListRestartAtNumber(1)` 1부터 번호 매기기를 다시 시작합니다.

#### Q: Aspose.Words에서 다시 시작된 목록 번호 매기기의 접두사와 접미사를 사용자 정의할 수 있습니까?

 A: 예, Aspose.Words에서 다시 시작된 목록 번호 매기기의 접두사와 접미사를 사용자 정의할 수 있습니다. 그만큼`ListLevel` 클래스는 다음과 같은 속성을 제공합니다.`ListLevel.NumberPrefix` 그리고`ListLevel.NumberSuffix` 이를 통해 목록의 각 수준에 대한 접두사와 접미사를 지정할 수 있습니다. 이러한 속성을 사용하여 필요에 따라 접두사와 접미사를 사용자 지정할 수 있습니다.

#### Q: 목록을 다시 시작해야 하는 특정 번호 매기기 값을 어떻게 지정할 수 있습니까?

A: 목록을 다시 시작해야 하는 특정 숫자 값을 지정하려면`ListRestartAtNumber` 원하는 값을 인수로 전달하는 메서드입니다. 예를 들어, 5부터 번호 매기기를 다시 시작하려면 다음을 사용할 수 있습니다.`list.ListRestartAtNumber(5)`.

#### Q: Aspose.Words에서 다단계 목록 번호 매기기를 다시 시작할 수 있나요?

 A: 예, Aspose.Words는 여러 목록 수준의 다시 번호 매기기를 지원합니다. 당신은`ListRestartAtNumber` 번호 매기기를 개별적으로 다시 시작하려면 각 목록 수준에서 메서드를 사용하세요. 예를 들어 다음을 사용할 수 있습니다.`list.Levels[0].ListRestartAtNumber(1)` 첫 번째 목록 수준을 1에서 다시 시작하고`list.Levels[1].ListRestartAtNumber(1)` 1부터 시작하여 두 번째 수준 목록을 다시 시작하는 식입니다.



