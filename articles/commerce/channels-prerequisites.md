---
title: Pré-requisitos de configuração de canal
description: Este artigo apresenta uma visão geral dos pré-requisitos de configuração de canais no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 98ca2dc4691534853467c1680890199d08bc4e79
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282259"
---
# <a name="channel-setup-prerequisites"></a>Pré-requisitos de configuração de canal

[!include [banner](includes/banner.md)]

Este artigo apresenta uma visão geral dos pré-requisitos de configuração de canal no Microsoft Dynamics 365 Commerce.

Para que um canal do Dynamics 365 Commerce possa ser criado, é preciso concluir várias tarefas de pré-requisito. As listas de tarefas de pré-requisito a seguir estão organizadas por tipo de canal.

> [!NOTE]
> Uma parte da documentação ainda está sendo escrita, e os links serão atualizados quando novos conteúdos forem publicados.

## <a name="initialization"></a>Inicialização

- [Inicializar dados semente](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Pré-requisitos globais necessários para todos os tipos de canal

- [Definir e configurar sua estrutura de entidade legal](channels-legal-entities.md) 
- [Configurar sua hierarquia organizacional](channels-org-hierarchies.md)
- [Configurar um depósito](channels-setup-warehouse.md)
- [Configurar imposto](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [Configurar um perfil de notificação por email](email-notification-profiles.md)
- [Configurar sequências numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [Configurar um padrão e um catálogo de endereços padrão](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Pré-requisitos do canal de varejo

- [Códigos informativos e grupos de códigos informativos](info-codes-retail.md)
- [Configurar um perfil de funcionalidade de varejo](retail-functionality-profile.md)
- [Configurar um catálogo de endereços de funcionário](new-address-book.md)
- [Configurar um layout de tela](pos-screen-layouts.md)
- [Configurar uma estação de hardware](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a>Pré-requisitos do canal de Call Center

- Parâmetros de call center
- [Formas de pagamento para ordens e reembolsos de call center](work-with-payments.md)
- [Modos de entrega e encargos de call center](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a>Pré-requisitos do canal online

- [Criar um perfil de funcionalidade online](online-functionality-profile.md)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de canais](channels-overview.md)

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Configurar hierarquias da organização](channels-org-hierarchies.md)

[Criar entidades legais](channels-legal-entities.md)

[Configurar um canal de varejo](channel-setup-retail.md)
    
[Configurar um canal online](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
