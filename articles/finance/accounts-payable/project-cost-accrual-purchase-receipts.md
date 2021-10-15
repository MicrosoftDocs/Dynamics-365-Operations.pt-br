---
title: Despesas de custo de projeto sobre recebimentos de compra
description: Este tópico descreve como os custos de projeto acumulados de recibos de compra podem ser rastreados no Microsoft Dynamics 365 Finance.
author: sunfzam
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7ae2f57e0104a30492363f1576962d36a2a1b04b
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2021
ms.locfileid: "7595221"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>Despesas de custo de projeto sobre recebimentos de compra

[!include [banner](../includes/banner.md)]

Este tópico descreve como os custos de projeto acumulados de recibos de compra podem ser rastreados no Microsoft Dynamics 365 Finance. 

As notas fiscais de um projeto geralmente chegam após as mercadorias e os serviços serem entregues, podendo ter um impacto significativo nos indicadores de desempenho principais do projeto (KPIs). É importante poder acompanhar essas transações em relatórios financeiros e de projeto.

O cenário de exemplo a seguir ilustra isto. 

A Consultoria da Contoso iniciou um novo projeto de implantação de nuvem. Uma ordem de compra é criada para comprar um computador para o projeto. O computador custará US$ 1.500 e os serviços de instalação custarão US$ 150. O fornecedor entregou e instalou o computador, mas as faturas ainda não chegaram à Consultoria da Contoso. O gerente de projeto gostaria de ver as despesas de custo de projeto de US$ 1.650 antes da fatura ser entregue. Esse custo também deve ser refletido nos demonstrativos financeiros finais do mês da empresa. 

Os custos acumulados precisam ser registradas em nível financeiro e em nível de projeto para fins de relatório. A atualização financeira do recibo do produto pode ser rastreada para categorias de item e compra. 

Para itens, na página **Parâmetros de contas a pagar**, selecione a opção **Lançar recibos de produto ao razão**.
[![Página Parâmetros de contas a pagar.](./media/accruals1-1024x409.png)](./media/accruals1.png) 

Para categorias de compras, na página **Regra de política de categoria**, selecione políticas de **Compras** e depois selecione **Despesas de compras acumuladas no recebimento** para cada categoria de compra.
[![Página Regra de política de categoria.](./media/accruals2-1024x569.png)](./media/accruals2.png) 

As contas **Despesa de compra não faturada** e **Despesa de compra** na **Configuração de lançamento** serão usadas quando os comprovantes relacionados ao recibo do produto forem lançados.

Com esse mesmo cenário, vejamos como o lançamento de recibo de produto impactará as informações de contabilidade e projeto. 

**Etapa 1:** Criar e confirmar uma nova ordem de compra do projeto para registrar a compra de um computador por US$ 1.500 e serviços de instalação por US$ 150.
[![Criar nova ordem de compra.](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Quando a ordem de compra for confirmada, as transações do custo comprometido são criadas para o projeto. 
[![Transações criadas.](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> As transações do custo comprometido terão o campo **Origem da transação** definido para **Ordem de compra**. Criar e confirmar uma ordem de compra não cria transações para um projeto. 

**Etapa 2:** Mercadorias e serviços são entregues e um recibo de produto é registrado. 

Lançar um recebimento de produtos gerará e lançará um comprovante no razão. O comprovante debitará as despesas de compra, conta não faturada e conta de despesas de compra em crédito. 
[![Comprovantes de transações.](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> Lançar um recibo de produtos usará a configuração de lançamento de categorias de compra e produtos, e não a configuração de lançamento das categorias de projeto. Para refletir corretamente o impacto financeiro das despesas de compra, essa configuração precisar estar alinhada. 

É possível mapear categorias de compras para projetar categorias na página **Categoria de compra**.
[![Página Categoria de compras.](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Etapa 3:** Criar um rascunho da fatura de fornecedor. 

Lançar um recibo de produto não afetará as informações de projeto. Como uma solução alternativa, você pode gerar um rascunho de fatura de fornecedor logo após o lançamento do recebimento de compra. Acesse a página **Ordem de compra** &gt; **Guia de fatura** &gt; **Gerar** &gt; **Fatura**. Essa ação cria um documento de fatura pendente que atualiza as informações do projeto. 

Criar um rascunho da fatura de fornecedor gerará transações de projeto pendentes. 
[![Minhas transações de projeto pendentes.](./media/accruals8-1024x225.png)](./media/accruals8.png) 

Na página **Custo comprometido**, registros criados na etapa 1 serão fechados e novos registros serão criados para refletir o custo comprometido proveniente de fatura de fornecedor pendente. O campo **Origem da transação** do custo comprometido será definido como **Fatura de fornecedor**.
[![Página Custos comprometidos.](./media/accruals9-1024x200.png)](./media/accruals9.png)

A fatura do fornecedor permanecerá em um estado pendente até que a fatura de fornecedor real chegue.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
