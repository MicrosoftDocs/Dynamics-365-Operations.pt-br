---
title: Configurar grades de remuneração
description: As grades de remuneração são usadas para definir e manter as estruturas de pagamento para os planos de remuneração fixa.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9592c993cb1d1d392c5cd349663325d326d821521ca7042ba593d74e8f3b5d2f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732456"
---
# <a name="set-up-compensation-grids"></a>Configurar grades de remuneração

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

As grades de remuneração são usadas para definir e manter as estruturas de pagamento para os planos de remuneração fixa. As grades de remuneração poderão ser compartilhadas entre vários planos ou copiadas ao criar um novo plano de remuneração.  Antes de criar uma grade de compensação, os níveis do pontos de Referência devem ser configurados. Este exemplo criará um novo tipo de Classificação da grade de remuneração com dados de demonstração para os níveis e os pontos de Referência. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="set-up-information-about-the-compensation-grid"></a>Configurar informações sobre a grade de remuneração
1. Acesse Recursos humanos > Remuneração > Remuneração > Grades de remuneração.
2. Clique em Novo.
3. No campo Grade, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo, selecione uma opção.
6. No campo Configuração referência, insira ou selecione um valor.
7. No campo Moeda, insira ou selecione um valor.
8. No campo Moeda, digite um valor.
9. No campo Data efetiva, insira uma data.

## <a name="add-levels-to-the-compensation-structure"></a>Adicionar níveis à estrutura de remuneração
1. Clique em Estrutura de remuneração.
2. Na lista, marque a linha selecionada.
3. No campo Nível, insira ou selecione um valor.
4. Clique em Novo.
5. Na lista, marque a linha selecionada.
6. No campo Nível, insira ou selecione um valor.
7. Clique em Novo.
8. Na lista, marque a linha selecionada.
9. No campo Nível, insira ou selecione um valor.
10. Clique em Novo.
11. Na lista, marque a linha selecionada.
12. No campo Nível, insira ou selecione um valor.
13. Clique em Novo.
14. Na lista, marque a linha selecionada.
15. No campo Nível, insira ou selecione um valor.

## <a name="fill-in-the-compensation-structure-with-values"></a>Preencha a estrutura de remuneração com valores
1. Na lista, marque a linha selecionada.
    * Nesse ponto, os valores de remuneração poderão ser inseridos manualmente em todos os campos na tabela, ou a funcionalidade Alteração em massa poderá ser usada para preencher facilmente vários campos e para executar cálculos básicos.  
2. Clique em Alteração em massa.
    * Para essa grade, aplicaremos primeiro o valor do ponto médio do primeiro nível a todos os campos da tabela. Essa será a base para a matriz de remuneração.  
3. No campo Tipo de Ajuste, selecione uma opção.
4. No campo Valor do ajuste, insira um número.
5. Na lista, marque ou desmarque todas as linhas.
6. Clique em Aplicar à grade.
    * Agora usaremos a função de alteração em massa para incrementar os valores em cada nível subsequente por uma determinada porcentagem ou valor. Neste exemplo, cada classificação terá 12,5% difundido entre os valores médios.  
7. No campo Tipo de Ajuste, selecione uma opção.
8. No campo Valor do ajuste, insira um número.
9. Na lista, localize e selecione o registro desejado.
10. Na lista, localize e selecione o registro desejado.
11. Na lista, localize e selecione o registro desejado.
12. Na lista, localize e selecione o registro desejado.
13. Clique em Aplicar à grade.
14. Na lista, localize e selecione o registro desejado.
15. Na lista, localize e selecione o registro desejado.
16. Na lista, localize e selecione o registro desejado.
17. Clique em Aplicar à grade.
18. Na lista, localize e selecione o registro desejado.
19. Na lista, localize e selecione o registro desejado.
20. Clique em Aplicar à grade.
21. Na lista, localize e selecione o PDV desejado.
22. Clique em Aplicar à grade.
    * Agora usaremos a função de alteração em massa para ajustar os pontos de referência Mínimo e Máximo para cada nível. Este exemplo usará 50% difundido, dessa forma, o ponto de referência Mínimo será ajustado para -20% o Máximo será ajustado para +20%.  
23. No campo Valor do ajuste, insira um número.
24. No campo Ponto de referência, insira ou selecione um valor.
25. Na lista, marque ou desmarque todas as linhas.
26. Clique em Aplicar à grade.
27. No campo Valor do ajuste, insira um número.
28. No campo Ponto de referência, insira ou selecione um valor.
29. Na lista, marque ou desmarque todas as linhas.
30. Clique em Aplicar à grade.



[!INCLUDE[footer-include](../includes/footer-banner.md)]