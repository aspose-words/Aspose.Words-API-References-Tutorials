---
title: 필드 업데이트 문화 소스 변경
linktitle: 필드 업데이트 문화 소스 변경
second_title: Aspose.Words 문서 처리 API
description: 필드 업데이트 문화 소스 변경, .NET용 Aspose.Words에서 문화 소스를 수정하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/working-with-fields/change-field-update-culture-source/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 필드 업데이트 문화 소스를 변경하는 과정을 안내합니다. 문화 소스를 수정하면 필드 업데이트 및 메일 병합 작업 중에 날짜 형식을 제어할 수 있습니다. 이를 달성하는 데 필요한 C# 소스 코드와 단계별 지침을 제공합니다.

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

## 2단계: 특정 로케일의 콘텐츠 삽입
다음으로 로캘을 독일어로 설정하고 날짜 형식이 포함된 필드를 삽입합니다.

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

위 코드에서는 글꼴 로케일을 독일어(로케일 ID 1031)로 설정하고 특정 날짜 형식이 있는 두 개의 필드를 삽입합니다.

## 3단계: 필드 업데이트 문화 소스 변경
필드 업데이트 문화권 소스를 변경하려면 FieldOptions 클래스를 사용하세요.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

이 예에서는 필드 업데이트 중에 사용되는 문화권이 필드에서 사용되는 문화권에서 선택되도록 설정합니다.

## 4단계: 메일 병합 수행
메일 병합 작업을 수행하고 "Date2" 필드에 날짜 값을 지정합니다.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

이 코드 조각에서는 메일 병합 작업을 실행하고 "Date2" 필드에 DateTime 값을 제공합니다.

## 5단계: 문서 저장
Document 클래스의 Save 메서드를 사용하여 수정된 문서를 파일에 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### .NET용 Aspose.Words를 사용하여 필드 업데이트 문화 소스를 변경하기 위한 예제 소스 코드
다음은 .NET용 Aspose.Words를 사용하여 Word 문서에서 필드 업데이트 문화 소스를 변경하기 위한 전체 소스 코드입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## 결론
축하해요! .NET용 Aspose.Words를 사용하여 Word 문서에서 필드 업데이트 문화 소스를 변경하는 방법을 성공적으로 배웠습니다. 단계별 가이드를 따르고 제공된 소스 코드를 활용하면 이제 필드 업데이트 및 메일 병합 작업 중 날짜 형식 지정에 사용되는 문화권을 제어할 수 있습니다. 정확하고 일관된 날짜를 보장하기 위해 요구 사항에 따라 배양 소스를 사용자 정의하십시오.

### FAQ

#### Q: Aspose.Words for .NET에서 필드 업데이트 문화 소스를 어떻게 변경할 수 있나요?

 A: .NET용 Aspose.Words에서 필드 업데이트 문화 소스를 변경하려면 다음을 사용할 수 있습니다.`Document.FieldOptions.CultureSource` 속성을 지정하고 해당 값을 다음으로 설정합니다.`FieldCultureSource.FieldCode` 또는`FieldCultureSource.CurrentThread` . 예를 들어 다음을 사용할 수 있습니다.`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` 필드 코드에 정의된 문화권을 사용합니다.

#### Q: Aspose.Words for .NET에서 필드를 업데이트하기 위해 특정 문화권을 어떻게 지정할 수 있습니까?

 A: .NET용 Aspose.Words에서 필드를 업데이트하기 위한 특정 문화권을 지정하려면 다음을 사용할 수 있습니다.`Document.FieldOptions.FieldUpdateCultureInfo` 속성을 설정하고`CultureInfo` 원하는 문화에 해당하는 개체입니다. 예를 들어 다음을 사용할 수 있습니다.`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` 프랑스어(프랑스) 문화권을 지정합니다.

#### Q: .NET용 Aspose.Words에서 자동 필드 업데이트를 비활성화할 수 있습니까?

 A: 예, .NET용 Aspose.Words에서 자동 필드 업데이트를 비활성화할 수 있습니다. 당신은 사용할 수 있습니다`Document.FieldOptions.UpdateFields` 속성을 설정하고`false` 필드가 자동 업데이트되는 것을 방지합니다. 이를 통해 필요에 따라 필드 업데이트를 수동으로 제어할 수 있습니다.

#### Q: .NET용 Aspose.Words에서 문서 필드를 수동으로 업데이트하려면 어떻게 해야 합니까?

 A: Aspose.Words for .NET에서 문서의 필드를 수동으로 업데이트하려면 다음을 사용할 수 있습니다.`Field.Update` 각 분야에 대해 개별적으로 방법을 제공합니다. 예를 들어 다음을 사용할 수 있습니다.`field.Update()` 특정 필드를 업데이트합니다.