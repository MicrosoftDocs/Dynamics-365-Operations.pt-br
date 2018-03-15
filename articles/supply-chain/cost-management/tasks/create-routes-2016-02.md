--- 
title: Criar roteiros (apenas fevereiro de 2016)
description: "Esta tarefa se concentra na criação dos roteiros de produção para produtos finalizados e semifinalizados."
author: BibiSp
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a1c4b7623f3409d4474adcd04fb1331b944b9fbb
ms.openlocfilehash: a1da6a38e9e70efdbbd04e85318f208c82ab39ed
ms.contentlocale: pt-br
ms.lasthandoff: 02/13/2018

---
# <a name="create-routes-february-2016-only"></a>Criar roteiros (apenas fevereiro de 2016)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta tarefa se concentra na criação dos roteiros de produção para produtos finalizados e semifinalizados. Trata-se da quinta tarefa na série de cálculo BOM. A empresa de dados demo usada para criar esta tarefa é USMF.


## <a name="create-a-route-for-a-semi-finished-product"></a>Criar um roteiro para um produto semifinalizado
1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Na lista, clique no link na linha selecionada.
    * Selecione o número de item BOM_2.  
3. No Painel de Ação, clique em Engenharia.
4. Clique em Rota.
5. Clique em Novo.
6. Clique em Roteiro e versão de roteiro.
7. No campo Descrição, digite um valor.
    * Por exemplo, digite ROUTE_2.  
8. No campo Local, insira ou selecione um valor.
    * Neste exemplo, insira ou selecione Site 1.  
9. Clique em OK.
10. Clique em Novo.
11. No campo Operação, insira ou selecione um valor.
    * Neste exemplo, selecione Montagem.  
12. No campo Tempo de execução, insira um número.
    * Por exemplo, digite 1. O tempo de execução geralmente faz parte do preço que é calculado para um item.  
13. No campo Grupo de roteiro, insira ou selecione um valor.
    * Neste exemplo, selecione Std.  
14. Clique na guia Configuração.
15. No campo categoria de Configuração, insira ou selecione um valor.
    * Neste exemplo, selecione Montagem.  
16. Clique na guia Horas.
17. No campo Tempo de preparação, insira um número.
    * Neste exemplo, digite 1. O tempo de preparação geralmente faz parte do preço que é calculado para um item.  
18. No Painel de Ação, clique em Versão de roteiro.
19. Clique em Aprovar.
20. Selecione Sim em Também deseja aprovar o roteiro? .
21. Clique em OK.
22. No Painel de Ação, clique em Versão de roteiro.
23. Clique em Ativar.
24. Feche a página.
25. Feche a página.

## <a name="create-a-route-for-a-finished-product"></a>Criar um roteiro para um produto finalizado
1. Na lista, clique no link na linha selecionada.
    * Selecione o número do item BOM_1.  
2. No Painel de Ação, clique em Engenharia.
3. Clique em Rota.
4. Clique em Novo.
5. Clique em Roteiro e versão de roteiro.
6. No campo Descrição, digite um valor.
    * Neste exemplo, digite ROUTE_1.  
7. No campo Local, insira ou selecione um valor.
    * Neste exemplo, insira ou selecione Site 1.  
8. Clique em OK.
9. Clique em Novo.
10. No campo Operação, insira ou selecione um valor.
    * Neste exemplo, selecione Embalagem.  
11. No campo Tempo de execução, insira um número.
    * Neste exemplo, digite 1.  
12. No campo Grupo de roteiro, insira ou selecione um valor.
    * Neste exemplo, selecione Std.  
13. Clique na guia Configuração.
14. No campo categoria de Configuração, insira ou selecione um valor.
    * Neste exemplo, selecione Embalagem.  
15. Clique na guia Horas.
16. No campo Tempo de preparação, insira um número.
    * Neste exemplo, digite 1.  
17. No Painel de Ação, clique em Versão de roteiro.
18. Clique em Aprovar.
19. Clique em OK.
20. No Painel de Ação, clique em Versão de roteiro.
21. Clique em Ativar.
22. Feche a página.
23. Feche a página.

## <a name="enable-automatic-consumption-of-setup-time"></a>Habilitar o consumo automático do tempo de preparação
1. Vá para Controle de produção > Configuração > Roteiros > Grupos de roteiros.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione Std na lista.  
3. Clique em Editar.
4. Selecione Sim no campo Tempo de preparação.
    * O tempo de preparação geralmente faz parte do preço que é calculado para um item.  
5. Clique em Salvar.
6. Feche a página.


