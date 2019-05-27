---
title: Criar uma célula de trabalho subcontratada para lean manufacturing
description: Para modelar trabalho subcontratado para o lean manufacturing, você deve criar uma célula de trabalho associada ao fornecedor que fornece o trabalho.
author: cvocph
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
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58b725af456f1a5c7f158f01ffe48a2d8cdf056b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550528"
---
# <a name="create-a-subcontracted-work-cell-for-lean-manufacturing"></a>Criar uma célula de trabalho subcontratada para lean manufacturing

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para modelar trabalho subcontratado para o lean manufacturing, você deve criar uma célula de trabalho associada ao fornecedor que fornece o trabalho. Uma célula de trabalho subcontratada é vinculada ao fornecedor por meio da associação de um recurso do tipo de fornecedor. Se fizer o registro na empresa de demonstração USMF, selecione o ID da conta do fornecedor 1002 e o site 1.


## <a name="create-a-vendor-resource"></a>Crie um recurso de fornecedor
1. Vá para Recursos.
2. Clique em Novo.
3. No campo Recurso, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo, selecione 'Fornecedor'.
6. No campo Fornecedor, clique no botão suspenso para abrir a pesquisa.

## <a name="create-the-resource-group"></a>Crie o grupo de recursos
1. Ir para grupos de Recurso.
2. Clique em Novo.
3. No campo grupo de Recurso, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Local, clique no botão suspenso para abrir a pesquisa.
    * Selecione o local ao qual a célula de trabalho deve ser atribuída. Em tese, um local pode representar um único local que é operado por um fornecedor. Entretanto, na maioria dos casos, os recursos subcontratados são alocados apenas ao local que solicita o trabalho subcontratado. Observe que os depósitos de entrada e saída das células de trabalho subcontratadas devem estar no mesmo local.  
6. No campo Local, digite um valor.
7. @SysTaskRecorder:_RequestClose
8. Marque ou desmarque a caixa de seleção Célula de trabalho.
9. No campo Depósito de entrada, clique no botão suspenso para abrir a pesquisa.
    * Selecione o depósito e o local usados para preparar o material para a célula de trabalho gerenciada pelo fornecedor. Em muitos casos, depósito e a localização são modelados usando um depósito separado por fornecedor e uma localização por célula de trabalho.  
10. No campo Localização de entrada, clique no botão suspenso para abrir a pesquisa.
11. No campo Depósito de saída, clique no botão suspenso para abrir a pesquisa.
    * Defina o depósito e a localização onde o material será lançado quando as atividades subcontratadas da célula de trabalho forem lançadas. O depósito e a localização podem ser no local do fornecedor, se o fornecedor reportar os trabalhos kanban. Se preferir, o depósito e o local podem ser o local de recebimento associado à próxima etapa do fluxo de produção.  
12. No campo Localização de saída, clique no botão suspenso para abrir a pesquisa.
13. Expanda ou recolha a seção Calendários.
14. Clique em Adicionar.
15. No campo Calendário, clique no botão suspenso para abrir a pesquisa.
    * Associe o calendário de produção da célula de trabalho ao grupo de recursos. Para recursos críticos, recomendamos que você defina os calendários específicos que representam os horários de trabalho exatos as habilidades relacionadas à célula de trabalho e ao site de fornecedor.  
16. Expanda ou recolha a seção Recursos.
17. Clique em Adicionar.
    * Um grupo de recursos subcontratado deve ter o recurso associado do tipo fornecedor que vincula o grupo de recursos à conta do fornecedor.  
18. No campo Recurso, clique no botão suspenso para abrir a pesquisa.
    * Selecione ou insira o recurso do fornecedor que você acabou de criar na subtarefa anterior.  
19. Expanda ou recolha a seção Capacidade de célula de trabalho.
20. Clique em Adicionar.
    * Uma célula de trabalho deve ter uma capacidade definida. Neste exemplo, criamos capacidade de produtividade de 100 peças por dia útil padrão.  
21. No campo Modelo de fluxo de produção, clique no botão suspenso para abrir a pesquisa.
22. No campo Período de capacidade, selecione uma opção.
23. No campo Quantidade de produtividade média, insira um número.
24. No campo Unidade, clique no botão suspenso para abrir a pesquisa.
25. Resolver altera a Unidade.

