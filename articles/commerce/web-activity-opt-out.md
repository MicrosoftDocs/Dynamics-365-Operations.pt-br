---
title: Cancelar a coleta de eventos da atividade Web
description: Este artigo explica como você pode permitir que os visitantes do seu site recusem a coleta de eventos de atividade da Web no Microsoft Dynamics 365 Commerce.
author: aamiral
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 78d3f795820eb36d1a81fb28875456e7471f8971
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878390"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Cancelar a coleta de eventos da atividade Web
[!include [banner](includes/banner.md)]

Este artigo explica como você pode permitir que os clientes optem por cancelar a coleção de evento de atividade da Web no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce permite que os administradores de sites analisem a atividade da Web de usuários de seus sites de comércio eletrônico. Dessa forma, eles podem compreender melhor como os sites são usados e podem otimizar os sites para proporcionar uma experiência de usuário aprimorada e atender a objetivos comerciais.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Maneiras de os administradores implementarem uma experiência de recusa

Os administradores podem implementar uma experiência de recusa de três maneiras.

### <a name="opt-out-on-behalf-of-users"></a>Recusar em nome de usuários

No gerenciamento de contas no Commerce headquarters (HQ), os administradores podem recusar em nome de usuários.

1. Nos cliente do HQ, na página **Todos os clientes**, procure e selecione um cliente.
1. Na página de detalhes do cliente, na Guia Rápida **Varejo**, na seção **Privacidade**, defina a opção **Não rastrear atividade da Web** como **Sim**.

    ![Configurações de privacidade.](media/Disablepersonalizationpart2.png)

1. Selecione **Salvar** e feche a página.

### <a name="module-based-opt-out-experience"></a>Experiência de recusa baseada em módulo

Os administradores podem permitir que os usuários autenticados cancelem a coleta de eventos de atividade da Web sozinhos. Para fornecer essa experiência de recusa, adicione o módulo de recusa de usuário às páginas de perfil de conta de cliente.

### <a name="custom-extensions"></a>Extensões personalizadas

Os administradores podem criar suas próprias extensões para gerenciar a experiência de recusa dos usuários. Para obter mais informações, consulte [Chamar APIs do Retail Server](e-commerce-extensibility/call-retail-server-apis.md) e a [extensibilidade de canal online](e-commerce-extensibility/overview.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
