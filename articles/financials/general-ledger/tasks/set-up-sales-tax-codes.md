---
title: Configurar códigos de imposto
description: Códigos de imposto são criados para cada imposto ou direito indireto que a entidade legal é obrigada a calcular, arrecadar e pagar às autoridades de imposto sobre vendas.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f29442c2ef2e3d0008a74298fda218e4cbd93f8e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571574"
---
# <a name="set-up-sales-tax-codes"></a>Configurar códigos de imposto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Códigos de imposto são criados para cada imposto ou direito indireto que a entidade legal é obrigada a calcular, arrecadar e pagar às autoridades de imposto sobre vendas.

Esta tarefa usa a empresa de demonstração USMF.



1. Vá para Imposto > Impostos indiretos > Imposto sobre vendas > Códigos de imposto sobre vendas.
2. Clique em Novo.
3. No campo Impostos, digite um valor.
4. No campo Nome, digite um valor.
5. Selecione um período de liquidação para especificar em que a autoridade de impostos sobre vendas e em intervalos que esses impostos sobre vendas precisem ser informado e pago.
6. Na lista, clique no link na linha selecionada.
7. Selecione um grupo de lançamentos contábeis para especificar as contas principais para lançar impostos sobre vendas na contabilidade.
8. Na lista, localize e selecione o registro desejado.
9. Na lista, clique no link na linha selecionada.
10. Expanda a Guia Rápida Cálculo.
    * O cálculo FastTab têm vários campos que controlam como os valores do imposto sobre vendas será calculado.  
11. No Painel de Ação, clique em Código de impostos de vendas.
12. Clique em Valores.
13. Na lista, marque a linha selecionada.
14. Insira o valor para este código de imposto.
    * No cálculo FastTab, no campo de origem, se o valor da unidade for selecionado, o valor será multiplicado pela quantidade da transação para calcular o valor do imposto sobre vendas.  Se o código de imposto não for um imposto baseado na unidade, o valor é uma porcentagem que é aplicada na origem para a qual esse código de imposto calcula o valor do imposto sobre vendas.     
15. Clique em Salvar.
16. Feche a página.
17. Clique em Salvar.

