---
title: Criar uma entrada de diário usando modelo
description: Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3843c165b3fc3030a937ec47a1439b1c1b36206d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216488"
---
# <a name="create-a-journal-entry-using-template"></a>Criar uma entrada de diário usando modelo

[!include [banner](../../includes/banner.md)]

Os comprovantes de diário lançados podem ser salvos como modelos de comprovante e ser aplicados em um novo comprovante de diário. Este procedimento usa a empresa de dados de demonstração USMF.

1. Vá até **Painel de Navegação > Módulos > Contabilidade > Entradas de diário > Diários gerais**.
2. No **Painel de Ações**, clique em **Novo**. Este procedimento começa criando e lançando um comprovante de diário, mas qualquer comprovante de diário lançado anteriormente pode ser salvo como um modelo.  
3. No campo **Nome**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. Clique em **Linhas**.
7. No campo **Tipo de conta**, insira um valor.
8. No campo **Descrição**, digite um valor.
9. No campo **Débito**, digite um valor.
10. Clique em **Novo**.
11. No campo **Tipo de conta**, insira um valor.
12. No campo **Descrição**, digite um valor.
13. No campo **Débito**, digite um valor.
14. Clique em **Novo**.
14. No campo **Conta**, especifique os valores desejados.
15. No campo **Descrição**, digite um valor.
16. No campo **Crédito**, digite um valor para verificar o comprovante.
17. No **Painel de Ações**, clique em **Lançar**.
18. Clique em **Funções**.
19. Clique no modelo **Salvar comprovante**.
20. Este procedimento pressupõe um tipo **Modelo percentual**. Clique em OK.
    - Porcentagem: os valores do comprovante são convertidos em fatores de porcentagem, que permitem que qualquer valor seja aplicado quando o modelo de comprovante é selecionado.
    - Valor: os valores reais serão armazenados e serão aplicados.  
21. Clique em **Diários gerais**.
22. Clique em **Novo**.
23. No campo **Nome**, clique no botão suspenso para abrir a pesquisa.
24. Na lista, clique no link na linha selecionada.
25. Clique em **Linhas**.
26. Clique em **Funções**.
27. Clique em **Selecionar modelo de comprovante**.
28. Encontre o modelo criado anteriormente. Clique em **OK**. Talvez você precise clicar em **Etapa anterior** e selecionar o modelo correto se outros modelos existirem.  
29. No campo **Valor**, insira o valor a ser aplicado ao comprovante. O campo **Valor** é apenas exibido se o modelo de comprovante for do tipo Porcentagem.  
30. Clique em **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]