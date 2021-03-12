---
title: Preço base e contratos comerciais
description: Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db3a91807c0cfb51426c03eeaf7785168e6ad0de
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006041"
---
# <a name="base-price-and-trade-agreements"></a>Preço base e contratos comerciais

[!include [banner](../includes/banner.md)]

Este procedimento orienta na criação de contratos comerciais de preço de venda específicos para o canal. Este procedimento usa a empresa de dados de demonstração USRT.

1. No **Painel de navegação**, vá para **Módulos > Varejo e Comércio > Gerenciamento de preços e descontos > Grupos de preços > Todos os grupos de preços**. Os grupos de preço são como os contratos comerciais são atribuídos a canais específicos. O uso de grupos de preços para atribuir contratos comerciais a um canal habilita a definição de preços específica para o canal.  
2. Clique em **Novo**.
3. No campo **Grupos de preços**, digite um valor.
4. No campo **Nome**, digite um valor.
5. Clique em **Salvar**.
6. Feche a página.
7. No **Painel de navegação**, acesse **Módulos > Varejo e Comércio > Canais > Lojas > Todas as lojas**.
8. Na lista, selecione 'Nova York'.
9. No Painel de Ações, clique em **Loja**.
10. Clique em **Grupos de preços**.
11. Clique em **Novo**.
12. No campo **Grupos de preços**, clique no botão suspenso para abrir a pesquisa.
13. Na lista, localize e selecione o registro desejado.
14. Clique em **Salvar**.
15. Feche a página.
16. Feche a página.
17. No **Painel de navegação**, vá para **Módulos > Varejo e Comércio > Produtos e categorias > Produtos lançados por categoria**.
18. Na lista, clique no link na linha selecionada.
19. Clique em **Editar**.
20. Expanda a Guia Rápida **Vender**.
21. No campo **Preço**, insira um número. Esse preço será usado se nenhum contrato comercial aplicável for encontrado.  
22. Clique em **Salvar**.
23. No **Painel de Ações**, clique em **Vender**.
24. Criar em **Criar contratos comerciais**.
25. Clique em **Novo**.
26. No campo **Nome**, clique no botão suspenso para abrir a pesquisa.
27. Na lista, selecione **Comércio**. Nos dados de demonstração, o nome do diário **Comércio** tem a relação de **Preço (vendas)** padrão. Isso significa que todas as novas linhas criadas assumirão como padrão os contratos comerciais de preço de venda.  
28. No **Painel de ação**, clique em **Linhas**.
29. No campo **Tipo de código de participante**, selecione "Grupo".
30. No campo **Seleção de conta**, clique no botão suspenso para abrir a pesquisa.
31. Na lista, localize e selecione o PDV desejado. Isso completará o link do canal com o grupo de preços com o contrato comercial.  
32. No campo **Relação de item**, digite um valor.
33. No campo **Valor em moeda**, insira um número.
34. Na Guia Rápida **Detalhes**, marque ou desmarque caixa de seleção **Localizar próximo**. Quando **Localizar próximo** estiver definido como "Sim", o mecanismo de definição de preços continuará a pesquisar por contratos comerciais aplicáveis com um preço de venda mais baixo. Quando **Localizar próximo** estiver definido como "Não", o mecanismo de definição de preços para de pesquisar e usa o contrato comercial.  
35. Clique em **Enviar**.
36. Clique em **OK**.
37. Feche a página.
38. No **Painel de Ações**, clique em Vender.
39. Clique em **Preço de venda**.

