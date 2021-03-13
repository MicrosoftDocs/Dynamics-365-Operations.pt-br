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
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7090a7461c7b77d74f081afd8f22db100cdf0792
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154168"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Recursos removidos ou obsoletos do Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://docs.microsoft.com/dynamics/s-e/). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Recursos removidos ou substituídos na versão 10.0.16 do Finance

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Formatos de relatório eletrônico "Declaração de IVA (CZ)" e "Exportação de instrução de controle (CZ)" para a República Tcheca

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituídos por novos formatos |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Substituído: até 22 de janeiro de 2022, planejamos não oferecer mais suporte aos formatos de relatório eletrônico (ER) "Declaração de IVA (CZ)" e "Exportação de demonstrativo de controle (CZ)". Em vez disso, os formatos XML de declaração de IVA (CZ), Excel de declaração de IVA (CZ) e Demonstrativo de controle de IVA (CZ) são introduzidos no modelo "Declaração de imposto". |

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
