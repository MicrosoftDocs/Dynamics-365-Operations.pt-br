---
title: Criar uma entrada de diário usando modelo
description: Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a3fb750e04fb134fc9ac38d9a47201803566113
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846622"
---
# <a name="create-a-journal-entry-using-template"></a>Criar uma entrada de diário usando modelo

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

