--- 
title: "Começar uma ordem de produção"
description: "Esse procedimento mostra como iniciar uma ordem de produção no chão de fábrica."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33558053d33d9fe4a2ecb3576da569b2c441db80
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="start-a-production-order"></a>Começar uma ordem de produção

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esse procedimento mostra como iniciar uma ordem de produção no chão de fábrica. Consumo de materiais e tempo são relatados nesse processo. A empresa de dados demo usada para criar este procedimento é USMF. Este é o quinto procedimento de sete que explica o ciclo de vida da ordem de produção.


## <a name="start-a-production-order"></a>Começar uma ordem de produção
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
    * Selecione uma ordem de produção com o status Liberada.  
2. No Painel de Ação, clique em Ordem de produção.
3. Clique em Iniciar.
    * Nesta página, você pode confirmar o início da ordem de produção.  
4. Clique na guia Geral.
5. No campo Da Oper. Não. , insira '10'.
6. No campo Consumo automático de roteiro, selecione 'Sempre'.
7. Clique na caixa de seleção Lançar cartão de roteiro agora.
8. No campo Consumo automático de BOM, selecione 'Sempre'.
9. Clique na caixa de seleção Lançar lista de separação agora.
10. Clique na caixa de seleção Imprimir lista de separação.
11. Clique em OK.
    * Esta é a lista de separação impressa que mostra os materiais usados na ordem de produção.  
12. Feche a página.

## <a name="validate-the-picking-list"></a>Validar a lista de separação
1. No Painel de Ação, clique em Exibir.
2. Clique em Lista de separação.
3. Na lista, localize e selecione o PDV desejado.
4. Na lista, clique no link na linha selecionada.
5. Clique em Editar.
6. No campo Consumo, insira um número.
7. Clique em Lançar.
8. Clique em OK.
    * No diário da lista de separação, os materiais consumidos pela ordem de produção são lançados. Antes de lançar o diário, você pode fazer ajustes se houver uma diferença entre a quantidade prevista e a quantidade realmente consumida.  
9. Clique na guia GridPanel.
10. Feche a página.

## <a name="verify-the-route-card-journal"></a>Verificar o diário de cartão de roteiro
1. No Painel de Ação, clique em Exibir.
2. Clique em Cartão de roteiro.
3. Na lista, localize e selecione o PDV desejado.
4. Na lista, clique no link na linha selecionada.
5. Clique em Editar.
6. No campo Horas, insira um número.
7. Clique em Lançar.
8. Clique em OK.
    * No diário de cartão de roteiro, é registrado o tempo gasto em operações individuais. A quantidade de erros e acertos também pode ser informada.  


