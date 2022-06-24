---
title: Criar e manter um bloqueio de estoque
description: Este artigo descreve como usar um bloqueio de estoque para evitar que o estoque físico disponível seja reservado por outros documentos de origem de saída.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba95b689bedfc76598dfa81548a074f4fb7c833a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859333"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Criar e manter um bloqueio de estoque

[!include [banner](../../includes/banner.md)]

Este artigo descreve como usar um bloqueio de estoque para evitar que o estoque físico disponível seja reservado por outros documentos de origem de saída. Antes de iniciar os procedimentos deste artigo, você precisa ter um item do estoque físico disponível.

## <a name="block-inventory"></a>Bloquear estoque

Para criar um registro de bloqueio de estoque para que o estoque seja bloqueado, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Tarefas periódicas \> Bloqueio de estoque**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho do novo registro de bloqueio, defina o campo **Número do item** como o item que você deseja bloquear e digite uma descrição.
1. Na FastTab **Geral**, no campo **Quantidade**, insira o número de itens para bloquear.
1. Na FastTab **Dimensões de estoque**, especifique o local e o depósito onde os itens que você deseja bloquear estão localizados no momento.
1. No Painel de ações, selecione **Salvar**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Atualizar as condições de bloqueio de estoque

Para atualizar um registro de bloqueio de estoque, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Tarefas periódicas \> Bloqueio de estoque**.
1. No painel de lista, selecione o registro de bloqueio relevante.
1. Edite o registro, conforme necessário. Por exemplo, você pode alterar o valor do campo **Data esperada** para indicar quando o estoque bloqueado deve ficar disponível para reserva. Se a opção **Recebimentos esperados** for selecionada, a data aparecerá na transação esperada. (A opção **Recebimentos esperados** é selecionada por padrão quando você criar manualmente um registro de bloqueio.)
1. No Painel de ações, selecione **Salvar**.

## <a name="unblock-inventory"></a>Desbloquear estoque

Para remover um registro de bloqueio de estoque para que o estoque seja desbloqueado, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Tarefas periódicas \> Bloqueio de estoque**.
1. No painel de lista, selecione o registro de bloqueio relevante.
1. No Painel de Ações, selecione **Excluir**.
1. Será solicitado que você confirme a operação. Selecione **Sim** para continuar.
1. Feche a página.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
