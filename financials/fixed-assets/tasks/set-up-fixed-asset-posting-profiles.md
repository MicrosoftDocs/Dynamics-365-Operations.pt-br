--- 
title: "Configurar perfis de lançamento de ativos fixos"
description: "Este guia de tarefa definirá os perfis de postagem de ativo fixo."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f2fd3c8cfa63e11a0bf4e5e095375d024c9d45ce
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-fixed-asset-posting-profiles"></a>Configurar perfis de lançamento de ativos fixos

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este guia de tarefa definirá os perfis de postagem de ativo fixo.  Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.  Os exemplos dados no guia da tarefa são para um perfil de lançamentos básicos, embora os perfis de lançamento devam ser criados para seus requisitos do plano de contas e específico de relatórios financeiros.

1. Vá para Ativos fixos > Configuração > Perfis de postagem de ativo fixo.
2. Clique em Novo.
3. No campo de perfil de lançamento, insira um valor.
4. No campo Descrição, digite um valor.
    * Será necessário criar um perfil de lançamento para cada tipo de transação de ativo fixo que você utilizará ao trabalhar com ativos fixos.  Esta guia será iniciada com tarefas com o tipo de transação de aquisição.  
5. Clique em Adicionar.
6. No campo Livro, insira ou selecione um valor.
    * O campo de agrupamentos permite que você defina o perfil de lançamentos para baixo na tabela (uma configuração de conta para cada ativo fixo) ou ao grupo (uma conta configurada para cada grupo de ativos fixos).  Para este guia de tarefa deixarei o conjunto de valores “Tudo“ a ser aplicado a todos os ativos fixos com o registro especificado.  
7. No campo Conta principal, especifique os valores desejados.
    * Para aquisições, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.    
8. No campo Tipo de transação, selecione o 'Ajuste de aquisição'.
    * Para transações de ajuste de aquisição, usaremos as mesmas contas usadas para transações de aquisição.  
9. Clique em Adicionar.
10. No campo Livro, insira ou selecione um valor.
11. No campo Conta principal, especifique os valores desejados.
    * Para ajustes de aquisições, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.    
12. No Tipo de transação, selecione 'Depreciação'.
13. Clique em Adicionar.
14. No campo Livro, insira ou selecione um valor.
15. No campo Conta principal, especifique os valores desejados.
16. No campo Contrapartida, especifique os valores desejados.
17. No campo Tipo de transação, selecione 'Ajuste de depreciação'.
    * Para transações de ajuste de depreciação, usaremos as mesmas contas usadas para transações de depreciação.  
18. Clique em Adicionar.
19. No campo Livro, insira ou selecione um valor.
20. No campo Conta principal, especifique os valores desejados.
21. No campo Contrapartida, especifique os valores desejados.
22. No campo Tipo de transação, selecione 'Descarte - venda'.
23. Clique em Adicionar.
24. No campo Livro, insira ou selecione um valor.
25. No campo Conta principal, especifique os valores desejados.
    * Para Descartes, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.  
26. No campo Tipo de transação, selecione 'Descarte - sucata'.
    * Usaremos as mesmas contas para Descarte e Descarte de sucata.  
27. Clique em Adicionar.
28. No campo Livro, insira ou selecione um valor.
29. No campo Conta principal, especifique os valores desejados.
    * Para Descartes, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.  
30. Expanda a seção Alienação.
    * Você deve configurar perfis de lançamentos de eliminação para venda e sucata.  Começaremos com transações de venda de eliminação.  
31. Clique em Adicionar.
32. No campo Livro, insira ou selecione um valor.
33. No campo Postar valor de lançamentos, selecione o 'Valor de aquisição'.
    * O valor de aquisição endereçará valores de aquisição e de ajuste de aquisição para todos os anos.  Você também pode definir contas para esses tipos de transação separadamente.  
    * Você pode definir o processo de eliminação para usar contas diferentes dependendo dos resultados de descarte em um ganho ou perda.  Definirei o tipo de valor de venda 'Tudo” para usar as mesmas contas para todos os tipos de descarte.  
34. No campo Conta principal, especifique os valores desejados.
35. No campo Contrapartida, especifique os valores desejados.
36. Clique em Adicionar.
37. No campo Livro, insira ou selecione um valor.
    * No campo Valor de lançamentos, selecione 'Depreciação (anos anteriores)'.  
38. No campo Conta principal, especifique os valores desejados.
39. No campo Contrapartida, especifique os valores desejados.
40. Clique em Adicionar.
41. No campo Livro, insira ou selecione um valor.
42. No campo Valor de lançamentos, selecione 'Depreciação (este ano)'.
43. No campo Conta principal, especifique os valores desejados.
44. No campo Contrapartida, especifique os valores desejados.
45. Clique em Adicionar.
46. No campo Livro, insira ou selecione um valor.
47. No campo Valor de lançamentos, selecione 'Ajustes de depreciação (anos anteriores)'.
48. No campo Conta principal, especifique os valores desejados.
49. No campo Contrapartida, especifique os valores desejados.
50. Clique em Adicionar.
51. No campo Livro, insira ou selecione um valor.
52. No campo Valor de lançamentos, selecione 'Ajustes de depreciação (este ano)'.
53. No campo Conta principal, especifique os valores desejados.
54. No campo Contrapartida, especifique os valores desejados.
55. Clique em Adicionar.
56. No campo Livro, insira ou selecione um valor.
57. No campo Postar valor de lançamentos, selecione o 'Valor líquido contábil'.
58. No campo Conta principal, especifique os valores desejados.
59. No campo Contrapartida, especifique os valores desejados.
60. Na venda ou no campo de sucata, selecione o tópico 'Sucata'.
61. Clique em Adicionar.
62. No campo Livro, insira ou selecione um valor.
63. No campo Postar valor de lançamentos, selecione o 'Valor de aquisição'.
64. No campo Conta principal, especifique os valores desejados.
65. No campo Contrapartida, especifique os valores desejados.
66. Clique em Adicionar.
67. No campo Livro, insira ou selecione um valor.
    * No campo Valor de lançamentos, selecione 'Depreciação (anos anteriores)'.  
68. No campo Conta principal, especifique os valores desejados.
69. No campo Contrapartida, especifique os valores desejados.
70. Clique em Adicionar.
71. No campo Livro, insira ou selecione um valor.
72. No campo Valor de lançamentos, selecione 'Depreciação (este ano)'.
73. No campo Conta principal, especifique os valores desejados.
74. No campo Contrapartida, especifique os valores desejados.
75. Clique em Adicionar.
76. No campo Livro, insira ou selecione um valor.
77. No campo Valor de lançamentos, selecione 'Ajustes de depreciação (anos anteriores)'.
78. No campo Conta principal, especifique os valores desejados.
79. No campo Contrapartida, especifique os valores desejados.
80. Clique em Adicionar.
81. No campo Livro, insira ou selecione um valor.
82. No campo Valor de lançamentos, selecione 'Ajustes de depreciação (este ano)'.
83. No campo Conta principal, especifique os valores desejados.
84. No campo Contrapartida, especifique os valores desejados.
85. Clique em Adicionar.
86. No campo Livro, insira ou selecione um valor.
87. No campo Postar valor de lançamentos, selecione o 'Valor líquido contábil'.
88. No campo Conta principal, especifique os valores desejados.
89. No campo Contrapartida, especifique os valores desejados.


