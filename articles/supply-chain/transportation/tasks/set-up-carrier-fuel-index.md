--- 
title: "Configurar um índice de combustível da transportadora"
description: "Este guia mostra como criar uma região do índice de combustível, um índice de combustível e um índice de combustível da transportadora."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 81f3244ff42cf13cd93ac10656c47f8a9204ef99
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-carrier-fuel-index"></a>Configurar um índice de combustível da transportadora

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este guia mostra como criar uma região do índice de combustível, um índice de combustível e um índice de combustível da transportadora. A região do índice de combustível especifica em qual região o índice de combustível deve ser aplicado, e o índice de combustível especifica um preço do combustível para um determinado período de tempo. Para refletir a alteração nos preços do combustível ao longo do tempo, você pode associar múltiplos índices de combustível da transportadora.  Essas tarefas são feitas tipicamente por um coordenador de transporte. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou usando seus próprios dados.


## <a name="create-a-fuel-index-region"></a>Crie uma região de índice de combustível
1. Vá para Gerenciamento de transporte > Configurar > Índices de combustível > Regiões de índices de combustível.
    * Primeiro você deve criar as diferentes regiões, onde você opera e calcula as diferentes sobretaxas de combustível.  
2. Clique em Novo.
3. No campo Região, digite um valor.
4. No campo Nome, digite um valor.
5. Clique em Salvar.

## <a name="create-a-fuel-index"></a>Crie um índice de combustível
1. Vá para Gerenciamento de transporte > Configurar > Índices de combustível > Índices de combustível.
    * Para as regiões que você configurou é preciso inserir os preços atuais do combustível.  
2. Clique em Novo.
3. No campo Região, clique no botão suspenso para abrir a pesquisa.
4. Na lista, clique no link na linha selecionada.
5. No campo Preço por galão, insira um número.
6. No campo Data e hora efetiva de início, insira uma data e hora.
7. Clique em Salvar.

## <a name="create-a-carrier-fuel-index"></a>Crie um índice de combustível da transportadora
1. Vá para Gerenciamento de transporte > Configurar > Índices de combustível > Índices de combustível da transportadora.
2. Clique em Novo.
3. No campo Índice de combustível da transportadora, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Novo.
6. No campo Data e hora efetiva de início, insira uma data e hora.
7. No campo PPG De, insira um número.
    * Neste exemplo, você pode definir o campo PPG De para 1,95.  
8. No campo PPG Até, insira um número.
    * Neste exemplo, você pode definir o campo PPG Até para 2.  
9. No campo Porcentagem, insira um número.
    * Neste exemplo, você pode definir a porcentagem para 3.  
10. No campo Moeda, clique no botão suspenso para abrir a pesquisa.
11. Na lista, localize e selecione o PDV desejado.
12. Na lista, clique no link na linha selecionada.
13. Clique em Salvar.


