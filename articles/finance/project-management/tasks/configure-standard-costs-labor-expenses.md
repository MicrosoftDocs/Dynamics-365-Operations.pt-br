---
title: Configurar custos padrão para trabalho e despesas
description: Este tópico explica como configurar custos padrão para mão de obra e despesas de um projeto.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140084"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Configurar custos padrão para trabalho e despesas

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar custos padrão para mão de obra e despesas de um projeto. Essa tarefa usa o conjunto de dados de USSI.

1. No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de custo (hora)**.
2. Selecione **Novo**.
3. No campo **Data efetiva**, insira uma data.
4. No campo **Preço de custo**, insira um número. É possível configurar um preço de custo padrão para a categoria de projeto ou configurar um preço de custo por número de trabalhador, número de projeto, categoria, data ou qualquer combinação destes itens. O preço de custo que é aplicado é o preço de custo com o nível mais alto de detalhes.  
5. Selecione **Salvar**.
6. No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de venda (hora)**.
7. Selecione **Novo**.
8. No campo **Data efetiva**, insira uma data.
9. No campo **Válido para**, selecione uma opção.
10. No campo **Definição de preços**, insira um número. Você pode configurar um preço de venda padrão para transações de horas ou para uma categoria de projeto. Também é possível configurar preços de venda por número do trabalhador, número do projeto, categoria, data da transação ou qualquer outra combinação desses itens. O preço de venda real, que é aplicado quando um trabalhador lança uma transação no Diário de horas, é aquele com o nível mais alto de detalhes. Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.  
11. Selecione **Salvar**.
12. Feche a página.
13. No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de custo (despesa)**.
14. Selecione **Novo**.
15. No campo **Data efetiva**, insira uma data.
16. No campo **Preço de custo**, insira um número. Vários campos podem ser preenchidos, mas este é o mínimo necessário salvar o registro.  
17. Selecione **Salvar**.
18. No Painel de Navegação, vá para **Módulos > Gerenciamento e contabilidade do projeto > Configuração > Preços > Preço de venda (despesa)**.
19. Selecione **Novo**.
20. No campo **Data efetiva**, insira uma data.
21. No campo **Válido para**, selecione uma opção.
22. No campo **Definição de preços**, insira um número. O preço de venda real, que é aplicado quando um trabalhador insere transações em um diário de despesas, é o preço de venda com o nível mais alto de detalhes. Por exemplo, se tanto o preço de venda geral quanto um preço de venda específico do trabalhador estiverem configurados, será usado o preço de venda específico do trabalhador.  
23. Selecione **Salvar**.

