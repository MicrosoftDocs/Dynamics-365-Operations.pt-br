---
title: Espaços reservados em textos da nota fiscal do Brasil
description: Os espaços reservados de texto de nota fiscal são marcas predefinidas que representam valores específicos. Você poderá incluir os espaços reservados no campo <strong>Texto </strong>da página <strong>Modelos de textos da nota fiscal </strong>quando você criar um modelo de textos da nota fiscal.
author: AdamTrukawka
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 268684
ms.openlocfilehash: 9964bb558a947ca3ed3964d9b215db8c0a518369
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281622"
---
# <a name="fiscal-document-text-placeholders-for-brazil"></a>Espaços reservados em textos da nota fiscal do Brasil

[!include [banner](../includes/banner.md)]

Os espaços reservados de texto de nota fiscal são marcas predefinidas que representam valores específicos. Você poderá incluir os espaços reservados no campo <strong>Texto </strong>da página <strong>Modelos de textos da nota fiscal </strong>quando você criar um modelo de textos da nota fiscal.

Você também pode incluir espaços reservados no campo **Observação** na página **Textos da nota fiscal** quando anexar um texto de nota fiscal a uma ordem de venda, ordem de compra ou fatura de texto livre. Quando você lança uma ordem de venda, ordem de compra ou fatura de texto livre que tem um texto de nota fiscal que inclui espaços reservados, os espaços reservados são substituídos pelos valores nas marcas predefinidas.

As tabelas a seguir contêm as marcas predefinidas que têm suporte para texto da nota fiscal e seu valor.

## <a name="tags-that-support-fiscal-document-text-for-referenced-processes"></a>As marcas que têm suporte para texto da nota fiscal para processos mencionados

| Marca predefinida                  | Alíquota                                 |
|---------------------------------|---------------------------------------|
| %RefProcess\_TaxAuthorityName   | O nome da autoridade do imposto.        |
| %RefProcess\_TaxAuthorityAgency | A agência da autoridade do imposto.      |
| %RefProcess\_RefProcessNumber   | O número do processo mencionado. |

## <a name="tag-that-supports-fiscal-document-text-for-suframa"></a>A marca que tem suporte para texto da nota fiscal para SUFRAMA

| Marca predefinida       | Alíquota                        |
|----------------------|------------------------------|
| %Suframa\_CustNumber | O número de cliente da SUFRAMA. |

## <a name="tags-that-support-fiscal-document-text-for-taxes"></a>As marcas que têm suporte para texto de nota fiscal para impostos

| Marca predefinida | Alíquota                                                                                    |
|----------------|------------------------------------------------------------------------------------------|
| %ICMS          | O valor do ICMS (Imposto Sobre Circulação de Mercadorias e Serviços).                |
| %PIS           | O valor da contribuição do PIS (Programa de Integração Social).                             |
| %COFINS        | O valor da contribuição de COFINS (Contribuição para Financiamento da Seguridade Social). |
| %IPI           | O valor total do Imposto sobre Produtos Industrializados (IPI).                              |
| %IPI\_TaxValue | O valor do Imposto sobre Produtos Industrializados (IPI).                            |

## <a name="tags-that-support-fiscal-document-text-for-fiscal-references"></a>As marcas que têm suporte para texto da nota fiscal para referências fiscais

| Marca predefinida                  | Alíquota                                                                                                               |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------|
| %FiscalRef\_InvNoRef            | O número da fatura de referência.                                                                                |
| %FiscalRef\_InvSeriesRef        | A série da fatura de referência.                                                                                |
| %FiscalRef\_InvDateRef          | A data da fatura de referência.                                                                                  |
| %FiscalRef\_InvAccNameRef       | O nome da conta da fatura de referência.                                                                          |
| %FiscalRef\_InvAccAddressRef    | O endereço da fatura de referência.                                                                               |
| %FiscalRef\_InvAccIENumberRef   | A IE (Inscrição Estadual), ou número de inscrição do estado, da conta de fatura de referência.                        |
| %FiscalRef\_InvAccCNPJCPFNumRef | O CNPJ (Cadastro Nacional da Pessoa Jurídica), ou número de inscrição do contribuinte, da conta de fatura de referência. |

## <a name="tags-that-support-fiscal-document-text-that-involve-vendor-information"></a>As marcas que têm suporte para texto da nota fiscal que envolvem informações do fornecedor

| Marca predefinida     | Alíquota                                                                                                                              |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------|
| %Vendor\_Name      | O nome do fornecedor.                                                                                                            |
| %Vendor\_CNPJ\_CPF | O CNPJ (Cadastro Nacional da Pessoa Jurídica)/CPF (Cadastro de Pessoas Físicas), ou número de inscrição do contribuinte, do fornecedor. |
| %Vendor\_IE        | A IE do fornecedor.                                                                                                              |
| %Vendor\_Address   | O endereço do fornecedor.                                                                                                         |

## <a name="tags-that-support-fiscal-document-text-that-involve-customer-information"></a>Marcas que têm suporte para texto de nota fiscal que envolvem informações do cliente

| Marca predefinida       | Alíquota                         |
|----------------------|-------------------------------|
| %Customer\_Name      | O nome do cliente.     |
| %Customer\_CNPJ\_CPF | O CNPJ/CPF do cliente. |
| %Vendor\_IE          | A IE do cliente.       |
| %Vendor\_Address     | O endereço do cliente.  |

## <a name="tags-that-support-fiscal-document-text-for-withholding-taxes"></a>As marcas que têm suporte para texto da nota fiscal para impostos retidos na fonte

