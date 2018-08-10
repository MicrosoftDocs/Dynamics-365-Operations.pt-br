--- 
title: Dividir um ativo fixo
description: "Este guia da tarefas dividirá uma porcentagem do registro de ativos em um novo registro de ativos."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="split-a-fixed-asset"></a>Dividir um ativo fixo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este guia da tarefas dividirá uma porcentagem do registro de ativos em um novo registro de ativos.  Usa os dados de função de contador e de demonstração de USMF.


## <a name="create-a-new-fixed-asset"></a>Criar um novo ativo fixo
1. Vá para Ativos fixos > Ativos fixos > Ativos fixos.
2. Clique em Novo.
3. No campo Grupo de ativo fixo, insira ou selecione um valor.
4. Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.
5. No campo Nome, digite um valor.
6. Feche o formulário.

## <a name="split-a-fixed-asset"></a>Dividir um ativo fixo
1. Na lista, localize e selecione o ativo fixo que você deseja dividir.
2. Na lista, clique no link na linha selecionada.
3. Clique em Registros.
    * Selecione o registro a ser dividido no novo ativo.  
4. Clique em Funções.
5. Clique em Dividir ativo fixo.
6. No campo Para o ativo fixo, insira ou selecione um valor.
7. No campo Para o registro, clique no botão suspenso para abrir a pesquisa.
8. No campo Transação, insira uma data.
9. No campo Porcentagem, insira um número.
10. No campo Diário, insira ou selecione um valor.
11. Clique em OK.

## <a name="post-the-journal-transaction"></a>Lançar a transação de diário
1. Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.
2. Na lista, selecione o diário criado com o processo de divisão.
3. Clique em Linhas.
    * Verifique as linhas de diário criadas.  Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.  Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.  
4. Clique em Lançar.


