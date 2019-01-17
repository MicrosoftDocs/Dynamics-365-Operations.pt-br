---
title: "Integração com o Microsoft Dynamics 365 for Field Service"
description: "Este tópico fornece uma visão geral da integração com o Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 08/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 95031534c43dc0578e258bc3e5376c429d72b0ab
ms.openlocfilehash: 673ab2a101cee1a3dbbb1249f582d959cecc7f7f
ms.contentlocale: pt-br
ms.lasthandoff: 12/23/2018

---

# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integração com o Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

O Microsoft Dynamics 365 for Finance and Operations permite a sincronização dos processos comerciais entre o Finance and Operations e o Microsoft Dynamics 365 for Field Service. Os cenários de integração são configurados usando modelos extensíveis do Integrador de dados e o CDS (Common Data Service) para habilitar a sincronização dos processos comerciais.
Os modelos padrão podem ser usados para criar projetos de integração personalizados, em que o padrão adicional e os campos e as entidades personalizados podem ser mapeados para ajustar a integração e para atender a necessidades de negócios específicas. 

A integração do Field Service se baseia na funcionalidade existente de pagamento à vista.

![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/field-service-integration.png)

A primeira fase da integração entre o Field Service e o Finance and Operations é centrada em habilitar ordens de trabalho e contratos no Field Service para serem faturados no Finance and Operations. O fluxo com suporte começa no Field Service, onde as informações das ordens de trabalho são sincronizadas com o Finance and Operations como ordens de venda. No Finance and Operations, as ordens de venda são faturadas para gerar os documentos de fatura. Além disso, as informações das faturas de contrato do Field Service são sincronizadas com o Finance and Operations. O Integrador de dados do Microsoft Dynamics 365 sincroniza os dados usando projetos personalizáveis. Modelos padrão podem ser usados para criar projetos de integração personalizados em que o padrão adicional e os campos personalizadas, além das entidades, podem ser mapeados para ajustar a integração e para atender a requisitos específicos.

O primeira fase da integração entre o Field Service e o Finance and Operations permite a sincronização dos seguintes itens:

- [Produto no Finance and Operations com produtos no Field Service que incluam informações de Tipo de Produto](field-service-product.md)
- [Ordens de trabalho no Field Service com ordens de venda no Finance and Operations](field-service-work-order.md)
- [Faturas no Field Service com faturas de texto livre no Finance and Operations](field-service-invoice.md)

Para ver um exemplo de como você pode sincronizar uma ordem de trabalho entre o Field Service e Finance and Operations, assista a um vídeo do YouTube [Como sincronizar uma ordem de trabalho com a integração do Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos de sistema para Finance and Operations
A integração do Field Service é compatível com as seguintes versões:

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Versão 8.0 do Dynamics 365 for Finance and Operations (abril de 2018) ou posterior

- A versão 8.0 do Dynamics 365 for Finance and Operations (abril de 2018) foi liberada em abril de 2018 e tem o número de compilação do aplicativo 8.0.30.8020 com a atualização 15 da plataforma (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>Requisitos do sistema para o Field Service
Para usar a solução de integração do Field Service, você deve instalar os seguintes componentes:

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 ou posterior

- Dynamics 365 for Field Service, versão 1612 (9.0.1.733) (DB 9.0.1.733) online ou uma versão posterior.
- Solução P2C (Prospect to Cash) para Dynamics 365, versão 1.15.0.1 ou uma versão posterior. A solução está disponível para download no [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Integração do Field Service para Dynamics 365, versão 1.0.0.0 ou uma versão posterior. A solução está disponível para download no [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegration).

# <a name="integration-with-microsoft-dynamics-365-for-field-service-including-inventory-and-project-information"></a>Integração com o Microsoft Dynamics 365 for Field Service, incluindo informações de estoque e projeto

A funcionalidade adicional nesta segunda fase está centrada em fornecer aos técnicos de campo informações sobre o estoque do Finance and Operations, permitindo que eles atualizem níveis de estoque e façam transferências de materiais. Além disso, as empresas que instalam ou oferecem mercadorias vendidas se beneficiarão de melhor de controle e visibilidade do processo completo de vendas e atendimento com a integração de projetos.

### <a name="functionality-includes-integration-of"></a>A funcionalidade inclui a integração de:
- Informações de depósito
- Informações de estoque disponíveis
- Transferências de estoque
- Ajustes de estoque
- Projetos do Dynamics 365 for Finance and Operations conectados a ordens de serviço do Dynamics 365 for Field Service
- As ordens de serviço do Dynamics 365 for Field Service com link para projetos do Dynamics 365 for Finance and Operations aplicam este número de projeto a ordem de vendas do Dynamics 365 for Finance and Operations para permitir o faturamento do projeto. 

![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-finance-and-operations-enables-synchronization-with-the-following-templates"></a>O segunda fase da integração entre o Field Service e o Finance and Operations permite a sincronização com os seguintes modelos:
- Depósitos (Fin and Ops para Field Service) - depósitos do Finance and Operations para o Field Service [Consulta Avançada] 
- Estoque de Produtos (Fin and Ops para Field Service) - informações em nível de estoque do Finance and Operations para o Field Service [Consulta Avançada] 
- Ajuste de Estoque (Field Service para Fin and Ops) - ajustes de estoque do Field Service para o Finance and Operations [Consulta Avançada] 
- Transferências de Estoque (Field Service para Fin and Ops) - transferências de estoque do Field Service para o Finance and Operations [Consulta Avançada] 
- Projetos (Fin and Ops para Field Service) - lista de projetos do Finance and Operations para o Field Service 
- Ordens de trabalho com projetos (Field Service para Fin and Ops) - ordens de trabalho no Field Service para ordens de vendas no Finance and Operations, com suporte para o projeto [Consulta Avançada] 
- Produtos do Field Service com unidade de estoque (Fin and Ops para Sales) - 'produtos lançados comercializáveis' do Finance and Operations para o Field Service, incluindo a unidade de estoque 

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos de sistema para Finance and Operations
A integração do Field Service é compatível com as seguintes versões:

- O Dynamics 365 for Finance and Operations versão 8.1.2 (dezembro de 2019) será liberado em dezembro de 2019 e tem um número de compilação do aplicativo 8.1.195 com com a atualização 22 da plataforma (7.0.5095). 

## <a name="system-requirements-for-field-service"></a>Requisitos do sistema para o Field Service
Para usar a solução de integração do Field Service, você deve instalar os seguintes componentes:

- Field Service for Dynamics 365 (versão 8.2.0.286) ou versão mais recente no Dynamics 365 9.1.x - liberado em novembro de 2018
- Solução P2C (Prospect to Cash) para Dynamics 365, versão 1.15.0.1 ou uma versão posterior. A solução está disponível para download no [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Solução 'Integração, projeto e estoque do Field Service' para o Dynamics 365, versão 2.0.0.0 ou uma versão posterior. A solução está disponível para download no [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).

