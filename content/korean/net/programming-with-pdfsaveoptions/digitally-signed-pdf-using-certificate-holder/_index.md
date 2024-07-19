---
title: 인증서 보유자를 사용하여 PDF에 디지털 서명 추가
linktitle: 인증서 보유자를 사용하여 PDF에 디지털 서명 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words와 함께 인증서 보유자를 사용하여 PDF에 디지털 서명을 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

이 튜토리얼에서는 Aspose.Words for .NET의 인증서 홀더를 사용하여 PDF에 디지털 서명을 추가하는 단계를 안내합니다. 디지털 서명은 PDF 문서에 보안 및 무결성 계층을 추가합니다. 아래 단계를 따르십시오.

## 1단계: 문서 만들기 및 콘텐츠 추가

Document 클래스의 인스턴스를 생성하여 시작합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 문서에 콘텐츠 추가

 그런 다음`DocumentBuilder`문서에 내용을 추가하려면 예를 들어, "서명된 PDF 테스트"라는 텍스트가 포함된 단락을 추가하려면`Writeln` 방법:

```csharp
builder.Writeln("Test Signed PDF.");
```

필요에 따라 다른 콘텐츠 항목을 추가할 수 있습니다.

## 3단계: PDF 저장 옵션 설정

PdfSaveOptions 클래스의 인스턴스를 만들고 디지털 서명 세부 정보를 지정합니다.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

인증서 및 관련 비밀번호의 올바른 경로를 지정하십시오. 서명 이유와 위치를 사용자 정의할 수도 있습니다.

## 4단계: 문서를 디지털 서명된 PDF로 저장

 사용`Save` 저장 옵션을 지정하여 문서를 PDF로 저장하는 방법:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

디지털 서명된 PDF를 저장하려면 올바른 경로를 지정해야 합니다.

다음 단계를 따르면 Aspose.Words for .NET을 사용하여 인증서로 디지털 서명된 PDF를 쉽게 만들 수 있습니다.

### .NET용 Aspose.Words를 사용하는 인증서 보유자를 사용하는 디지털 서명된 PDF의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하는 문서의 인증서 홀더를 사용하여 디지털 서명된 PDF에 대한 전체 소스 코드입니다.

```csharp

            // 문서 디렉터리의 경로입니다.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## 결론

이 튜토리얼에서는 .NET용 Aspose.Words가 포함된 인증서를 사용하여 PDF 문서에 디지털 서명을 추가하는 단계를 살펴보았습니다. 디지털 서명은 문서에 보안 및 무결성 계층을 추가하여 문서의 신뢰성을 보장하고 이후 수정 사항을 감지할 수 있게 해줍니다. 주어진 단계를 따르면 Aspose.Words for .NET이 포함된 인증서를 사용하여 디지털 서명된 PDF를 쉽게 만들 수 있습니다.

### 자주 묻는 질문

#### Q: 디지털 서명이란 무엇이며 PDF 문서에서 디지털 서명이 중요한 이유는 무엇입니까?
답변: 디지털 서명은 PDF 파일과 같은 전자 문서의 신뢰성, 무결성 및 부인 방지를 보장하는 데 도움이 되는 보안 기술입니다. 디지털 인증서를 사용하여 문서에 보안 계층을 추가합니다. 이는 작성자의 신원을 확인하고 콘텐츠에 대한 후속 변경 사항을 감지하는 데 도움이 됩니다.

#### Q: Aspose.Words for .NET 인증서를 사용하여 PDF 문서에 디지털 서명을 추가하려면 어떻게 해야 합니까?
A: .NET용 Aspose.Words가 포함된 인증서를 사용하여 PDF 문서에 디지털 서명을 추가하려면 다음 단계를 따르세요.

 인스턴스를 생성합니다.`Document` 문서를 표현하는 클래스입니다.

 사용`DocumentBuilder` 문서에 원하는 내용을 추가하는 클래스입니다.

 인스턴스를 생성합니다.`PdfSaveOptions` 클래스를 사용하여 디지털 서명 세부 정보를 지정합니다.`PdfDigitalSignatureDetails` 수업. 인증서 경로(`CertificateHolder.Create`), 관련 비밀번호, 서명 이유 및 위치.

 사용`Save` 저장 옵션을 지정하여 문서를 PDF 형식으로 저장하는 방법입니다.

#### Q: PDF 문서에 디지털 서명을 추가하기 위한 인증서를 얻으려면 어떻게 해야 합니까?
답변: PDF 문서에 디지털 서명을 추가하기 위한 인증서를 얻으려면 일반적으로 인증 기관(CA)이나 신뢰 서비스 제공업체에 문의하세요. 이러한 기관은 귀하의 신원을 확인하고 요청을 확인한 후 디지털 인증서를 발급합니다. 인증서를 얻은 후에는 응용 프로그램에서 이를 사용하여 PDF 문서에 디지털 서명을 추가할 수 있습니다.

#### Q: 디지털 서명의 사유, 위치 등 세부 사항을 맞춤 설정할 수 있나요?
 A: 예, 서명 이유와 위치를 지정하여 디지털 서명 세부 사항을 사용자 정의할 수 있습니다. 제공된 예제 코드에서`reason`그리고`location` 생성 시 매개변수`PdfDigitalSignatureDetails` 물체. PDF 문서의 서명 이유와 위치를 반영하려면 각 매개변수에 적절한 정보를 제공해야 합니다.