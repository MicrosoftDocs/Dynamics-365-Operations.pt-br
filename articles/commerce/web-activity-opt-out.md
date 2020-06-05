---
title: Cancelar a coleta de eventos da atividade Web
description: Este tópico explica como você pode permitir que os visitantes do seu site recusem a coleta de eventos de atividade da Web no Microsoft Dynamics 365 Commerce.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b0e48307527a8fea729d8dfdcdbc6337be0faf1
ms.sourcegitcommit: 8058db089b8768076ff1250be77d42a6e2b3f570
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378983"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Cancelar a coleta de eventos da atividade Web
[!include [banner](includes/banner.md)]

Este tópico explica como você pode permitir que os clientes optem por cancelar a coleção de evento de atividade da Web no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O Dynamics 365 Commerce permite que os administradores de sites analisem a atividade da Web de usuários de seus sites de comércio eletrônico. Dessa forma, eles podem compreender melhor como os sites são usados e podem otimizar os sites para proporcionar uma experiência de usuário aprimorada e atender a objetivos comerciais.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Maneiras de os administradores implementarem uma experiência de recusa

Os administradores podem implementar uma experiência de recusa de três maneiras.

### <a name="opt-out-on-behalf-of-users"></a>Recusar em nome de usuários

No gerenciamento de contas no Commerce headquarters (HQ), os administradores podem recusar em nome de usuários.

1. Nos cliente das sedes (HQ), na página **Todos os clientes**, procure e selecione um cliente.
1. Na página de detalhes do cliente, na Guia Rápida **Varejo**, na seção **Privacidade**, defina a opção **Não rastrear atividade da Web** como **Sim**.

    ![Configurações de privacidade](media/Disablepersonalizationpart2.png)

1. Selecione **Salvar** e feche a página.

### <a name="module-based-opt-out-experience"></a>Experiência de recusa baseada em módulo

Os administradores podem permitir que os usuários autenticados cancelem a coleta de eventos de atividade da Web sozinhos. Para fornecer essa experiência de recusa, adicione o módulo de recusa de usuário às páginas de perfil de conta de cliente.

### <a name="custom-extensions"></a>Extensões personalizadas

Os administradores podem criar suas próprias extensões para gerenciar a experiência de recusa dos usuários. Para obter mais informações, consulte [Chamar APIs do Retail Server](e-commerce-extensibility/call-retail-server-apis.md) e a [extensibilidade de canal online](e-commerce-extensibility/overview.md).
