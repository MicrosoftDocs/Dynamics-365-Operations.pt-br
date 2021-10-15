---
title: Visão geral da integração com o Microsoft Dynamics 365 Field Service
description: Este tópico fornece uma visão geral da Integração com o Microsoft Dynamics 365 Field Service.
author: Henrikan
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 23661bca91ccd7b7a04c763e60cfca9a99d62bfa
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566446"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Visão geral da integração com o Microsoft Dynamics 365 Field Service

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

O Supply Chain Management permite a sincronização de processos de negócios entre o Dynamics 365 Supply Chain Management e o Dynamics 365 Field Service. Os cenários de integração são configurados usando modelos extensíveis do Integrador de dados e o Microsoft Dataverse para permitir a sincronização dos processos de negócios.
Os modelos padrão podem ser usados para criar projetos de integração personalizados, em que outras colunas e tabelas padrão e personalizadas podem ser mapeadas para ajustar a integração e para atender a necessidades de negócios específicas. 

A integração do Field Service se baseia na funcionalidade existente de pagamento à vista.

![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service.](./media/field-service-integration.png)

A primeira fase da integração entre o Field Service e o Supply Chain Management é centrada em permitir que ordens de serviço e contratos no Field Service sejam faturados no Supply Chain Management. O fluxo com suporte começa no Field Service, onde as informações das ordens de serviço são sincronizadas para o Supply Chain Management como ordens de venda. No Supply Chain Management, as ordens de venda são faturadas para gerar documentos de fatura. Além disso, as informações das faturas de contrato do Field Service são sincronizadas para o Supply Chain Management. O Integrador de dados do Microsoft Dynamics 365 sincroniza os dados usando projetos personalizáveis. Modelos padrão podem ser usados para criar projetos de integração personalizados em que outras colunas e tabelas padrão e personalizadas podem ser mapeadas para ajustar a integração e para atender a requisitos específicos.

A primeira fase da integração entre o Field Service e o Supply Chain Management permite a sincronização dos seguintes itens:

- [Sincronizar produtos no Supply Chain Management com produtos no Field Service](field-service-product.md)
- [Sincronizar ordens de serviço no Field Service com ordens de venda no Supply Chain Management](field-service-work-order.md)
- [Sincronizar faturas de contrato no Field Service com faturas de texto livre no Supply Chain Management](field-service-invoice.md)

Para ver um exemplo de como você pode sincronizar uma ordem de serviço entre o Field Service e o Supply Chain Management, assista ao vídeo do YouTube [Como sincronizar uma ordem de serviço com a integração do Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>Integração com o Field Service, incluindo o estoque e as informações do projeto

A funcionalidade adicional nesta segunda fase está centrada em fornecer aos técnicos de campo informações sobre o estoque do Supply Chain Management, permitindo que eles atualizem níveis de estoque e façam transferências de materiais. Além disso, as empresas que instalam ou oferecem mercadorias vendidas se beneficiarão de melhor de controle e visibilidade do processo completo de vendas e atendimento com a integração de projetos.

### <a name="functionality-includes-integration-of"></a>A funcionalidade inclui a integração de:
- Informações de depósito
- Informações de estoque disponíveis
- Transferências de estoque
- Ajustes de estoque
- Projetos do Supply Chain Management conectados a ordens de serviço do Dynamics 365 Field Service
- Ordens de serviço do Dynamics 365 Field Service com links para projetos do Supply Chain Management, aplicar esse número de projeto à ordem de venda para permitir o faturamento do projeto. 

![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service, incluindo informações de estoque e projeto.](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>O segunda fase da integração entre o Field Service e o Supply Chain Management permite a sincronização com os seguintes modelos:
- Depósitos (Supply Chain Management para Field Service) - Depósitos do Supply Chain Management para o Field Service [Consulta Avançada] 
- Estoque de Produtos (Supply Chain Management para Field Service) - Informações de nível de estoque do Supply Chain Management para o Field Service [Consulta Avançada] 
- Ajuste de Estoque (Field Service para Supply Chain Management) - Ajustes de estoque do Field Service para o Supply Chain Management [Consulta Avançada] 
- Transferências de Estoque (Field Service para Supply Chain Management) - Transferências de estoque do Field Service para o Supply Chain Management [Consulta Avançada] 
- Projetos (Supply Chain Management para Field Service) - Lista de projetos do Supply Chain Management para o Field Service 
- Ordens de serviço com projeto (Field Service para Supply Chain Management) - Ordens de serviço no Field Service para Ordens de venda no  Supply Chain Management, com suporte para o projeto [Consulta Avançada] 
- Produtos do Field Service com unidade de estoque (Supply Chain Management para Sales) - 'Produtos lançados comercializáveis' do Supply Chain Management para 'Produtos' do Sales para o Field Service, incluindo a unidade de estoque 

## <a name="system-requirements"></a>Requisitos do sistema

### <a name="system-requirements-for-supply-chain-management"></a>Requisitos de sistema do Supply Chain Management
A integração do Field Service é compatível com as seguintes versões:

- O Dynamics 365 for Finance and Operations versão 8.1.2 (dezembro de 2018) foi lançada em dezembro de 2018 e tem o número da compilação de aplicativo 8.1.195 com a atualização de plataforma 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Requisitos do sistema para o Field Service
Para usar a solução de integração do Field Service, você deve instalar os seguintes componentes:

- Field Service (versão 8.2.0.286) ou versão posterior no Dynamics 365 9.1.x - lançado em novembro de 2018
- Solução P2C (Prospect to Cash) para Dynamics 365, versão 1.15.0.1 ou uma versão posterior. A solução está disponível para download no [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Solução 'Integração, projeto e estoque do Field Service' para o Dynamics 365, versão 2.0.0.0 ou uma versão posterior. A solução está disponível para download no [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]