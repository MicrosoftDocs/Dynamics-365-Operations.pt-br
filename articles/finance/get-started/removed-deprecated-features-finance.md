---
title: Recursos removidos ou obsoletos do Dynamics 365 Finance
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.
author: roschlom
manager: AnnBe
ms.date: 12/07/2020
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
ms.openlocfilehash: a406db6d78302fa05596a58fffb7464222d4bfea
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689485"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Recursos removidos ou obsoletos do Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Recursos removidos ou substituídos na versão 10.0.16 do Finance

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>O formato de relatório eletrônico "Formato de exportação da transação do razão (BE)" e o respectivo modelo "Exportação de transações do razão (BE)" para a Bélgica

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído pelo novo formato ER, no modelo "Arquivo de Auditoria Padrão (SAF-T)".  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de dezembro de 2021, planejamos não oferecer mais suporte ao formato de Relatório eletrônico (ER) "Formato de exportação de transações do razão (BE)" e seu respectivo modelo "Exportação de transação do razão (BE)". Um novo formato "Exportação de dados da contabilidade (BE)", em conjunto com "Mapeamento de modelos de dados da contabilidade", é introduzido no modelo "Arquivo de Auditoria Padrão (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Relatório "IVA 100" para o Reino Unido no formato SSRS

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído pelo novo formato ER - o formato "Declaração de IVA Excel (UK)" em "Modelo de declaração de impostos".  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de dezembro de 2021, planejamos não oferecer mais suporte ao "relatório IVA 100" no formato SSRS. Um novo formato "Declaração de IVA Excel (UK)" no "Modelo de declaração de imposto" foi introduzido no [recurso IVA MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Recursos removidos ou substituídos na versão 10.0.15 do Finance

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Suporte do Internet Explorer 11 para Dynamics 365 foi substituído

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A partir de dezembro de 2020, o suporte do Internet Explorer 11 da Microsoft para todos os produtos Dynamics 365 é preterido e Internet Explorer 11 não receberá suporte depois de agosto de 2021.<br><br>Isso afetará os clientes que usam os produtos do Dynamics 365 projetados para serem usados por meio de uma interface do Internet Explorer 11. Depois de agosto de 2021, o Internet Explorer 11 não terá suporte para esses produtos do Dynamics 365. |
| **Substituída por outro recurso?**   | Recomendamos que os clientes façam a transição para o Microsoft Edge.|
| **Áreas afetadas do produto**         | Todos os produtos do Dynamics 365 |
| **Opção de implantação**              | Todas|
| **Status**                         | Preterido. O Internet Explorer 11 não terá suporte depois de agosto de 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Recursos removidos ou substituídos na versão 10.0.12 do Finance

### <a name="polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Relatórios SSRS poloneses: registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – Referência de recurso PL-00014

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não é legalmente obrigatório.  |
| **Substituída por outro recurso?**   | Sim (formato do Excel para arquivo de auditoria padrão com declaração de IVA - JPK_VDEK) |
| **Áreas afetadas do produto**         | Requerimento |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de julho de 2021, planejamos não oferecer mais suporte aos relatórios SSRS: **registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – referência de recurso PL-00014**. Em vez disso, o exemplo de formato do Excel para arquivo de auditoria padrão com declaração de IVA (JPK_VDEK) será introduzido. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Recursos removidos ou substituídos na versão 10.0.11 do Finance

### <a name="norwegian-standard-main-accounts"></a>Contas principais no padrão da Noruega

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Recriar  |
| **Substituída por outro recurso?**   | Sim (Substituída pelos parâmetros específicos do aplicativo do formato ER) |
| **Áreas afetadas do produto**         | Requerimento |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: Em 1° de abril de 2021, planejamos descontinuar o suporte da funcionalidade relacionada às contas principais Padrão: Campo de referência, tabela relacionada, entidade de dados. |

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
