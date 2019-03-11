---
title: Configurar custos padrão para trabalho e despesas
description: Este procedimento mostra como configurar custos padrão para mão de obra e despesas de um projeto.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "339386"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configurar custos padrão para trabalho e despesas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar custos padrão para mão de obra e despesas de um projeto. Essa tarefa usa o conjunto de dados de USSI.

1. Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de custo (hora).
2. Clique em Novo.
3. No campo Data efetiva, insira uma data.
4. No campo Preço de custo, insira um número.
    * É possível configurar um preço de custo padrão para a categoria de projeto ou configurar um preço de custo por número de trabalhador, número de projeto, categoria, data ou qualquer combinação destes itens. O preço de custo que é aplicado é o preço de custo com o nível mais alto de detalhes.  
5. Clique em Salvar.
6. Feche a página.
7. Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de venda (hora).
8. Clique em Novo.
9. No campo Data efetiva, insira uma data.
10. No campo Válido para, selecione uma opção.
11. No campo Definição de preços, insira um número.
    * Você pode configurar um preço de venda padrão para transações de horas ou para uma categoria de projeto. Também é possível configurar preços de venda por número do trabalhador, número do projeto, categoria, data da transação ou qualquer outra combinação desses itens. O preço de venda real, que é aplicado quando um trabalhador lança uma transação no Diário de horas, é aquele com o nível mais alto de detalhes. Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.  
12. Clique em Salvar.
13. Feche a página.
14. Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de custo (despesa).
15. Clique em Novo.
16. No campo Data efetiva, insira uma data.
17. No campo Preço de custo, insira um número.
    * Vários campos podem ser preenchidos, mas este é o mínimo necessário salvar o registro.  
18. Clique em Salvar.
19. Feche a página.
20. Vá para Gerenciamento e contabilidade de projeto > Configuração > Preços > Preço de venda (despesa).
21. Clique em Novo.
22. No campo Data efetiva, insira uma data.
23. No campo Válido para, selecione uma opção.
24. No campo Definição de preços, insira um número.
    * O preço de venda real, que é aplicado quando um trabalhador insere transações em um diário de despesas, é o preço de venda com o nível mais alto de detalhes. Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.  
25. Clique em Salvar.

