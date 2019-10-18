---
title: Integração de dados quase em tempo real entre o Finance and Operations e o Common Data Service
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
ms.openlocfilehash: b7d9e6be6fb2fef85bcf1182f89b8e370abea3d6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184476"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Integração de dados quase em tempo real com o Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

No mundo digital atual, os ecossistemas comerciais usam os aplicativos do Microsoft Dynamics 365 como um todo. Como os dados de dispositivos de contatos, clientes, operações e da Internet das Coisas (IoT) fluem para uma origem, há uma oportunidade de loops de comentários digitais. Para obter essa experiência, é essencial a integração entre os aplicativos do Finance and Operations e outros aplicativos do Dynamics 365. Alguns aplicativos são desenvolvidos com base no Common Data Service. A integração entre dados de aplicativos do Finance and Operations com o Common Data Service permite que outros aplicativos se comuniquem de maneira coerente e fluente com o Finance and Operations.

Os aplicativos do Finance and Operations e o Common Data Service oferecem sincronização de dados quase em tempo real entre aplicativos do Finance and Operations e outros aplicativos do Dynamics 365 por meio de uma estrutura de gravação dupla. A cobertura é ampla e abrange 28 áreas de superfície do aplicativo. A meta é oferecer ao usuário uma experiência "One Dynamics 365" por meio de fluxos de dados contínuos que conectem processos de negócios em aplicativos.

![Diagrama de visão geral da arquitetura](media/dual-write-overview.jpg)

As seguintes propostas de valor estão disponíveis para clientes:

+ [Hierarquia da organização no Common Data Service](dual-write-organization.md)
+ [Conceito de empresa no Common Data Service](dual-write-company.md)
+ [Cliente mestre integrado](dual-write-customer.md)
+ [Fornecedor mestre integrado](dual-write-vendor.md)
+ Produto mestre unificado

## <a name="system-requirements"></a>Requisitos do sistema

Fluxos de dados assíncronos, bidirecionais quase em tempo real exigem as seguintes versões:

+ Microsoft Dynamics 365 for Finance and Operations versão 10.0.4 (julho de 2019) com atualização da plataforma 28 ou posterior
+ Microsoft Dynamics 365 for Customer Engagement, versão de plataforma 9.1 (4.2) ou posterior

## <a name="setup-instructions"></a>Instruções de configuração

Siga estas etapas para configurar a integração entre aplicativos do Finance and Operations e o Common Data Service.
    
1. Para a configuração do sistema de gravação dupla, consulte [guia passo a passo](https://aka.ms/dualwrite-docs) Anunciando a exibição de gravação dupla.
2. Baixe e instale a solução do grupo [Finance and Operations, Common Data Service e Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer. O pacote contém cinco soluções:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Siga a ordem de execução para [sincronizar dados iniciais de referência](dual-write-initial.md).
4. Se você encontrar problemas de sincronização de gravação dupla, consulte o [Guia de solução de problemas de integração de dados](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Você não pode executar a gravação dupla e o [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) lado a lado. Se você estiver executando a solução Prospect to cash, desinstale-a. Você também pode desativar os modelos de gravação dupla para clientes e fornecedores que fazem parte da solução Prospect to cash.