| Marca predefinida       | Alíquota                          |
|----------------------|--------------------------------|
| %TaxWithhold\_Code   | O código de imposto retido na fonte.      |
| %TaxWithhold\_Value  | A taxa de imposto retido na fonte.   |
| %TaxWithhold\_Amount | O valor do imposto retido na fonte. |

## <a name="tags-that-support-fiscal-document-text-for-imports"></a>As marcas que têm suporte para texto da nota fiscal para importações

| Marca predefinida | Alíquota                                                                    |
|----------------|--------------------------------------------------------------------------|
| %DI\_Number    | O identificador do documento da declaração de importação.                       |
| %DI\_Date      | A data que o documento da declaração de importação foi emitido.                |
| %ImportTax     | O valor do imposto sobre importação.                                                   |
| %Freight       | O valor de frete para a importação.                                       |
| %Insurance     | O valor de seguro para a importação.                                     |
| %Siscomex      | O valor de encargo para Siscomex (Sistema Integrado de Comércio Exterior). |
| %ExchRate      | A taxa de câmbio usada na importação.                            |

## <a name="tags-for-icmsdif-final-consumer"></a>As marcas para o consumo de ICMSDIF final

| Marca predefinida           | Alíquota                                                                          |
|--------------------------|--------------------------------------------------------------------------------|
| %DifICMS\_vBCUFDest      | Valor da base de imposto usado para o tipo de imposto ICMS-DIF.                                    |
| %DifICMS\_pICMSUFDest    | Valor do imposto do estado federal do destinatário.                                         |
| %DifICMS\_pICMSInter     | Valor do imposto para a transação interestadual.                                          |
| %DifICMS\_pICMSInterPart | Porcentagem definida para estado federal do destinatário (baseado no ano fiscal do documento). |
| %DifICMS\_vICMSUFDest    | Valor do imposto do estado do destinatário.                                                |
| %DifICMS\_vICMSUFRemet   | Valor do imposto no estado de emissor.                                                   |

## <a name="tags-for-approximated-tax-values"></a>Marcas para valores de imposto aproximados
| Marca predefinida          | Alíquota                                                            |
|-------------------------|------------------------------------------------------------------|
| %ApproximateTaxValue    | A taxa de imposto aproximado.                                       |
| %ApproximateTaxAmount   | O valor da taxa de imposto aproximado.                                     |
| %ApproximateValueSource | O nome da origem da taxa de imposto aproximado.              |

## <a name="tags-for-fci-number"></a>Marcas para número de FCI
| Marca predefinida          | Alíquota                                                            |
|-------------------------|------------------------------------------------------------------|
| %FCINumber              | O número da Ficha de Controle de Importação (FCI).            |

## <a name="tags-for-poverty-funds-over-icms-icms-fcp"></a>Marcas para fundos para pobreza sobre o ICMS (ICMS FCP)
| Marca predefinida          | Alíquota                                                                 |
|-------------------------|-----------------------------------------------------------------------|
| %FCP\_amount            | O valor do fundo para pobreza calculado sobre o valor do ICMS.       |
| %FCP\_baseAmount        | O valor base do ICMS para cálculo do valor do fundo para pobreza.      |
| %FCP\_percentage        | A taxa de fundo para pobreza sobre o valor do ICMS.                           |


## <a name="tags-for-poverty-funds-over-icms-st-icms-st-fcp"></a>Marcas para fundos para pobreza sobre o ICMS-ST (ICMS-ST FCP)
| Marca predefinida          | Alíquota                                                                 |
|-------------------------|-----------------------------------------------------------------------|
| %FCP\_ST\_amount        | O valor do fundo para pobreza calculado sobre o valor do ICMS-ST.    |
| %FCP\_ST\_baseAmount    | O valor base do ICMS-ST para cálculo do valor do fundo para pobreza.   |
| %FCP\_ST\_percentage    | A taxa de fundo para pobreza sobre o valor do ICMS-ST.                         |


## <a name="tags-for-presumed-tax-icms-st"></a>Marcas para imposto presumido (ICMS-ST)
| Marca predefinida                                | Alíquota                                                       |
|-----------------------------------------------|-------------------------------------------------------------|
| %Presumed\_tax\_rate                          | A taxa de imposto presumido ICMS-ST.                               |
| %Presumed\_tax\_base\_amount                  | O valor base para valor do imposto presumido ICMS-ST.             |
| %Presumed\_per\_unit\_tax\_base\_amount       | O valor base para valor do imposto presumido ICMS-ST por unidade.    |
| %Presumed\_tax\_amount                        | O valor do imposto presumido ICMS-ST.                             |
| %Presumed\_per\_unit\_tax\_amount             | O valor do imposto presumido ICMS-ST por unidade.                    |
| %Presumed\_FCP\_tax\_rate                     | A taxa de imposto do fundo presumido para pobreza.                          |
| %Presumed\_FCP\_tax\_base\_amount             | O valor base do imposto do fundo presumido para pobreza.                   |
| %Presumed\_FCP\_per\_unit\_tax\_base\_amount  | O valor base do imposto do fundo presumido para pobreza por unidade.          |
| %Presumed\_FCP\_tax\_amount                   | O valor do fundo presumido para pobreza.                            |
| %Presumed\_FCP\_per\_unit\_tax\_amount        | O valor do fundo presumido para pobreza por unidade.                   |

## <a name="tags-for-presumed-tax-from-the-substitute"></a>Marcas para imposto presumido (do substituto)
| Marca predefinida                 | Alíquota                                                                |
|--------------------------------|----------------------------------------------------------------------|
| %Substituto\_ICMS\_tax\_amount | O valor do imposto presumido do ICMS do substituto do ICMS.                |
| %Substituto\_FCP\_tax\_amount  | O valor presumido do FCP do substituto do ICMS.                     |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
