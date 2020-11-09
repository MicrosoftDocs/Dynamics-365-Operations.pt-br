---
title: Dividir um ativo fixo
description: Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40703622bc8c7a21451d31e7606596c5edbe90f7
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000284"
---
# <a name="split-a-fixed-asset"></a>Dividir um ativo fixo

[!include [banner](../../includes/banner.md)]

Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos. Usa os dados de função de contador e de demonstração de USMF.

## <a name="create-a-new-fixed-asset"></a>Criar um novo ativo fixo

1. No painel de navegação, vá para **Módulos \> Ativos fixos \> Ativos fixos \> Ativos fixos**.
2. Selecione **Novo**.
3. No campo **Grupo de ativo fixo** , insira ou selecione um valor. Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.
4. No campo **Nome** , insira um valor.
5. Feche o formulário.

## <a name="split-a-fixed-asset"></a>Dividir um ativo fixo

Antes que um ativo com depreciação total seja dividido, o status do registro de ativos deve ser alterado manualmente de **Fechado** para **Aberto**. Essa etapa é necessária porque o status do registro precisa estar **Aberto** se você precisar lançar transações para o ativo (por exemplo, para uma venda de alienação). Depois que o status do registro de ativos for alterado, siga estas etapas para dividir o ativo.

1. Na lista, localize e selecione o link do ativo fixo que você deseja dividir.
2. Selecione **Registros**. Selecione o registro a ser dividido no novo ativo.
3. Selecione **Funções**.
4. Selecione **Dividir ativo fixo**.
5. No campo **Para o ativo fixo** , insira ou selecione um valor.
6. No campo **Para o registro** , selecione o botão suspenso para abrir a pesquisa.
7. No campo **Data de transação** , insira uma data.
8. No campo **Porcentagem** , insira um número.
9. No campo **Nome do diário** , insira ou selecione um valor.
10. Selecione **OK**.

## <a name="post-the-journal-transaction"></a>Lançar a transação de diário

1. No Painel de navegação, vá para **Módulos \> Ativos fixos \> Entradas de diário \> Diário de ativos fixos**.
2. Na lista, selecione o diário criado com o processo de divisão.
3. Selecione **Linhas**.

    - Verifique as linhas de diário criadas.
    - Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.
    - Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.

4. Selecione **Lançar**.
