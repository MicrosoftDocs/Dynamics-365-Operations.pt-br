---
title: Visão geral de canais
description: Este tópico apresenta uma visão geral dos canais no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e060fe2a578296f079653244ed4d5676313e5ea8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963051"
---
# <a name="channels-overview"></a>Visão geral de canais


[!include [banner](includes/banner.md)]

Este tópico apresenta uma visão geral dos canais no Microsoft Dynamics 365 Commerce. Inclui informações sobre as tarefas que devem ser concluídas antes e depois de você configurar cada canal.

## <a name="types-of-channels"></a>Tipos de canais

O Dynamics 365 Commerce oferece suporte a três diferentes tipos de canal: varejo, call center e online.

### <a name="retail-channels"></a>Canais de varejo

Os canais de varejo representam as lojas físicas padrão. Cada loja pode ter seus próprios terminais de ponto de venda (PDV), contas de receita e despesa e equipe. 

### <a name="call-center-channels"></a>Canais de call center

Os canais de call center representam o gerenciamento de clientes e de ordens do call center.

### <a name="online-channels"></a>Canais online

Os canais online representam as lojas de comércio eletrônico online. Depois que um canal online é criado, um site deve ser criado usando a ferramenta Assistente para Criação de Sites do Microsoft Dynamics 365 Commerce ou outra solução de comércio eletrônico de terceiros.

## <a name="channel-setup-basics"></a>Noções básicas da configuração de canal

A configuração de canal é realizada na ferramenta Commerce. Cada canal pode ter seus próprios métodos de pagamento, grupos de preços, hierarquias de produtos, classificações e conjuntos de produtos. Depois de criar um canal, você atribui os produtos que deseja que a loja contenha e venda. Cada tipo de canal tem um conjunto exclusivo de recursos que podem precisar ser configurados. Por exemplo, um canal de varejo precisa de funcionários, terminais e clientes atribuídos. Depois que um novo canal é criado, ele precisa ser atribuído a uma hierarquia da organização.

## <a name="channel-setup-prerequisites"></a>Pré-requisitos de configuração de canal

Para configurar um canal, você deve concluir algumas tarefas de pré-requisito com base no tipo de canal. Para obter mais informações, consulte [Pré-requisitos de configuração de canal](channels-prerequisites.md).

## <a name="set-up-a-channel"></a>Configurar um canal

Depois de concluir as tarefas de pré-requisito, para obter mais instruções de configuração, use os links a seguir.

- [Configurar um canal de varejo](channel-setup-retail.md)
- [Configurar um canal de call center](channel-setup-callcenter.md)
- [Configurar um canal online](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a>Recursos adicionais

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Configurar um canal de varejo](channel-setup-retail.md)
    
[Configurar um canal online](channel-setup-online.md)

[Configurar um canal de call center](channel-setup-callcenter.md)

[Configurar hierarquias da organização](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]