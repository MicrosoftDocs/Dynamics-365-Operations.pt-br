---
title: Recursos removidos ou preteridos no Dynamics 365 Finance
description: Este artigo descreve os recursos que já foram removidos ou foram planejados para remoção do Dynamics 365 Finance.
author: kfend
ms.date: 10/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 516b2b6091fa620b21eebba25f56ff55aa282ffc
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643785"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>Recursos removidos ou preteridos no Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Este artigo descreve os recursos que já foram removidos ou foram planejados para remoção do Dynamics 365 Finance.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos em aplicativos de finanças e operações podem ser encontradas nos [Relatórios de referência técnica](/dynamics/s-e/global/axtechrefrep_61). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão de aplicativos de finanças e operações.

## <a name="features-removed-or-deprecated-in-the-finance-10031-release"></a>Recursos removidos ou substituídos na versão 10.0.31 do Finance

### <a name="edifact-paymul-at-configuration-under-payment-model"></a>Configuração EDIFACT PAYMUL (AT) no modelo de pagamento

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo para a reprovação/remoção** | Substituído por um novo formato baseado na ISO 20022 pain.001.001.09. | 
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Aplicativo |
| **Opção de implantação**              | Todos |
| **Status**                         | Preterido: os bancos na Áustria descontinuarão o EDICFACT-PAYMUL para pagamentos internacionais até novembro de 2022 e o substituirão pela versão XML pain.001.001.09N. Uma nova configuração foi adicionada no repositório de configuração global que permite aos usuários concluir a solicitação de pagamento internacional. |

## <a name="features-removed-or-deprecated-in-the-finance-10030-release"></a>Recursos removidos ou substituídos na versão 10.0.30 do Finance

### <a name="revenue-recognition"></a>Reconhecimento de receita

