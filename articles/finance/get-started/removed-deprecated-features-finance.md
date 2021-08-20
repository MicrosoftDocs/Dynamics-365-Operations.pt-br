---
title: Recursos removidos ou obsoletos do Dynamics 365 Finance
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.
author: roschlom
ms.date: 04/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7ce7353de5795fd82e53bb1b7919c95dae4fe0ab6b8f536361613a7bcae19101
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781192"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Recursos removidos ou obsoletos do Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção de Dynamics 365 Finance.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](/dynamics/s-e/global/axtechrefrep_61). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>Recursos removidos ou substituídos na versão 10.0.20 do Finance

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>Configuração de formato do relatório eletrônico (ER) "Solicitação de dados da fatura de consulta do RTIR (HU)"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Removido do processamento de interoperação do sistema de mensagens eletrônicas com o sistema online de faturamento húngaro |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Descontinuação: até 15 de abril de 2022, planejamos não oferecer mais a configuração de formato "Solicitação de dados para consulta da fatura do RTIR (HU)". |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>Formato de relatório eletrônico (ER) "Arquivo de auditoria francês FEC" para a França no formato "Saída de arquivo de auditoria alemão"

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído pelo novo formato "Arquivo de auditoria FEC (FR)" |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de maio de 2022, planejamos interromper o suporte ao formato de relatório eletrônico (ER) "Arquivo de auditoria francês FEC" para a França no formato "Saída de arquivo de auditoria alemão". O novo formato Arquivo de auditoria FEC (FR) foi introduzido no "Modelo de exportação de dados". |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>Recursos removidos ou substituídos na versão 10.0.17 do Finance

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>Repositório LCS como uma opção de armazenamento para configurações de Relatório eletrônico

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído pelo novo repositório global do RCS (serviço de configuração regulatória) |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Dynamics 365 Finance, produtos do Supply Chain Management e Project Operations|
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: em 1º de abril de 2022, planejamos não oferecer mais suporte ao repositório do Microsoft Dynamics Lifecycle Services (LCS) como uma opção de armazenamento para configurações de relatório eletrônico (ER). As novas configurações do Microsoft ER serão publicadas para download exclusivamente no repositório global. O repositório global pode ser acessado de produtos e RCS do Dynamics 365. Para obter mais informações, consulte [Importar configurações do ER a partir de RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) e [Regulatory Configuration Service - Suspensão do armazenamento de Lifecycle Services](../localizations/rcs-lcs-repo-dep-faq.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>Recursos removidos ou substituídos na versão 10.0.16 do Finance

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>Formatos de relatório eletrônico "Declaração de IVA (CZ)" e "Exportação de instrução de controle (CZ)" para a República Tcheca

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituídos por novos formatos |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Substituído: até 22 de janeiro de 2022, planejamos não oferecer mais suporte aos formatos de relatório eletrônico (ER) "Declaração de IVA (CZ)" e "Exportação de demonstrativo de controle (CZ)". Em vez disso, os formatos XML de declaração de IVA (CZ), Excel de declaração de IVA (CZ) e Demonstrativo de controle de IVA (CZ) são introduzidos no modelo "Declaração de imposto". |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>O formato de relatório eletrônico "Formato de exportação da transação do razão (BE)" e o respectivo modelo "Exportação de transações do razão (BE)" para a Bélgica

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído pelo novo formato ER, no modelo "Arquivo de Auditoria Padrão (SAF-T)".  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de dezembro de 2021, planejamos não oferecer mais suporte ao formato de Relatório eletrônico (ER) "Formato de exportação de transações do razão (BE)" e seu respectivo modelo "Exportação de transação do razão (BE)". Um novo formato "Exportação de dados da contabilidade (BE)", em conjunto com "Mapeamento de modelos de dados da contabilidade", é introduzido no modelo "Arquivo de Auditoria Padrão (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>Relatório "IVA 100" para o Reino Unido no formato SSRS

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído pelo novo formato ER - o formato "Declaração de IVA Excel (UK)" em "Modelo de declaração de impostos".  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de dezembro de 2021, planejamos não oferecer mais suporte ao "relatório IVA 100" no formato SSRS. Um novo formato "Declaração de IVA Excel (UK)" no "Modelo de declaração de imposto" foi introduzido no [recurso IVA MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>Recursos removidos ou substituídos na versão 10.0.15 do Finance

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Suporte do Internet Explorer 11 para Dynamics 365 foi substituído

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A partir de dezembro de 2020, o suporte do Internet Explorer 11 da Microsoft para todos os produtos Dynamics 365 é preterido e Internet Explorer 11 não receberá suporte depois de agosto de 2021.<br><br>Isso afetará os clientes que usam os produtos do Dynamics 365 projetados para serem usados por meio de uma interface do Internet Explorer 11. Depois de agosto de 2021, o Internet Explorer 11 não terá suporte para esses produtos do Dynamics 365. |
| **Substituída por outro recurso?**   | Recomendamos que os clientes façam a transição para o Microsoft Edge.|
| **Áreas afetadas do produto**         | Todos os produtos do Dynamics 365 |
| **Opção de implantação**              | Todas|
| **Status**                         | Preterido. O Internet Explorer 11 não terá suporte depois de agosto de 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>Recursos removidos ou substituídos na versão 10.0.12 do Finance

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>Não preterido: relatórios SSRS poloneses: registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – Referência de recurso PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não é legalmente obrigatório.  |
| **Substituída por outro recurso?**   | Sim (formato do Excel para arquivo de auditoria padrão com declaração de IVA - JPK_VDEK) |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Não preterido: a partir de 27 de abril de 2021, planejamos continuar a oferecer suporte aos relatórios SSRS: **registro de IVA de saída, registro de IVA de entrada, registro de IVA de resumo da UE – Referência de recurso PL-00014**. O exemplo de formato do Excel para Arquivo de Auditoria Padrão com declaração de IVA (JPK_VDEK) também foi introduzido. |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>Recursos removidos ou substituídos na versão 10.0.11 do Finance

### <a name="norwegian-standard-main-accounts"></a>Contas principais no padrão da Noruega

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Recriar  |
| **Substituída por outro recurso?**   | Sim (Substituída pelos parâmetros específicos do aplicativo do formato ER) |
| **Áreas afetadas do produto**         | Requerimento |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: Em 1° de abril de 2021, planejamos descontinuar o suporte da funcionalidade relacionada às contas principais Padrão: Campo de referência, tabela relacionada, entidade de dados. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>Recursos removidos ou substituídos na versão 10.0.7 do Finance

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Caixa de diálogo Alterar solicitação de fluxo de trabalho não inclui mais a seleção do usuário de lista suspensa

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Recurso alterado para a seleção de grupos de contas.  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Fluxo de Trabalho |
| **Opção de implantação**              | Todas |
| **Status**                         | Substituído: até 1º de dezembro de 2020, não planejamos mais oferecer suporte à configuração de tipos de comprovantes chineses sem a seleção de Grupos de contas. Obtenha mais detalhes sobre o novo design em [Novidades no 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
