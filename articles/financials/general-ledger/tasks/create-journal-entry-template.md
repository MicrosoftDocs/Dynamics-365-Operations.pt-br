--- 
title: "Criar uma entrada de diário usando um modelo"
description: "Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário."
author: aprilolson
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6567bc969d003abc9fcf21886cc202cc85db6a14
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-journal-entry-using-a-template"></a>Criar uma entrada de diário usando um modelo

[!include[task guide banner](../../includes/task-guide-banner.md)]

Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário. Este procedimento usa a empresa de dados de demonstração USMF.

1. Contabilidade > Entradas de diários > Diários gerais. Clique em Novo.
    * Este procedimento começa criando e lançando um comprovante de diário, mas qualquer comprovante de diário lançado anteriormente pode ser salvo como um modelo.  
2. No campo Nome, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. Clique em Linhas.
6. Insira uma conta para o Tipo de conta.
7. No campo Descrição, digite um valor.
8. Insira um valor no campo Débito.
9. Clique em Novo.
10. Insira uma conta diferente para o Tipo de conta.
11. No campo Descrição, digite um valor.
12. Insira um valor no campo Débito.
13. Clique em Novo.
14. No campo Conta, especifique os valores desejados.
15. No campo Descrição, digite um valor.
16. Insira um valor no campo de crédito para verificar o comprovante.
17. Clique em Lançar.
18. Clique em Funções.
19. Clique em Salvar o modelo de comprovante.
20. Este procedimento pressupõe um tipo de modelo percentual. Clique em OK.
    * • Porcentagem: Os valores do comprovante são convertidos em fatores de porcentagem, que permitem que qualquer valor seja aplicado quando o modelo de comprovante for selecionado.  • Valor: Os valores reais serão armazenados e serão aplicados.  
21. Clique em Diários gerais.
22. Clique em Novo.
23. No campo Nome, clique no botão suspenso para abrir a pesquisa.
24. Na lista, clique no link na linha selecionada.
25. Clique em Linhas.
26. Clique em Funções.
27. Clique em Selecionar modelo de comprovante.
28. Encontre o modelo criado anteriormente. Clique em OK.
    * Talvez você precise clicar na etapa anterior e selecionar o modelo correto se outros modelos existirem.  
29. No campo Valor, insira o valor a ser aplicado ao comprovante.
    * O campo Valor é apenas exibido se o modelo de comprovante for do tipo Porcentagem.  
30. Clique em OK.


