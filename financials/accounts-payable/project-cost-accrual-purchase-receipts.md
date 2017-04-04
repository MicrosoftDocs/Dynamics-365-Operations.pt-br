---
title: "Acúmulo de custo previsto do projeto em recibos de compra"
description: "Este tópico descreve como os custos acumulados de projeto a partir de compra podem ser rastreados no Microsoft Dynamics 365 para as operações."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 27a0a71095dce46c0119b32a92f8c4dce0f42e43
ms.lasthandoff: 03/31/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Acúmulo de custo previsto do projeto em recibos de compra

Este tópico descreve como os custos acumulados de projeto a partir de compra podem ser rastreados no Microsoft Dynamics 365 para as operações. 

As notas fiscais para um projeto chegam em geral após o produto e serviços é entregue, que podem ter um impacto significativo para indicadores chave de desempenho (KPIs) da chave projeto. É importante acompanhar poder essas transações em relatórios financeiros e de projeto.

O cenário a seguir ilustra exemplo deste. 

Consulte de A Contoso começou um novo projeto de implantação do nuvem. Uma ordem de compra está criada comprar um computador para o projeto. O computador $1500 custará e serviços da instalação custarão $150. O fornecedor e entregue instalou o computador a nota fiscal, mas ainda não tiver atingido consulte de A Contoso. O gerente de projeto gostaria consulte a projeto da competência de custo previsto de $1650 antes da fatura obtenha entregue. Esses custos devem também ser refletidos nos demonstrativos financeiros de fechamento de mês empresarial. 

Os custos acumulados precisam ser registradas em nível financeiro e o nível do para fins de relatório. Em dynamics 365 para operações, a atualização financeira de recebimento de produtos pode serem rastreadas para categorias de item e de itens. 

Para itens, ** parâmetros de contas a pagar ** na página, selecione ** lançar recebimentos de produtos no razão ** a opção.
[![(accruals1]. /media/accruals1-1024x409.png)](. /media/accruals1.png) 

Para categorias de compras, ** regras de diretiva de categoria ** na página, selecione ** compras ** diretivas, e selecione ** aumentam as despesas de compra em recibo ** para cada categoria de compras.
[![(accruals2]. /media/accruals2-1024x569.png)](. /media/accruals2.png) 

** Despesas de compra faturadas e un- ** ** competência de compra ** contas ** configuração de postagem ** serão usadas em quando comprovantes relacionadas ao recebimento de produtos são lançadas.
[![(accruals3]. /media/accruals3-1024x429.png)](. /media/accruals3.png) 

Com esse mesmo deixe-nos cenário, consulte como lançar um recebimento de produtos afetará a contabilidade e as informações sobre o projeto. 

** Etapa 1: ** Crie e confirme uma nova ordem de compra do projeto registre a compra de um computador para $1500 e de serviço de instalação para $150.
[![(accruals4]. /media/accruals4-1024x497.png)](. /media/accruals4.png) 

Quando a ordem de compra for confirmada, as transações do custo comprometido são criadas para o projeto. 
[![(accruals5]. /media/accruals5-1024x219.png)](. /media/accruals5.png) 

> [!NOTE]
> As transações do custo comprometido terão ** origem da transação definido ** campo ** ** ordem de compra. Criar e confirmar uma ordem de compra não cria transações para um projeto. 

** Etapa 2: ** O produto e serviços e entregue é um recebimento de produtos é registrado. 

Lançar um recebimento de produtos gera e lança um comprovante no razão. O comprovante debitará despesa de compra, a conta un- faturada, e a conta de competência de compra de crédito. 
[![(accruals6]. /media/accruals6-1024x214.png)](. /media/accruals6.png)

> [!NOTE]
> Lançar um recebimento de produtos usados a configuração de postagem de produtos e categorias de compras, não a configuração de postagem das categorias de projeto. Para refletir corretamente o impacto financeiro de competências de compra, essa configuração precisa ser. de serem 

É possível mapear categorias de compras para projetar categorias ** ** categoria de compras na página.
[![(accruals7]. /media/accruals7-1024x390.png)](. /media/accruals7.png)

** Etapa 3: ** Crie uma nota fiscal de fornecedor de rascunho. 

Em dynamics 365 para operações, lançar um recebimento de produtos não afeta informações sobre o projeto. Como uma solução alternativa, você pode gerar uma nota fiscal de fornecedor de rascunho mesmo depois lançar o recebimento de compra. Ir ** ** ordem de compra para &gt; a página guia ** fiscal ** &gt; ** geram ** &gt; ** fatura **. Isso cria um documento de nota fiscal pendente que atualize informações sobre o projeto. 

Criar uma nota fiscal de fornecedor de rascunho geradas durante transações de projeto. 
[![(accruals8]. /media/accruals8-1024x225.png)](. /media/accruals8.png) 

** Custo comprometido ** na página, registros criados na etapa 1 serão fechadas e novos recordes serão criados para refletir o compromisso de custo previsto que vêm da nota fiscal de fornecedor pendente. ** Origem da transação ** o campo para o custo comprometido será definida ** ** nota fiscal de fornecedor.
[![(accruals9]. /media/accruals9-1024x200.png)](. /media/accruals9.png)

A nota fiscal permanecerá fornecedor de um estado pendente até que a nota fiscal de fornecedor real chegue.


