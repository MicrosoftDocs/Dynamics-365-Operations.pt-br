--- 
title: "Definir células de trabalho de lean manufacturing"
description: "Uma célula de trabalho é um formulário específico dos grupos de recursos que podem ser usados em atividades do processo de lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: dc9793bd59e59c96532549d73c56bad518fa7394
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="define-lean-manufacturing-work-cells"></a>Definir células de trabalho de lean manufacturing

[!include[task guide banner](../../includes/task-guide-banner.md)]

Uma célula de trabalho é um formulário específico dos grupos de recursos que podem ser usados em atividades do processo de lean manufacturing. As células de trabalho têm locais de entrada e de saída e uma definição de capacidade com base em um modelo de fluxo de produção. Para saber mais sobre os conceitos básicos células de trabalho de lean manufacturing e dos cálculos de capacidade, consulte os white papers sobre Lean manufacturing. A empresa de dados de demonstração usada para criar este procedimento é USMF.


## <a name="create-a-work-cell"></a>Crie uma célula de trabalho. 
1. Vá para Administração da organização > Recursos > Grupos de recursos.
2. Clique em Novo.
3. No campo grupo de Recurso, digite um valor.
    * A ID da célula de trabalho normalmente é um código sistemático e deve ser exclusivo da entidade legal.  
4. No campo Descrição, digite um valor.
    * A descrição contém o nome ou título da célula de trabalho.  
5. No campo Local, clique no botão suspenso para abrir a pesquisa.
    * Uma célula de trabalho está localizada em um site específico. Depósito de entrada e saída e local devem ser localizados neste site.  
6. Na lista, clique no link na linha selecionada.
7. No campo Unidade de produção, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
    * Selecione uma unidade de produção à qual a célula de trabalho pertence.  
9. Marque a caixa de seleção Célula de trabalho.
    * Para usar um grupo de recursos como uma célula de trabalho de lean manufacturing, a caixa de seleção Célula de trabalho deve ser selecionada.  Observe que essa propriedade não poderá ser alterada depois que o grupo de recursos for criado.  
10. No campo Depósito de entrada, clique no botão suspenso para abrir a pesquisa.
11. Na lista, clique no link na linha selecionada.
    * Para contabilidade e controle de material, o material preparado no chão de fábrica normalmente é alocado em um depósito virtual específico. No entanto, se desejar reabastecer os locais usando o trabalho de depósito, eles devem ser parte do depósito receptivo de matéria-prima.  
12. No campo Localização de entrada, clique no botão suspenso para abrir a pesquisa.
13. Na lista, clique no link na linha selecionada.
    * Observe que para uma atividade do processo, o local de entrada pode ser substituído, geralmente, por um produto específico ou por uma variante do produto, definindo atividades de separação que alimentam a atividade do processo. Os locais de entrada de uma célula de trabalho não podem ser controlados por placa de licença.  
14. No campo Depósito de saída, clique no botão suspenso para abrir a pesquisa.
15. Na lista, localize e selecione o PDV desejado.
    * Em vários fluxos de produção da atividade ou nas linhas de produção, normalmente este é o depósito de entrada da próxima célula de trabalho ou do depósito de vendas ou em trânsito no qual um produto, geralmente é transferido após o processo de produção. Lembre-se que ao modelar processos de lean manufacturing, o transporte geralmente é de resíduos, pois está reportando transporte.  
16. Na lista, clique no link na linha selecionada.
17. No campo Localização de saída, clique no botão suspenso para abrir a pesquisa.
    * Em um fluxo de produção com várias atividades do processo, geralmente é a localização de entrada da próxima célula de trabalho.  
18. Na lista, localize e selecione o PDV desejado.
19. Na lista, clique no link na linha selecionada.
20. Expanda ou recolha a seção Operação.
    * Uma categoria de tempo de execução deve ser fornecida para habilitar o cálculo do custo e o processamento de trabalhos kanban de lean manufacturing.  
21. No campo Categoria do tempo de execução, clique no botão suspenso para abrir a pesquisa.
22. Na lista, localize e selecione o PDV desejado.
    * A categoria de custo do tempo de execução é usada no cálculo de custo padrão e custos de fluxo inverso.  
23. Na lista, clique no link na linha selecionada.
24. Expanda ou recolha a seção Calendários.
25. Clique em Adicionar.
26. No campo Calendário, clique no botão suspenso para abrir a pesquisa.
27. Na lista, localize e selecione o PDV desejado.
    * Normalmente células de trabalho de um determinado site usam o mesmo calendário de trabalho. Se as células de trabalho puderem ter horários de trabalho individuais, pode ser necessário criar um calendário de horas úteis específico para a célula de trabalho. Observe que o calendário deve ter um horário de trabalho padrão definido quando usado para uma célula de trabalho de lean manufacturing, porque a definição da capacidade geralmente está relacionada ao horário de trabalho padrão de um dia de trabalho.  
28. Na lista, clique no link na linha selecionada.
29. Expanda ou recolha a seção Capacidade de célula de trabalho.
30. Clique em Adicionar.
31. No campo Modelo de fluxo de produção, clique no botão suspenso para abrir a pesquisa.
32. Na lista, localize e selecione o PDV desejado.
    * Este procedimentos exige o tipo de modelo do fluxo de produção Produtividade, para mostrar a definição da capacidade de produtividade.  
33. Na lista, clique no link na linha selecionada.
34. No campo Período de capacidade, selecione uma opção.
    * As opções incluem: Dia útil padrão - a capacidade é expressa pela duração do dia útil padrão do calendário de horas úteis para a célula de trabalho. Para cada dia, o horário de trabalho real é determinado a partir do calendário e a capacidade disponível em vigor é calculada com base nisso.   Semana - Permite uma capacidade semanal. Não há nenhum ajuste feito no horário de trabalho real.   Mês - Permite uma capacidade mensal. Não há nenhum ajuste feito na capacidade real.   Normalmente, o dia útil padrão é usado para períodos diários e capacidade semanal é usada para períodos semanais de capacidade.  
35. No campo Quantidade de produtividade média, insira um número.
    * Observe que uma operação de lean manufacturing nunca está configurada para a capacidade máxima possível em um ambiente ideal. Em vez disso, a capacidade sempre deve ser definida para operações que executam sob condições normais.  
36. No campo Unidade, clique no botão suspenso para abrir a pesquisa.
37. Na lista, clique no link na linha selecionada.
38. Resolver altera a Unidade.

## <a name="add-a-financial-dimension"></a>Adicione uma dimensão financeira
1. Expanda ou recolha a seção Dimensões financeiras.
    * Observe que as dimensões financeiras definidas no fluxo de produção substituem a dimensão financeira de uma célula de trabalho específica.    As dimensões financeiras que podem ser selecionadas dependem da configuração de dimensões financeiras do sistema. As etapas a seguir correspondem ao conjunto de dados de demonstração na empresa USMF. Ao usar diferentes dados, as etapas não podem ser aplicáveis.  
2. No campo Centro de Custo, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o PDV desejado.
    * As dimensões que precisam ser selecionadas em células de trabalho de lean manufacturing dependem da implementação de dimensões financeiras no módulo de contabilidade para uma entidade legal específica.  
4. Na lista, clique no link na linha selecionada.
5. No campo Grupo de Item, clique no botão suspenso para abrir a pesquisa.
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.

## <a name="save"></a>Salvar
1. Clique em Salvar.


