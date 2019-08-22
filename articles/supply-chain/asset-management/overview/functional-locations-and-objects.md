---
title: Locais e ativos funcionais
description: Este tópico descreve locais e ativos funcionais em Gerenciamento de Ativos. O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de manutenção no Microsoft Dynamics 365 for Finance and Operations.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 351e27dfbbd5227a9642f14a48afe194c447a0f3
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783082"
---
# <a name="functional-locations-and-assets"></a>Locais e ativos funcionais

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Este tópico descreve locais e ativos funcionais em Gerenciamento de Ativos. O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de manutenção no Microsoft Dynamics 365 for Finance and Operations.

## <a name="overview"></a>Visão Geral

O Gerenciamento de Ativos está perfeitamente integrado a vários módulos no Finance and Operations. A ilustração a seguir mostra as interfaces com outros módulos.

![Figura 1](media/01-overview-image.png)

O Gerenciamento de Ativos permite que você gerencie e execute com eficiência todas as tarefas relacionadas ao gerenciamento e à manutenção de vários tipos de equipamentos na sua empresa. Este equipamento inclui computadores, equipamento de produção e veículos. O Gerenciamento de Ativos também dá suporte a soluções em vários setores.

A ilustração a seguir mostra uma visão geral da funcionalidade principal que é coberta pelo Gerenciamento de Ativos.

![Figura 2](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Locais e ativos funcionais

Os locais funcionais são usados para gerenciar ativos em locais. Este gerenciamento inclui o controle de custos de ativos em locais funcionais. Os locais funcionais são estruturados hierarquicamente e os locais podem ter sublocais. A estrutura de locais funcionais é estática. Ou seja, locais não podem mudar de lugar. Ativos podem ser instalados em locais funcionais e, se necessário, podem ser instalados em outros locais funcionais posteriormente.

Custos de ativos sempre acompanham o local do ativo. Ou seja, se você instalar um ativo em um novo local funcional, o ativo usará automaticamente as dimensões financeiras que relacionadas ao novo local funcional. Portanto, os custos de ativos são sempre relacionadas ao local funcional no qual o ativo está instalado no momento. Esta manipulação automática de dimensões financeiras ajuda a garantir o rastreamento completo de custos quando sua empresa faz o controle e relatório de projetos em locais funcionais.

A maneira que você cria a hierarquia de locais funcionais depende de requisitos da sua empresa para manter equipamentos internos ou atender equipamentos de clientes. A figura a seguir mostra um exemplo de locais funcionais baseados em localizações geográficas.

![Figura 3](media/03-overview-image.png)

A figura a seguir mostra um exemplo de locais funcionais baseados em clientes.

![Figura 4](media/04-overview-image.png)
