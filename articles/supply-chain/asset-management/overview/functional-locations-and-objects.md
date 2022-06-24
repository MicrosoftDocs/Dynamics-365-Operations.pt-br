---
title: Locais funcionais e ativos
description: Este artigo descreve locais e ativos funcionais em Gerenciamento de Ativos. O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de manutenção no Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 274e80136ee303af9d0fe5fd04095f575a345d19
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875645"
---
# <a name="functional-locations-and-assets"></a>Locais funcionais e ativos

[!include [banner](../../includes/banner.md)]

 

Este artigo descreve locais e ativos funcionais em Gerenciamento de Ativos. O Gerenciamento de Ativos é um módulo avançado para gerenciar ativos e trabalhos de manutenção no Dynamics 365 Supply Chain Management.

## <a name="overview"></a>Visão Geral

O Gerenciamento de Ativos está perfeitamente integrado a vários módulos com outros aplicativos do Finance and Operations. A ilustração a seguir mostra as interfaces com outros módulos.

![Diagrama mostrando como o Gerenciamento de Ativos interage com outros módulos.](media/01-overview-image.png)

O Gerenciamento de Ativos permite que você gerencie e execute com eficiência todas as tarefas relacionadas ao gerenciamento e à manutenção de vários tipos de equipamentos na sua empresa. Este equipamento inclui computadores, equipamento de produção e veículos. O Gerenciamento de Ativos também dá suporte a soluções em vários setores.

A ilustração a seguir mostra uma visão geral da funcionalidade principal que é coberta pelo Gerenciamento de Ativos.

![Diagrama mostrando a principal funcionalidade do Gerenciamento de Ativos.](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Locais funcionais e ativos

Os locais funcionais são usados para gerenciar ativos em locais. Este gerenciamento inclui o controle de custos de ativos em locais funcionais. Os locais funcionais são estruturados hierarquicamente e os locais podem ter sublocais. A estrutura de locais funcionais é estática. Ou seja, locais não podem mudar de lugar. Ativos podem ser instalados em locais funcionais e, se necessário, podem ser instalados em outros locais funcionais posteriormente.

Custos de ativos sempre acompanham o local do ativo. Ou seja, se você instalar um ativo em um novo local funcional, o ativo usará automaticamente as dimensões financeiras que relacionadas ao novo local funcional. Portanto, os custos de ativos são sempre relacionadas ao local funcional no qual o ativo está instalado no momento. Esta manipulação automática de dimensões financeiras ajuda a garantir o rastreamento completo de custos quando sua empresa faz o controle e relatório de projetos em locais funcionais.

A maneira que você cria a hierarquia de locais funcionais depende de requisitos da sua empresa para manter equipamentos internos ou atender equipamentos de clientes. A figura a seguir mostra um exemplo de locais funcionais baseados em localizações geográficas.

![Diagrama mostrando locais funcionais com base em locais geográficos.](media/03-overview-image.png)

A figura a seguir mostra um exemplo de locais funcionais baseados em clientes.

![Diagrama mostrando locais funcionais com base em clientes.](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]