[Reconhecimento de receita](../../finance/accounts-receivable/revenue-recognition-overview.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo para a reprovação/remoção** |Substituído por uma funcionalidade aprimorada, [Cobrança de assinatura](../../finance/accounts-receivable/subscription-billing-summary.md)
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto** | Aplicativo |
| **Opção de implantação** | Todos |
| **Status** | Preterido: depois de abril de 2023, a funcionalidade Reconhecimento de receita no Dynamics 365 Finance não receberá mais suporte com correções de bugs. Será solicitado que os clientes usem a funcionalidade aprimorada, [Cobrança de assinatura](../../finance/accounts-receivable/subscription-billing-summary.md). Em outubro de 2023, o recurso Reconhecimento de receita não estará mais disponível. Será solicitado que os clientes migrem para a funcionalidade aprimorada Cobrança de assinatura. Para o recurso de pacote como parte do reconhecimento de receita, não há funcionalidade de substituição planejada neste momento.|

## <a name="features-removed-or-deprecated-in-the-finance-10029-release"></a>Recursos removidos ou substituídos na versão 10.0.29 do Finance

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Ordens de transferência de estoque com impostos no preço de transferência

[Ordens de transferência de estoque com impostos no preço de transferência](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo para a reprovação/remoção** | Substituído por uma funcionalidade aprimorada, [Ordens de transferência de estoque para a Índia](../../finance/localizations/apac-ind-stock-transfer.md)|
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto** | Aplicativo |
| **Opção de implantação** | Todos |
| **Status** | Preterido: depois de 2023 de abril, as **Ordens de transferência de estoque com impostos no preço de transferência** não receberão mais suporte com correções de bugs e correções de segurança. Será solicitado que os clientes usem a funcionalidade aprimorada, [Ordens de transferência de estoque para a Índia](../../finance/localizations/apac-ind-stock-transfer.md). Depois de outubro de 2023, a funcionalidade **Ordens de transferência de estoque com impostos no preço de transferência** não estará mais disponíveis e será solicitado que os clientes mudem para a funcionalidade aprimorada. |

### <a name="bank-statement-import-and-export-of-positive-pay-file"></a>Importação de extrato bancário e exportação de arquivo de pagamento positivo

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo para a reprovação/remoção** |Substituído por uma funcionalidade aprimorada, importar extratos bancários e exportar arquivos de pagamento positivos.| 
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Aplicativo |
| **Opção de implantação**              | Todos |
| **Status**                         | Preterido: a funcionalidade XSLT para importar e exportar arquivos não receberá mais suporte com correções de bugs e correções de segurança. Os clientes deverão usar a funcionalidade aprimorada: [Configurar arquivos de pagamento positivos usando o Relatório eletrônico](../../finance/accounts-payable/set-up-positive-pay-er.md) e [Configurar a importação avançada de reconciliação bancária usando o Relatório eletrônico](../../finance/accounts-payable/import-bai2-er.md). Após setembro de 2022, a funcionalidade XSLT não estará mais disponível e os clientes deverão mudar para a funcionalidade aprimorada.|


## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>Recursos removidos ou substituídos na versão 10.0.26 do Finance

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>Relatório de impostos para a Finlândia (design baseado em códigos de relatório)

[Relatório de impostos para a Finlândia](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por um novo design de declaração de IVA, [Declaração de IVA para a Finlândia](../localizations/emea-fin-vat-declaration.md). |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Aplicativo |
| **Opção de implantação**              | Todos |
| **Status**                         | Preterido: até 1º de dezembro de 2023, planejamos não oferecer mais suporte ao relatório de impostos para a Finlândia (layout de relatório finlandês). Os novos formatos de Relatório Eletrônico (ER) **Declaração de IVA em TXT (FI**) e **Declaração de IVA em Excel (FI)** foram introduzidos no modelo **Declaração de imposto**. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>Recursos removidos ou substituídos na versão 10.0.24 do Finance

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>Relatório de impostos sobre vendas para a Suécia (design baseado em códigos de relatório)

[Relatório de impostos sobre vendas para a Suécia](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por um novo design de declaração de IVA, [Declaração de IVA para a Suécia](../localizations/emea-swe-vat-declaration-sweden.md) |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido: Até 1º de dezembro de 2022, planejamos não oferecer mais suporte ao relatório de impostos sobre vendas para a Suécia (layout de relatório sueco). Os formatos de Relatório Eletrônico (ER) **XML de declaração de IVA (SE)** e **Excel de declaração de IVA (SE)** são introduzidos no modelo **Declaração de imposto**. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>Demonstrativo de IVA para a Áustria (design baseado em códigos de relatório)

[Detalhes de demonstrativo de IVA para a Áustria](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por um novo design de declaração de IVA, [Declaração de IVA para a Áustria](../localizations/emea-aut-vat-declaration-austria.md) |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido: Até 1º de dezembro de 2022, planejamos não oferecer mais suporte ao formato de Relatório Eletrônico (ER) **Declaração de IVA (AT)** no **modelo de declaração de IVA**. Os novos formatos **XML de declaração de IVA (AT)** e **Excel de declaração de IVA (AT)** são introduzidos no modelo **Declaração de imposto**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes"></a>Declaração ELSTER para a Alemanha (design baseado em códigos de relatório)

[Demonstrativo de IVA](../localizations/emea-de-vat-declaration.md)</br>
[Configurar declaração eletrônica de impostos para a Alemanha](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>
[Transmissão eletrônica da declaração de IVA (ELSTER)](../localizations/tasks/de-00003-electronic-transmission-elster.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por um novo design de declaração de IVA, [Declaração de IVA para a Alemanha](../localizations/emea-deu-vat-declaration-germany.md) |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido: Até 1º de dezembro de 2022, planejamos não oferecer mais suporte aos formatos de Relatório Eletrônico (ER) **Elster (DE)** e **Modelo Elster**. Os novos formatos **XML de declaração de IVA (DE)** e **Excel de declaração de IVA (DE)** são introduzidos no modelo **Declaração de imposto**. |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes"></a>Declaração OB para os Países Baixos (design baseado em códigos de relatório)

[Declaração OB](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por um novo design de declaração de IVA, [Declaração de IVA para os Países Baixos](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido: Até 1º de dezembro de 2022, planejamos não oferecer mais suporte aos formatos de Relatório Eletrônico (ER) **Declaração OB (NL)** e **Modelo de declaração OB**. Os novos formatos **XML de declaração de IVA (NL)** e **Excel de declaração de IVA (NL)** são introduzidos no modelo **Declaração de imposto**. |

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
| **Áreas afetadas do produto**         | Produtos do Dynamics 365 Finance, Supply Chain Management e Project Operations|
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

