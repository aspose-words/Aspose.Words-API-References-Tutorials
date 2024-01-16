---
title: 로케일 변경
linktitle: 로케일 변경
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 날짜 및 숫자 형식의 로케일을 변경하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/change-locale/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 로케일을 변경하는 과정을 안내합니다. 로캘을 수정하면 메일 병합 작업 중 날짜와 숫자의 형식을 제어할 수 있습니다. 이를 달성하는 데 필요한 C# 소스 코드와 단계별 지침을 제공합니다.

## 전제조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 .NET 라이브러리용 Aspose.Words.

## 1단계: 문서 및 DocumentBuilder 만들기
시작하려면 Document 클래스와 DocumentBuilder 객체의 인스턴스를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 필드 삽입
그런 다음 InsertField 메서드를 사용하여 문서에 병합 필드를 삽입합니다.

```csharp
builder.InsertField("MERGEFIELD Date");
```

위 코드에서는 "Date"라는 병합 필드를 문서에 삽입합니다.

## 3단계: 로케일 변경
날짜 및 숫자 형식에 대한 로케일을 변경하려면 스레드의 현재 문화권을 수정하면 됩니다. 이 예에서는 로캘을 독일어("de-DE")로 설정합니다.

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

위 코드에서는 현재 문화권을 저장한 다음 현재 스레드의 문화권을 독일어로 설정합니다.

## 4단계: 메일 병합 수행
메일 병합 작업을 수행하고 "날짜" 필드에 날짜 값을 제공합니다.

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

이 코드 조각에서는 메일 병합 작업을 실행하고 현재 날짜를 "날짜" 필드의 값으로 제공합니다.

## 5단계: 원래 로케일 복원
메일 병합이 완료되면 스레드의 원래 문화권을 복원합니다.

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

위 코드에서는 스레드의 원래 문화권을 복원합니다.

## 6단계: 문서 저장
Document 클래스의 Save 메서드를 사용하여 수정된 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### .NET용 Aspose.Words를 사용하여 로케일을 변경하는 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 Word 문서에서 로케일을 변경하기 위한 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## 결론
축하해요! .NET용 Aspose.Words를 사용하여 Word 문서에서 로케일을 변경하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 메일 병합 작업 중 날짜와 숫자의 형식을 제어할 수 있습니다. 문서에서 정확하고 일관된 형식을 보장하려면 요구 사항에 따라 로캘을 사용자 정의하세요.

### FAQ

#### Q: Aspose.Words는 다른 버전의 Microsoft Word와 호환됩니까?

A: 예, Aspose.Words는 Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 및 Word 2019를 포함한 다양한 버전의 Microsoft Word와 호환됩니다.

#### Q: Aspose.Words는 복잡한 필드 구조를 지원합니까?

답: 물론이죠! Aspose.Words는 중첩 필드, 계산 및 조건식을 포함한 복잡한 필드 구조에 대한 광범위한 지원을 제공합니다. 이 강력한 API를 사용하여 모든 유형의 필드 구조로 작업할 수 있습니다.

#### Q: Aspose.Words는 필드 업데이트 작업을 지원합니까?

A: 네, Aspose.Words를 사용하면 일정에 따라 필드를 업데이트할 수 있습니다. API를 사용하면 쉽게 필드 값을 업데이트하고, 계산을 새로 고치고, 기타 필드 관련 작업을 수행할 수 있습니다.

#### Q: Aspose.Words를 사용하여 필드를 일반 텍스트로 변환할 수 있습니까?

답: 물론이죠! Aspose.Words는 필드를 일반 텍스트로 변환하는 방법을 제공합니다. 이는 서식이나 필드 관련 기능 없이 콘텐츠를 추출해야 할 때 유용할 수 있습니다.

#### Q: Aspose.Words를 사용하여 동적 필드가 있는 Word 문서를 생성할 수 있습니까?

답: 물론이죠! Aspose.Words는 동적 필드가 포함된 Word 문서를 생성하기 위한 강력한 기능을 제공합니다. 미리 정의된 필드가 있는 템플릿을 생성하고 여기에 데이터를 동적으로 채워 문서 생성을 위한 유연하고 효율적인 솔루션을 제공할 수 있습니다.