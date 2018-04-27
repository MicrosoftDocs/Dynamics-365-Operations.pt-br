---
title: "Integração com o Microsoft Dynamics 365 for Field Service"
description: "Este tópico fornece uma visão geral da integração com o Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: d32a4e376770fc73c79b94924d5ae062d201d84a
ms.openlocfilehash: a224962152e80293f6cf3425dea74d73a283e31a
ms.contentlocale: pt-br
ms.lasthandoff: 04/12/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integração com o Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

O Microsoft Dynamics 365 for Finance and Operations permite a sincronização dos processos comerciais entre o Finance and Operations e o Microsoft Dynamics 365 for Field Service. Os cenários de integração são configurados usando modelos extensíveis do Integrador de dados e o CDS (Common Data Service) para habilitar a sincronização dos processos comerciais.

[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

A primeira fase da integração entre o Field Service e o Finance and Operations é centrada em habilitar ordens de trabalho e contratos no Field Service para serem faturados no Finance and Operations. O fluxo com suporte começa no Field Service, onde as informações das ordens de trabalho são sincronizadas com o Finance and Operations como ordens de venda. No Finance and Operations, as ordens de venda são faturadas para gerar os documentos de fatura. Além disso, as informações das faturas de contrato do Field Service são sincronizadas com o Finance and Operations. O Integrador de dados do Microsoft Dynamics 365 sincroniza os dados usando projetos personalizáveis. Modelos padrão podem ser usados para criar projetos de integração personalizados em que o padrão adicional e os campos personalizadas, além das entidades, podem ser mapeados para ajustar a integração e para atender a requisitos específicos.

O primeira fase da integração entre o Field Service e o Finance and Operations permite a sincronização dos seguintes itens:

- [Produto no Finance and Operations com produtos no Field Service que incluam informações de Tipo de Produto](field-service-product.md)
- [Ordens de trabalho no Field Service com ordens de venda no Finance and Operations](field-service-work-order.md)
- [Faturas no Field Service com faturas de texto livre no Finance and Operations](field-service-invoice.md)

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos de sistema para Finance and Operations
A integração do Field Service é compatível com as seguintes versões:

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Versão 8.0 do Dynamics 365 for Finance and Operations (abril de 2018) ou posterior

- A versão 8.0 do Dynamics 365 for Finance and Operations (abril de 2018) foi liberada em abril de 2018 e tem o número de compilação do aplicativo 8.0.30.8020 com a atualização 15 da plataforma (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>Requisitos do sistema para o Field Service
Para usar a solução de integração do Field Service, você deve instalar os seguintes componentes:

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 ou posterior

- Dynamics 365 for Field Service, versão 1612 (9.0.1.733) (DB 9.0.1.733) online ou uma versão posterior.
- Solução P2C (Prospect to Cash) para Dynamics 365, versão 1.15.0.1 ou uma versão posterior. A solução está disponível para download no [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Integração do Field Service para Dynamics 365, versão 1.0.0.0 ou uma versão posterior. A solução está disponível para download no AppSource. **(LIBERAÇÃO PENDENTE)**

