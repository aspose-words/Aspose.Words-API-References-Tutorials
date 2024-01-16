---
title: Zarządzanie podpisami cyfrowymi i autentycznością
linktitle: Zarządzanie podpisami cyfrowymi i autentycznością
second_title: Aspose.Words API do zarządzania dokumentami w języku Python
description: Dowiedz się, jak zarządzać podpisami cyfrowymi i zapewniać autentyczność dokumentów za pomocą Aspose.Words dla Pythona. Przewodnik krok po kroku z kodem źródłowym.
type: docs
weight: 17
url: /pl/python-net/document-combining-and-comparison/manage-digital-signatures/
---

## Wprowadzenie do podpisów cyfrowych

Podpisy cyfrowe służą jako elektroniczne odpowiedniki podpisów odręcznych. Umożliwiają weryfikację autentyczności, integralności i pochodzenia dokumentów elektronicznych. Kiedy dokument jest podpisany cyfrowo, na podstawie zawartości dokumentu generowany jest skrót kryptograficzny. Ten skrót jest następnie szyfrowany przy użyciu klucza prywatnego osoby podpisującej, tworząc podpis cyfrowy. Każdy, kto posiada odpowiedni klucz publiczny, może zweryfikować podpis i potwierdzić autentyczność dokumentu.

## Konfigurowanie Aspose.Words dla Pythona

Aby rozpocząć zarządzanie podpisami cyfrowymi za pomocą Aspose.Words dla Pythona, wykonaj następujące kroki:

1. Zainstaluj Aspose.Words: Możesz zainstalować Aspose.Words dla Pythona za pomocą pip i następującego polecenia:
   
   ```python
   pip install aspose-words
   ```

2. Zaimportuj wymagane moduły: Zaimportuj niezbędne moduły do skryptu Python:
   
   ```python
   import asposewords
   ```

## Ładowanie i uzyskiwanie dostępu do dokumentów

Przed dodaniem lub zweryfikowaniem podpisów cyfrowych należy załadować dokument za pomocą Aspose.Words:

```python
document = asposewords.Document("document.docx")
```

## Dodawanie podpisów cyfrowych do dokumentów

Aby dodać podpis cyfrowy do dokumentu, będziesz potrzebować certyfikatu cyfrowego:

```python
certificate = asposewords.Certificate("certificate.pfx", "password")
```

Teraz podpisz dokument:

```python
digital_signature = asposewords.DigitalSignature()
digital_signature.certificate = certificate
document.digital_signatures.add(digital_signature)
document.save("signed_document.docx")
```

## Weryfikacja podpisów cyfrowych

Zweryfikuj autentyczność podpisanego dokumentu za pomocą Aspose.Words:

```python
for signature in document.digital_signatures:
    if signature.is_valid:
        print("Signature is valid.")
    else:
        print("Signature is invalid.")
```

## Usuwanie podpisów cyfrowych

Aby usunąć podpis cyfrowy z dokumentu:

```python
document.digital_signatures.clear()
document.save("unsigned_document.docx")
```

## Zapewnienie autentyczności dokumentów

Podpisy cyfrowe zapewniają autentyczność dokumentu, potwierdzając jego źródło i integralność. Chronią przed manipulacją i nieuprawnionymi modyfikacjami.

## Dostosowywanie wyglądu podpisu cyfrowego

Możesz dostosować wygląd podpisów cyfrowych:

```python
digital_signature.options.comments = "Approved by John Doe"
digital_signature.options.sign_date_time = datetime.now()
```

## Wniosek

Zarządzanie podpisami cyfrowymi i zapewnianie autentyczności dokumentów ma kluczowe znaczenie w dzisiejszym cyfrowym krajobrazie. Aspose.Words dla Pythona upraszcza proces dodawania, weryfikowania i dostosowywania podpisów cyfrowych, umożliwiając programistom zwiększanie bezpieczeństwa i wiarygodności swoich dokumentów.

## Często zadawane pytania

### Jak działają podpisy cyfrowe?

Podpisy cyfrowe wykorzystują kryptografię do generowania unikalnego skrótu na podstawie zawartości dokumentu, zaszyfrowanego kluczem prywatnym osoby podpisującej.

### Czy można manipulować dokumentem podpisanym cyfrowo?

Nie, ingerencja w dokument podpisany cyfrowo unieważnia podpis, co wskazuje na potencjalne nieautoryzowane zmiany.

### Czy do jednego dokumentu można dodać wiele podpisów?

Tak, możesz dodać wiele podpisów cyfrowych do jednego dokumentu, każdy od innego podpisującego.

### Jakie typy certyfikatów są kompatybilne?

Aspose.Words obsługuje certyfikaty X.509, w tym pliki PFX, które są powszechnie używane w podpisach cyfrowych.

### Czy podpisy cyfrowe są ważne prawnie?

Tak, podpisy cyfrowe są prawnie ważne w wielu krajach i często są uważane za równoważne podpisom odręcznym.