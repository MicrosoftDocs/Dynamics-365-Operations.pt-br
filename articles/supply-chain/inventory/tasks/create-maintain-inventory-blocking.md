---
title: Criar e manter um bloqueio de estoque
description: Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque.
author: perlynne
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eab6730daa2eb7df0f91d99d1026d4736285fef9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000050"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Criar e manter um bloqueio de estoque

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como evitar que o estoque físico disponível seja reservado para outros documentos de origem de saída usando o bloqueio de estoque. Você pode executar o procedimento na empresa USMF de dados de demonstração usando os valores de exemplo mostrados. Você precisa ter um item do estoque físico disponível antes de iniciar este procedimento.


## <a name="create-an-inventory-blocking"></a>Criar um bloqueio de estoque
1. No **Painel de Navegação**, vá para **Módulos > Gerenciamento de estoque > Tarefas periódicas > Bloqueio de estoque**.
2. Clique em **Novo**.
3. No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.
4. Na lista, selecione o item que deseja escolher. Selecione um número de item com estoque físico disponível que você deseja bloquear. Se você estiver usando USMF, você pode o item M9201.  
5. No campo **Quantidade.**, insira um número Se você estiver usando o item M9201, você precisará selecionar menos de 200.
6. Expanda a Guia Rápida **Dimensões de estoque**.
7. No campo **Depósito**, clique no botão suspenso para abrir a pesquisa.
8. Na lista, localize e selecione o PDV desejado. Se você estiver usando o item M9201, você pode selecionar o depósito 51.  
9. Clique em **Salvar**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Atualizar as condições de bloqueio de estoque
1. Na Guia Rápida **Geral**, no campo **Quantidade**, insira um número. Atualize o campo de quantidade em estoque para refletir a quantidade para bloquear.  
2. No campo **Data estimada**, insira uma data. Você pode desejar indicar quando o estoque bloqueado deve ficar disponível para reserva atribuindo uma data esperada. Se a opção esperada de recebimentos é marcada para o bloqueio de estoque, como é por padrão ao criar manualmente um bloqueio, essa data será exibida na transação esperada.  
3. Clique em **Salvar**.

## <a name="remove-the-inventory-blocking"></a>Remover o bloqueio de estoque
1. No **Painel de Ação**, clique em **Excluir**.
2. Clique em **Sim**.
3. Feche a página.

