---
title: Novidades ou alterações no Dynamics 365 Talent (31 de janeiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690043"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a>Novidades ou alterações no Dynamics 365 Talent (31 de janeiro de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

**Compilação 8.1.2128**

## <a name="core-hr-changes"></a>Alterações no Core HR

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a>A folga tirada no cartão pessoal de licença não considera as datas do plano de licença
Para os planos de licença que não são executados em um ano civil, o cartão **Tirado** agora exibe as folgas que foram tiradas no ano de licença defino no plano. Por exemplo, se o ano de licença de uma organização vai de 1º de junho a 30 de maio e um funcionário tirou três dias de folga em dezembro, o cartão **Tirado** em 15 de janeiro exibirá 3 dias. 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a>Os valores acumulados não está correspondendo à base de datas da camada
Novas opções foram adicionadas à licença e ausência (parâmetros **Recursos Humanos**) para permitir que clientes determinem quais meses da data de serviço dos funcionários são efetivos. Para algumas organizações, a data é o final do mês, mas para outras ela pode ser o início do próximo mês. Por exemplo, uma organização pode conceder folga em 31 de dezembro, enquanto outra pode conceder folga em 1º de janeiro. Essa opção permitirá que você escolha quando a folga deve ser concedida. 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a>As ações de contratação de trabalhadores estão com status "Fluxo de trabalho concluído"
As alterações foram feitas para corrigir um problema em que um pequeno número de fluxos de trabalho foram concluídos com um status "Fluxo de trabalho concluído". Novos fluxos de trabalho deverão agora mudar para um status "Concluído" quando o fluxo de trabalho for concluído. Os fluxos de trabalho com um status concluído serão modificados para um status de erro para permitir a atualização ou remoção se necessário. 
