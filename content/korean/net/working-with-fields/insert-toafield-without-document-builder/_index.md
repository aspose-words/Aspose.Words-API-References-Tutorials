---
title: 문서 작성기 없이 TOA 필드 삽입
linktitle: 문서 작성기 없이 TOA 필드 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Document Builder 없이 TOA 필드를 삽입하는 단계별 안내입니다.
type: docs
weight: 10
url: /ko/net/working-with-fields/insert-toafield-without-document-builder/
---

다음은 Aspose.Words for .NET의 "TOA 필드 삽입" 기능을 사용하는 아래 C# 소스 코드를 설명하는 단계별 가이드입니다. 원하는 결과를 얻으려면 각 단계를 주의 깊게 따르십시오.

## 1단계: 문서 디렉터리 설정

제공된 코드에서 문서의 디렉터리를 지정해야 합니다. "YOUR DOCUMENT DIRECTORY" 값을 문서 디렉토리에 대한 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 및 단락 만들기

새 문서를 만들고 단락을 초기화하는 것부터 시작합니다.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 3단계: TA 필드 삽입

FieldTA 클래스를 사용하여 TA 필드를 단락에 삽입합니다.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## 4단계: 문서 본문에 단락 추가

TA 필드가 포함된 단락을 문서 본문에 추가합니다.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 5단계: TOA 필드에 대한 단락 만들기

TOA 필드에 대한 새 단락을 만듭니다.

```csharp
para = new Paragraph(doc);
```

## 6단계: TOA 필드 삽입

FieldToa 클래스를 사용하여 TOA 필드를 단락에 삽입합니다.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## 7단계: 문서 본문에 단락 추가

TOA 필드가 포함된 단락을 문서 본문에 추가합니다.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 8단계: TOA 필드 업데이트

 마지막으로 우리는`Update()` TOA 필드를 업데이트하는 방법입니다.

```csharp
fieldToa.Update();
```

### .NET용 Aspose.Words를 사용하여 Document Builder 없이 TOA 필드 삽입을 위한 소스 코드 예

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// 다음과 같이 TA 및 TOA 필드를 삽입하려고 합니다.
// { TA \c 1 \l "값 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### FAQ

#### Q: Aspose.Words for .NET을 사용하여 Word 문서에 삽입된 TOA 필드의 모양을 사용자 정의하는 방법은 무엇입니까?

A: 삽입된 TOA 필드의 속성을 사용하여 모양을 사용자 정의할 수 있습니다.`FieldTOA` 서식 옵션을 지정하는 개체입니다.

#### Q: .NET용 Aspose.Words를 사용하여 단일 Word 문서에 여러 TOA 필드를 추가할 수 있습니까?

A: 예, Aspose.Words for .NET을 사용하여 단일 Word 문서에 여러 TOA 필드를 추가할 수 있습니다. 각 필드에 대해 삽입 단계를 반복하면 됩니다.

#### Q: Aspose.Words for .NET을 사용하여 TOA 필드가 Word 문서에 성공적으로 삽입되었는지 어떻게 확인할 수 있나요?

A: TOA 필드가 성공적으로 삽입되었는지 확인하려면 문서 내용을 탐색하고 TOA 필드 인스턴스를 검색하면 됩니다.

#### Q: DocumentBuilder를 사용하지 않고 TOA 필드를 삽입하면 .NET용 Aspose.Words를 사용하는 Word 문서 형식에 영향을 줍니까?

A: DocumentBuilder를 사용하지 않고 TOA 필드를 삽입해도 Word 문서의 형식에는 직접적인 영향이 없습니다. 그러나 TOA 필드 서식 옵션은 문서의 전체 서식에 영향을 줄 수 있습니다.