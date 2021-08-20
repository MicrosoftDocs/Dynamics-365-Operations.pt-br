---
title: Registro adiado de documentos NFC-e emitidos no modo de contingência offline
description: Este tópico dá uma visão geral da funcionalidade para o registro adiado de documentos NFC-e que são emitidos no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce no modo de contingência.
author: akviklis
manager: annbe
ms.date: 06/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: akviklis
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4fbe255a435a83f4f1e28e0bc21b788125b5a6e54e15d4c27d342118e3ea44c9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751581"
---
# <a name="postponed-registration-of-nfc-e-documents-issued-in-offline-contingency-mode"></a>Registro adiado de documentos NFC-e emitidos no modo de contingência offline

[!include[banner](../includes/banner.md)]

Este tópico dá uma visão geral da funcionalidade para o registro adiado de documentos NFC-e (Nota Fiscal do Consumidor eletrônica) que são emitidos no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce no modo de contingência.

O modo de contingência offline NFC-e deve ser usado quando a conexão à Internet de uma loja não estiver disponível, ou quando o serviço de autorização da SEFAZ (Secretaria de Estado de Fazenda) estiver desativado. No modo de contingência offline, o PDV gera documentos NFC-e localmente. Esses documentos são encaminhados à SEFAZ posteriormente.

Todos os documentos NFC-e que são emitidos por meio de terminais PDV podem ser vistos na página **Visualizar mensagem XML** na sede do Commerce após a execução dos P-jobs e a publicação da declaração de varejo. Depois disso, os documentos NFC-e que foram emitidos no PDV no modo de contingência offline podem ser enviados para autorização por meio da sede do Commerce.

## <a name="view-fiscal-document-details"></a>Veja os detalhes do documento fiscal

Para ver um documento NFC-e na sede do Commerce, acesse **Varejo e Comércio \> Consultas e relatórios \> Todos os documentos fiscais**. A página **Todos os documentos fiscais** mostra o mesmo formato que é mostrado quando você visualiza um documento fiscal NF-e modelo 55. Isso inclui o cabeçalho, linhas e todos os atributos. Para obter mais informações, consulte [Documentos fiscais e estrutura de documentos fiscais para o Brasil](../../finance/localizations/latam-bra-fiscal-documents-fiscal-document-framework.md).

> [!NOTE]
> - Por padrão, se você abrir a página **Todos os documentos fiscais** na sede do Commerce, ele lista apenas os documentos fiscais NFC-e modelo 65. Para visualizar os retornos que possuem documentos fiscais NFC-e modelo 55, você deve alterar os critérios do filtro. No entanto, se você abrir a página **Todos os documentos fiscais** no módulo **Contabilidade**, ele listará todos os modelos de documentos fiscais de entrada e saída, incluindo o modelo 55 e o modelo 65.
> - Se o documento NFC-e tiver sido emitido e autorizado no PDV, seu status será mostrado como **Aprovado**. Se o documento NFC-e for emitido no modo de contingência offline, seu status será mostrado como **Criado**, **Rejeitado** ou **RejectedNoFix**.

## <a name="authorize-nfc-e-documents-that-were-issued-in-offline-contingency-mode"></a>Autorizar documentos NFC-e que foram emitidos no modo de contingência offline

Para autorizar um documento NFC-e que foi emitido no modo de contingência offline, siga estas etapas na sede do Commerce.

1. Siga uma destas etapas:

    - Acesse **Contas a receber \> Documentos fiscais \> Documentos fiscais eletrônicos \> Processo de exportação/importação de NF-e**.
    - Se você estiver usando o [Complemento de faturamento eletrônico para o Brasil](../../finance/localizations/e-invoicing-bra-get-started.md), Acesse **Varejo e Commerce \> Varejo e IT do Commerce \> Publicação no PDV \> Exportar documentos NFC-e**.

1. Após a conclusão do processo de exportação, revise o status de autorização da NFC-e acessando **Varejo e Commerce \> Consultas e relatórios \> Todos os documentos fiscais**. Para as vendas autorizadas pela autoridade fiscal do estado, o campo **Status** será definido como **Aprovado**.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil](latam-bra-nfce.md)

[Gerenciar informações do cliente no PDV para o Brasil](latam-bra-customer-information.md)

[Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil](latam-bra-nfce-cancel-return.md)

[Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce](latam-bra-retail-statements.md)
