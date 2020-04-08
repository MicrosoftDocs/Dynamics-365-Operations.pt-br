---
title: Configurar perfis de lançamento de ativos fixos
description: Este guia de tarefa definirá os perfis de postagem de ativo fixo.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07961d8613b6b5e0e1c5dc6a91b554305dcb17f5
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138152"
---
# <a name="set-up-fixed-asset-posting-profiles"></a>Configurar perfis de lançamento de ativos fixos

[!include [banner](../../includes/banner.md)]

Este guia de tarefa definirá os perfis de postagem de ativo fixo.  Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.  Os exemplos dados no guia da tarefa são para um perfil de lançamentos básicos, embora os perfis de lançamento devam ser criados para seus requisitos do plano de contas e específico de relatórios financeiros.

1. No Painel de navegação, vá para **Módulos > Ativos fixos > Configuração > Perfis de lançamento de ativo fixo**.
2. Clique em **Novo**.
3. No campo **Perfil de lançamento**, insira um valor.
4. No campo **Descrição**, digite um valor. Será necessário criar um perfil de lançamento para cada tipo de transação de ativo fixo que você utilizará ao trabalhar com ativos fixos. Esta guia será iniciada com tarefas com o tipo de transação de aquisição.  
5. Na barra de ferramentas, clique em **Adicionar**.
6. No campo **Registro**, insira ou selecione um valor. O campo **Agrupamentos** permite que você defina o perfil de lançamentos na Tabela (uma configuração de conta para cada ativo fixo) ou Grupo (uma conta configurada para cada grupo de ativos fixos). Neste guia de tarefa, deixe o valor definido como "Tudo" para aplicar a todos os ativos fixos com o Registro especificado.  
7. No campo **Conta principal**, especifique os valores desejados. Para aquisições, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.    
8. No menu suspenso na Guia rápida **Contas contábeis**, selecione 'Ajuste de aquisição'. Para transações de ajuste de aquisição, usaremos as mesmas contas usadas para Transações de aquisição.  
9. Clique em **Adicionar**.
10. No campo **Registro**, insira ou selecione um valor.
11. No campo **Conta principal**, especifique os valores desejados. Para ajustes de aquisição, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.    
12. No menu suspenso na Guia rápida **Contas contábeis**, selecione 'Depreciação'.
13. Clique em **Adicionar**.
14. No campo **Registro**, insira ou selecione um valor.
15. No campo **Conta principal**, especifique os valores desejados.
16. No campo **Contrapartida**, especifique os valores desejados.
17. No menu suspenso na Guia rápida **Contas contábeis**, selecione 'Ajuste de depreciação'. Para transações de ajuste de depreciação, usaremos as mesmas contas usadas para Transações de depreciação.  
18. Clique em **Adicionar**.
19. No campo **Registro**, insira ou selecione um valor.
20. No campo **Conta principal**, especifique os valores desejados.
21. No campo **Contrapartida**, especifique os valores desejados.
22. No menu suspenso na Guia rápida **Contas contábeis**, selecione 'Descarte - venda'.
23. Clique em **Adicionar**.
24. No campo **Registro**, insira ou selecione um valor.
25. No campo **Conta principal**, especifique os valores desejados. Para descartes, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.  
26. No menu suspenso na Guia rápida **Contas contábeis**, selecione 'Descarte - sucata'. Use as mesmas contas para 'Descarte venda' e Descarte sucata'.  
27. Clique em **Adicionar**.
28. No campo **Registro**, insira ou selecione um valor.
29. No campo **Conta principal**, especifique os valores desejados. Para descartes, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.  
30. Expanda a Guia Rápida **Descarte**. Você deve configurar perfis de lançamentos de eliminação para venda e sucata.  Começaremos com transações de venda de eliminação.  
31. Clique em **Adicionar**.
32. No campo **Registro**, insira ou selecione um valor.
33. No campo **Lançar valor**, selecione 'Valor de aquisição'.
    * O valor de aquisição endereçará valores de aquisição e de ajuste de aquisição para todos os anos. Você também pode definir contas para esses tipos de transação separadamente.  
    * Você pode definir o processo de eliminação para usar contas diferentes dependendo dos resultados de descarte em um ganho ou perda. Definirei o tipo de valor de venda "Tudo" para usar as mesmas contas para todos os tipos de descarte.  
