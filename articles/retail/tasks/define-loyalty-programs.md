---
title: Definir programas de fidelidade
description: Este procedimento mostra como configurar um programa de fidelidade com as duas camadas de fidelidade.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e57bb9c9e3348f2a9853dfda1351a8a75261beb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "355302"
---
# <a name="define-loyalty-programs"></a>Definir programas de fidelidade

[!include [task guide banner](../includes/task-guide-banner.md)]

Este procedimento mostra como configurar um programa de fidelidade com as duas camadas de fidelidade. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > .. > Programas de fidelidade.
2. Clique em Novo.
3. No campo Nome, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Adicionar nova linha.
6. No campo Nível, insira um número.
7. No campo Camada, insira um nome para a camada de fidelidade.
8. No campo Descrição, digite um valor.
9. No campo Intervalo de datas, clique no botão suspenso para abrir a pesquisa.
    * O intervalo de datas deve se estender para o futuro. Por exemplo, se o intervalo de datas selecionado para a camada de nível ouro for um período de um ano, qualquer cliente qualificado para a camada de nível ouro poderá receber as recompensas atribuídas a ela por um ano. Se o cliente se qualificar novamente para a camada de nível ouro enquanto estiver nessa camada, a data de vencimento da camada será estendida por outro ano, começando da data de requalificação.  
10. Na lista, clique no link na linha selecionada.
11. Clique em Adicionar linha.
12. No campo Nível, insira um número.
13. No campo Camada, insira um nome para a camada de fidelidade.
14. No campo Descrição, digite um valor.
15. No campo Intervalo de datas, clique no botão suspenso para abrir a pesquisa.
16. Na lista, clique no link na linha selecionada.
17. Clique em Salvar.
18. Na lista, localize e selecione o PDV desejado.
    * As regras de camada definem o número mínimo necessário de um ponto de recompensa a ser obtido durante um período de tempo para se qualificar para a camada.  
19. Ative/desative a expansão da seção Regras de camada.
20. Clique em Novo.
    * Você pode ter mais de uma regra de camada por camada. Por exemplo, você pode ter três critérios diferentes para ganhar uma camada: gastando R$500,00 em um mês, gastando R$1.000,00 em um ano e fazendo 20 transações em um ano. Para fazer isso, seria necessário criar regras em três camadas.  
21. No campo Ponto de recompensa, clique no botão suspenso para abrir a pesquisa.
    * Isso deve ser um ponto de recompensa de fidelidade não resgatável.  
22. Na lista, clique no link na linha selecionada.
23. No campo Pontos mínimos emitidos, insira um número.
    * Para o nível de camada mais baixo, se todos os clientes se qualificarem simplesmente participando do programa, insira '0'.  
24. No campo Intervalo de datas de avaliação, clique no botão suspenso para abrir a pesquisa.
    * O intervalo de datas deve se estender para o passado. Somente os pontos ganhos durante esse intervalo de datas serão contados para alcançar o valor emitido mínimo de pontos.  
25. Na lista, clique no link na linha selecionada.
26. Clique em Salvar.
27. Na lista, localize e selecione o PDV desejado.
28. Clique em Novo.
29. No campo Ponto de recompensa, clique no botão suspenso para abrir a pesquisa.
30. Na lista, clique no link na linha selecionada.
31. No campo Pontos mínimos emitidos, insira um número.
32. No campo Intervalo de datas de avaliação, clique no botão suspenso para abrir a pesquisa.
    * O intervalo de datas deve se estender para o passado.  
33. Na lista, clique no link na linha selecionada.
34. Clique em Salvar.
35. Clique em Grupos de preços.
    * Se desejar conceder descontos aos clientes do programa de fidelidade, será necessário atribuir um ou mais grupos de preços ao programa de fidelidade e atribuir os grupos de preços aos descontos. É uma prática recomendada não misturar grupos de preços nos diferentes tipos de entidades desconto.  Por exemplo, não use o mesmo grupo de preços para um desconto de fidelidade e um desconto de canal.  
36. No campo Grupos de preços, clique no botão suspenso para abrir a pesquisa.
    * O link Grupos de preços na parte superior da página é para o programa de fidelidade. O link Grupos de preços na guia rápida Camadas do programa é somente para uma camada específica de fidelidade.  
37. Na lista, clique no link na linha selecionada.
38. Clique em Salvar.
39. Feche a página.
40. Clique em Salvar.

