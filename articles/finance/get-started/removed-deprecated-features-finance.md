---
title: Recursos removidos ou obsoletos do Dynamics 365 Finance
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: ec13076e6a05c3402af566487f7921f6971da215
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127968"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Recursos removidos ou obsoletos do Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Recursos removidos ou substituídos na versão 10.0.12 do Finance

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Relatórios SSRS poloneses: registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – Referência de recurso PL-00014

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não é legalmente obrigatório.  |
| **Substituída por outro recurso?**   | Sim (formato do Excel para arquivo de auditoria padrão com declaração de IVA - JPK_VDEK) |
| **Áreas afetadas do produto**         | Requerimento |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de julho de 2021, planejamos não oferecer mais suporte aos relatórios SSRS: **registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – referência de recurso PL-00014**. Em vez disso, o exemplo de formato do Excel para arquivo de auditoria padrão com declaração de IVA (JPK_VDEK) será introduzido. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Recursos removidos ou substituídos na versão 10.0.7 do Finance

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Caixa de diálogo Alterar solicitação de fluxo de trabalho não inclui mais a seleção do usuário de lista suspensa
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Recurso alterado para a seleção de grupos de contas.  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Fluxo de Trabalho |
| **Opção de implantação**              | Todas |
| **Status**                         | Substituído: até 1º de dezembro de 2020, não planejamos mais oferecer suporte à configuração de tipos de comprovantes chineses sem a seleção de Grupos de contas. Obtenha mais detalhes sobre o novo design em [Novidades no 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
