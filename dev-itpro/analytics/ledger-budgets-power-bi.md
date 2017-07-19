---
title: "Conteúdo do Power BI real versus orçamento"
description: "Este tópico descreve o Conteúdo do Power BI real versus orçamento. Ele explica como acessar os relatórios incluídos no conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usadas para criar o conteúdo."
author: ryansandness
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5d52cce3cccb16f0645d9de1832ebeffbfaf3a09
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="actual-vs-budget-power-bi-content"></a>Conteúdo do Power BI real versus orçamento

[!include[banner](../includes/banner.md)]


Este tópico descreve o conteúdo do Microsoft Power BI **Real versus orçamento**. Ele explica como acessar os relatórios do Power BI, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo. 

# <a name="overview"></a>Visão Geral

O conteúdo do Power BI **Real versus orçamento** foi criado para indivíduos responsáveis por monitorar o desempenho real versus o orçamento da organização. O conteúdo do Power BI **Real versus orçamento** oferece visibilidade sobre as variações de orçamento. Você pode analisar o orçamento do ano atual por categoria de conta, código de orçamento, conta principal, descrições de conta principal ou período fiscal para obter um melhor entendimento sobre a causa das variações. 

# <a name="accessing-the-power-bi-content"></a>Acessando o conteúdo do Power BI
Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, atualização de julho de 2017, os relatórios de conteúdo do Power BI **Real versus orçamento** são exibidos nos espaços de trabalho do **Orçamento e previsões do razão** e **CFO**.

# <a name="reports-that-are-included-in-the-power-bi-content"></a>Relatórios incluídos no conteúdo do Power BI
A tabela a seguir fornece detalhes sobre as métricas encontradas em cada página de relatório no conteúdo **Real versus orçamento** do Power BI.

| Relatório                      | Métrica |
|-----------------------------|---------|
| Despesas - Real vs de orçamento | <ul><li>Despesas totais deste ano</li><li>Total de despesas de orçamento deste ano</li></ul> |
| Receita - Real vs de Orçamento  | <ul><li>Receita total deste ano</li><li>Receita total de orçamento deste ano</li><ul> |
| Despesa                     | <ul><li>Despesas totais deste ano</li><li>Meta de despesas com base no orçamento </li><ul> |
| Receita                     | <ul><li>Receita total deste ano</li><li>Meta de receita com base no orçamento </li><ul> |
| Renda líquida                  | <ul><li>Rendimento líquido deste ano</li><li>Meta de rendimento líquido com base no orçamento </li><ul> |

## <a name="extending-the-power-bi-content"></a>Aumentando o conteúdo do Power BI
Usando os pacotes de conteúdo disponíveis no Microsoft Dynamics Lifecycle Services (LCS), você pode fornecer grande análise às pessoas que não acessam o Microsoft Dynamics 365. Você pode modificar esses pacotes de conteúdo para que eles incluam outros relatórios ou imagens e, em seguida, publique os pacotes de conteúdo no locatário do Power BI.com para análise. 

Você pode localizar o conteúdo do Power BI **Real versus orçamento** na biblioteca de ativos compartilhados do LCS. Para obter mais informações sobre como baixar o pacote de conteúdo e implementá-lo na sua organização, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md). Para ver uma demonstração que mostra como implementar o conteúdo do Power BI, veja o Office Mix [Conteúdo do Power BI da Microsoft e seus parceiros no Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w).

# <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades

| Entidade                    | Conteúdo |
|---------------------------|----------|
| Atividades de contabilidade | Valores de transação referente à contabilidade |
| Atividades de orçamento         | Valores de transação para o registro de orçamento |
| Contas Principais             | Contas principais para filtrar relatórios |
| Calendários fiscais          | Calendários fiscais para filtrar relatórios |
| Razões                   | Razões que podem ser usados para filtrar relatório para o razão atual |
| Códigos de orçamento              | Códigos de orçamento para filtrar relatórios |
| Entidades legais            | Entidades legais que podem ser usadas para filtrar relatório para a entidade legal atual |

