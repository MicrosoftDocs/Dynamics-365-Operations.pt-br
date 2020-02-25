---
title: Integração de dados quase em tempo real com o Common Data Service
description: Este tópico fornece uma visão geral da integração entre o Finance and Operations e o Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019642"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Integração de dados quase em tempo real com o Common Data Service

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

No mundo digital atual, os ecossistemas comerciais usam os aplicativos do Microsoft Dynamics 365 como um todo. Como os dados de dispositivos de contatos, clientes, operações e da Internet das Coisas (IoT) fluem para uma origem, há uma oportunidade de loops de comentários digitais. Para obter essa experiência, a integração entre os aplicativos do Finance and Operations e outros aplicativos do Dynamics 365 é essencial. Alguns aplicativos são desenvolvidos com base no Common Data Service. A integração entre dados de aplicativos do Finance and Operations com o Common Data Service permite que outros aplicativos se comuniquem de maneira coerente e fluente com o Finance and Operations.

Os aplicativos do Finance and Operations e o Common Data Service oferecem sincronização de dados quase em tempo real entre aplicativos do Finance and Operations e outros aplicativos do Dynamics 365 por meio de uma estrutura de gravação dupla. A cobertura é ampla e abrange 28 áreas de superfície do aplicativo. A meta é oferecer ao usuário uma experiência "One Dynamics 365" por meio de fluxos de dados contínuos que conectem processos de negócios em aplicativos.

![Diagrama de visão geral da arquitetura](media/dual-write-overview.jpg)

As seguintes propostas de valor estão disponíveis:

+ [Hierarquia da organização no Common Data Service](organization-mapping.md)
+ [Conceito de empresa no Common Data Service](company-data.md)
+ [Cliente mestre integrado](customer-mapping.md)
+ [Razão integrado](ledger-mapping.md)
+ [Experiência unificada de produto](product-mapping.md)
+ [Fornecedor mestre integrado](vendor-mapping.md)
+ [Sites e depósitos integrados](sites-warehouses-mapping.md)
+ [Mestre de imposto integrado](tax-mapping.md)

## <a name="system-requirements"></a>Requisitos do sistema

Fluxos de dados assíncronos, bidirecionais quase em tempo real exigem as seguintes versões:

+ Microsoft Dynamics 365 for Finance and Operations versão 10.0.4 (julho de 2019) com atualização da plataforma 28 ou posterior
+ Microsoft Dynamics 365 for Customer Engagement, versão de plataforma 9.1 (4.2) ou posterior

## <a name="setup-instructions"></a>Instruções de configuração

Siga estas etapas para configurar a integração entre aplicativos do Finance and Operations e o Common Data Service.
    
1. Para a configuração do sistema de gravação dupla, consulte [guia passo a passo](https://aka.ms/dualwrite-docs) Anunciando a exibição de gravação dupla.
2. Baixe e instale a solução a partir do grupo [Integração com Fin Ops e CDS/CE por meio de gravação dupla](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096)Yammer. O pacote contém cinco soluções:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Siga a ordem de execução para [sincronizar dados iniciais de referência](initial-sync.md).
4. Se você encontrar problemas de sincronização de gravação dupla, consulte o [Guia de solução de problemas de integração de dados](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Você não pode executar a gravação dupla e o [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) lado a lado. Se você estiver executando a solução Prospect to cash, desinstale-a. Você também pode desativar os modelos de gravação dupla para clientes e fornecedores que fazem parte da solução Prospect to cash.
