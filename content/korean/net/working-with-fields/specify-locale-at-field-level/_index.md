---
title: 필드 수준에서 로케일 지정
linktitle: 필드 수준에서 로케일 지정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 필드 수준 지역화를 지정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fields/specify-locale-at-field-level/
---

다음은 .NET용 Aspose.Words 기능을 사용하여 필드 수준에서 지역화를 지정할 수 있는 다음 C# 소스 코드를 설명하는 단계별 가이드입니다. 이 코드를 사용하기 전에 프로젝트에 Aspose.Words 라이브러리를 포함했는지 확인하세요.

## 1단계: 문서 디렉터리 경로 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

편집된 문서가 저장될 문서 디렉토리의 올바른 경로를 지정하십시오.

## 2단계: 문서 생성기 만들기

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 여기서 우리는`DocumentBuilder` 문서에 필드를 추가할 수 있는 클래스입니다.

## 3단계: 특정 위치가 포함된 날짜 필드 삽입

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 문서 생성기를 사용하여 유형 필드를 삽입합니다.`FieldType.FieldDate` 문서에. 설정하여`LocaleId`재산`1049`, 이 필드에 대해 러시아어 현지화를 지정합니다.

## 4단계: 수정된 문서 저장

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

마지막으로 지정된 위치의 수정된 문서를 지정된 파일에 저장합니다.

### .NET용 Aspose.Words를 사용하여 필드 수준 지역화를 지정하기 위한 샘플 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

이는 .NET용 Aspose.Words를 사용하여 문서의 필드 수준에서 지역화를 지정하는 예제 소스 코드입니다. 이 코드를 사용하여 Word 문서의 특정 위치에 날짜 필드를 삽입할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.Words에서 필드 수준 로캘을 어떻게 지정할 수 있나요?

 A: .NET용 Aspose.Words의 필드 수준에서 로케일을 지정하려면 다음을 사용할 수 있습니다.`FieldOptions` 수업과 그`FieldLocale` 원하는 로케일을 설정하는 속성입니다. 예를 들어 다음을 사용할 수 있습니다.`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` 프랑스어(프랑스) 로케일을 지정합니다.

#### Q: Aspose.Words for .NET의 각 필드에 대해 다른 로케일을 지정할 수 있습니까?

 A: 예, Aspose.Words for .NET의 각 필드에 대해 다른 로케일을 지정할 수 있습니다. 당신은 사용할 수 있습니다`FieldOptions.FieldLocale` 특정 필드를 생성하거나 업데이트하기 전에 속성을 사용하여 다른 로케일을 할당하세요.

#### Q: .NET용 Aspose.Words의 필드에 현재 사용되는 로캘을 어떻게 얻을 수 있나요?

 A: .NET용 Aspose.Words의 필드에 대해 현재 사용되는 로케일을 얻으려면 해당 필드의 로케일을 사용할 수 있습니다.`Field.LocaleId` 재산. 이를 통해 필드와 연관된 로케일 식별자를 얻을 수 있습니다.