34. No campo **Conta principal**, especifique os valores desejados.
35. No campo **Contrapartida**, especifique os valores desejados.
36. Clique em **Adicionar**.
37. No campo **Registro**, insira ou selecione um valor.
38. No campo **Lançar valor**, selecione 'Depreciação (anos anteriores)'.  
38. No campo **Conta principal**, especifique os valores desejados.
39. No campo **Contrapartida**, especifique os valores desejados.
40. Clique em **Adicionar**.
41. No campo **Registro**, insira ou selecione um valor.
42. No campo **Lançar valor**, selecione 'Depreciação (este ano)'.
43. No campo **Conta principal**, especifique os valores desejados.
44. No campo **Contrapartida**, especifique os valores desejados.
45. Clique em **Adicionar**.
46. No campo **Registro**, insira ou selecione um valor.
47. No campo **Lançar valor**, selecione 'Ajustes de depreciação (anos anteriores)'.
48. No campo **Conta principal**, especifique os valores desejados.
49. No campo **Contrapartida**, especifique os valores desejados.
50. Clique em **Adicionar**.
51. No campo **Registro**, insira ou selecione um valor.
52. No campo **Lançar valor**, selecione 'Ajustes de depreciação (este ano)'.
53. No campo **Conta principal**, especifique os valores desejados.
54. No campo **Contrapartida**, especifique os valores desejados.
55. Clique em **Adicionar**.
56. No campo **Registro**, insira ou selecione um valor.
57. No campo **Lançar valor**, selecione o 'Valor líquido contábil'.
58. No campo **Conta principal**, especifique os valores desejados.
59. No campo **Contrapartida**, especifique os valores desejados.
60. No campo **Venda ou sucata**, selecione 'Sucata'.
61. Clique em **Adicionar**.
62. No campo **Registro**, insira ou selecione um valor.
63. No campo **Lançar valor**, selecione 'Valor de aquisição'.
64. No campo **Conta principal**, especifique os valores desejados.
65. No campo **Contrapartida**, especifique os valores desejados.
66. Clique em **Adicionar**.
67. No campo **Registro**, insira ou selecione um valor.
67. No campo **Lançar valor**, selecione 'Depreciação (anos anteriores)'.  
68. No campo **Conta principal**, especifique os valores desejados.
69. No campo **Contrapartida**, especifique os valores desejados.
70. Clique em **Adicionar**.
71. No campo **Registro**, insira ou selecione um valor.
72. No campo **Lançar valor**, selecione 'Depreciação (este ano)'.
73. No campo **Conta principal**, especifique os valores desejados.
74. No campo **Contrapartida**, especifique os valores desejados.
75. Clique em **Adicionar**.
76. No campo **Registro**, insira ou selecione um valor.
77. No campo **Lançar valor**, selecione 'Ajustes de depreciação (anos anteriores)'.
78. No campo **Conta principal**, especifique os valores desejados.
79. No campo **Contrapartida**, especifique os valores desejados.
80. Clique em **Adicionar**.
81. No campo **Registro**, insira ou selecione um valor.
82. No campo **Lançar valor**, selecione 'Ajustes de depreciação (este ano)'.
83. No campo **Conta principal**, especifique os valores desejados.
84. No campo **Contrapartida**, especifique os valores desejados.
85. Clique em **Adicionar**.
86. No campo **Registro**, insira ou selecione um valor.
87. No campo **Lançar valor**, selecione o 'Valor líquido contábil'.
88. No campo **Conta principal**, especifique os valores desejados.
89. No campo **Contrapartida**, especifique os valores desejados.

