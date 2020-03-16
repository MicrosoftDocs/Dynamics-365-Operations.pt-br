---
title: Recursos de plataforma removidos ou obsoletos
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção nas atualizações de plataforma do Finance and Operations apps.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087874"
---
# <a name="removed-or-deprecated-platform-features"></a>Recursos de plataforma removidos ou obsoletos

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção nas atualizações de plataforma do Finance and Operations apps.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="platform-update-32"></a>Update 32 para plataforma

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Caixa de diálogo Alterar solicitação de fluxo de trabalho não inclui mais a seleção do usuário de lista suspensa
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Isso foi um problema de segurança, pois a solicitação de alteração poderia ser enviada para um usuário indesejado. Isso também era um problema de usabilidade porque forçava o usuário a determinar quem foi o originador do fluxo de trabalho e selecioná-los manualmente.  |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Fluxo de Trabalho |
| **Opção de implantação**              | Todas |
| **Status**                         | A lista suspensa de seleção de usuário foi removida da caixa de diálogo alteração de solicitação na atualização de plataforma 32. Solicitações de alteração de solicitação serão enviadas automaticamente para o originador conforme pretendido. Para obter mais informações sobre essa funcionalidade, consulte [Ações em processos de aprovação de fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../migration-upgrade/deprecated-features.md).

