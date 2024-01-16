---
title: Ole 패키지를 사용하여 Word에 Ole 개체 삽입
linktitle: Ole 패키지를 사용하여 Word에 Ole 개체 삽입
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 OLE 패키지가 포함된 OLE 개체를 문서에 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

다음은 .NET용 Aspose.Words를 사용하여 OLE 패키지와 함께 Word에 OLE 개체를 삽입하는 방법을 보여주는 C# 소스 코드를 설명하는 단계별 가이드입니다.

## 1단계: 필요한 참조 가져오기
시작하기 전에 Aspose.Words for .NET을 사용하는 데 필요한 참조를 프로젝트에 가져왔는지 확인하세요. 여기에는 Aspose.Words 라이브러리를 가져오고 소스 파일에 필요한 네임스페이스를 추가하는 작업이 포함됩니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## 2단계: 새 문서 및 문서 생성기 만들기
 이 단계에서는 다음을 사용하여 새 문서를 만듭니다.`Document` 클래스와 문서 작성기를 사용하는`DocumentBuilder` 수업.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: OLE 패키지를 사용하여 OLE 개체 삽입
 문서 생성기 사용`InsertOleObject` OLE 패키지가 포함된 OLE 개체를 문서에 삽입하는 방법입니다. 데이터 스트림, 개체 유형, 표시 옵션 및 기타 필요한 설정을 지정합니다.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## 4단계: 문서 저장
 문서의 내용을 사용하세요`Save` 문서를 파일로 저장하는 방법입니다.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### .NET용 Aspose.Words를 사용하여 OLE 패키지와 함께 OLE 개체를 삽입하기 위한 샘플 소스 코드

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

이것은 .NET용 Aspose.Words가 포함된 OLE 패키지와 함께 OLE 개체를 삽입하기 위한 완전한 코드 샘플입니다. 필요한 참조를 가져오고 이전에 설명한 단계에 따라 이 코드를 프로젝트에 통합하십시오.

## 결론

결론적으로 우리는 Aspose.Words for .NET을 사용하여 OLE 패키지를 사용하여 Word 문서에 OLE 개체를 삽입하는 단계별 가이드를 살펴보았습니다.

다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 OLE 패키지가 포함된 OLE 개체를 Word 문서에 성공적으로 삽입할 수 있습니다. 필요한 참조를 가져오고 지침을 주의 깊게 따라 원하는 결과를 얻으십시오.

### ole 패키지를 사용하여 단어로 ole 개체 삽입에 대한 FAQ

#### Q: Aspose.Words for .NET을 사용하려면 어떤 자격 증명을 가져와야 합니까?

A: .NET용 Aspose.Words를 사용하려면 다음 참조를 가져와야 합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Q: 새 문서와 문서 생성기를 만드는 방법은 무엇입니까?

 A: 다음을 사용하여 새 문서를 만들 수 있습니다.`Document` 클래스와 문서 작성기를 사용하는`DocumentBuilder` 클래스는 아래와 같습니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: OLE 패키지가 포함된 OLE 개체를 문서에 삽입하는 방법은 무엇입니까?

 답변:`InsertOleObject`문서 작성기의 메소드(`DocumentBuilder`) OLE 패키지가 포함된 OLE 개체를 문서에 삽입합니다. 데이터 스트림, 개체 유형, 표시 옵션 및 기타 필요한 설정을 지정합니다. 예는 다음과 같습니다.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Q: 문서를 어떻게 저장하나요?

 A: 문서를 사용하세요`Save` 문서를 파일로 저장하는 방법입니다. 예는 다음과 같습니다.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Q: Aspose.Words for .NET을 사용하여 OLE 패키지와 함께 OLE 개체를 삽입하는 완전한 예를 제공할 수 있습니까?

A: 다음은 .NET용 Aspose.Words를 사용하여 OLE 패키지와 함께 OLE 개체를 삽입하는 전체 샘플 코드입니다. 필요한 참조를 가져오고 이전에 설명한 단계에 따라 이 코드를 프로젝트에 통합해야 합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

이것으로 .NET용 Aspose.Words를 사용하여 OLE 패키지가 포함된 OLE 개체를 Word 문서에 삽입하는 방법에 대한 튜토리얼을 마칩니다. 필요한 참조를 자유롭게 가져오고 설명된 단계에 따라 이 코드를 프로젝트에 통합하세요. 추가 질문이 있으시면 언제든지 문의해 주세요.