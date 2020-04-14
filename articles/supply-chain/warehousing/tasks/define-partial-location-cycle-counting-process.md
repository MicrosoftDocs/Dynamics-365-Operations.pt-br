---
title: 'Definir processo de contagem cíclica de localização parcial '
description: Quando você usa planos de contagem cíclica para criar trabalhos de contagem, você pode orientar operações de contagem real solicitando que somente os produtos e as grades do produto foram contados específicos, em vez de todo estoque disponível no local.
author: ShylaThompson
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67f719d5990a4331559cab34412bf82f15eca735
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148345"
---
# <a name="define-partial-location-cycle-counting-process"></a>Definir processo de contagem cíclica de localização parcial  

[!include [banner](../../includes/banner.md)]

Quando você usa planos de contagem cíclica para criar trabalhos de contagem, você pode orientar operações de contagem real solicitando que somente os produtos e as grades do produto foram contados específicos, em vez de todo estoque disponível no local. Ao filtrar produtos específicos, o gerente do depósito pode reduzir custos indiretos de revisão, ajudar a evitar erros de consolidação e economizar tempo. Geralmente, um gerente de depósito executa as tarefas de configuração. Você pode ver todo esse procedimento na empresa de dados de demonstração USMF ou em seus próprios dados.


## <a name="create-a-cycle-counting-work-template"></a>Criar um modelo de trabalho de contagem cíclica
1. Vá para Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho.
2. No campo Tipo de ordem de trabalho, selecione "Contagem cíclica".
3. Clique em Novo.
4. No campo de número de sequência, insira um número.
    * A ordem de classificação é do número menor para o número maior. O valor deve ser maior que 0 (zero).  
5. Na lista, marque a linha selecionada.
6. No campo Modelo de trabalho, digite um valor.
7. No campo Descrição do modelo do trabalho, digite um valor.
8. No campo ID do grupo de trabalho, insira ou selecione um valor.
9. No campo Prioridade de trabalho, insira um número.
10. Clique em Salvar.
11. Clique em Novo.
12. Na lista, marque a linha selecionada.
13. No campo Tipo de trabalho, selecione 'Contagem'.
14. No campo ID de classe de trabalho, insira ou selecione um valor.
15. Clique em Salvar.
16. Clique em Divisões de linha de trabalho.
17. Clique em Novo.
18. No campo de número de sequência, insira um número.
    * A ordem de classificação é do número menor para o número maior. O valor deve ser maior que 0 (zero).  
19. Clique em Salvar.
20. Feche a página.
21. Feche a página.

## <a name="create-a-cycle-counting-plan"></a>Criar um plano de contagem cíclica
1. Vá para Gerenciamento de depósito > Configuração > Contagem cíclica > Planos de contagem cíclica.
2. Clique em Novo.
3. No campo ID do plano de contagem cíclica, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Número máximo de contagens cíclicas, insira um número.
6. No campo Modelo de trabalho, insira ou selecione um valor.
7. Clique em Novo.
8. No campo de número de sequência, insira um número.
    * A ordem de classificação é do número menor para o número maior. O valor deve ser maior que 0 (zero).  
9. No campo Descrição, digite um valor.
10. Clique em Salvar.
11. Clique em Definir consulta de produto.
12. Na lista, marque a linha selecionada.
13. No campo Critérios, insira ou selecione um valor.
14. Clique em OK.
15. Feche a página.

