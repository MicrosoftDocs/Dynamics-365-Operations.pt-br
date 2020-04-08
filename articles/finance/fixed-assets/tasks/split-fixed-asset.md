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
ms.openlocfilehash: 85ccf187e77faf338ac29452d823c3652b806a21
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138106"
---
# <a name="split-a-fixed-asset"></a>Dividir um ativo fixo

[!include [banner](../../includes/banner.md)]

Este tópico explica como dividir uma porcentagem do registro de ativos em um novo registro de ativos. Usa os dados de função de contador e de demonstração de USMF.


## <a name="create-a-new-fixed-asset"></a>Criar um novo ativo fixo
1. No Painel de Navegação, vá para **Módulos > Ativos fixos > Ativos fixos > Ativos fixos**.
2. Selecione **Novo**.
3. No campo **Grupo de ativo fixo**, insira ou selecione um valor. Anote o número do ativo fixo a ser usado posteriormente no processo de divisão.  
4. No campo **Nome**, digite um valor.
5. Feche o formulário.

## <a name="split-a-fixed-asset"></a>Dividir um ativo fixo
1. Na lista, localize e selecione o link do ativo fixo que você deseja dividir.
2. Selecione **Registros**. Selecione o registro a ser dividido no novo ativo.  
3. Selecione **Funções**.
4. Selecione **Dividir ativo fixo**.
5. No campo **Para o ativo fixo**, insira ou selecione um valor.
6. No campo **Para o registro**, selecione o botão suspenso para abrir a pesquisa.
7. No campo **Data de transação**, insira uma data.
8. No campo **Porcentagem**, insira um número.
9. No campo **Nome do diário**, insira ou selecione um valor.
10. Selecione **OK**.

## <a name="post-the-journal-transaction"></a>Lançar a transação de diário
1. No Painel de navegação, vá para **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.
2. Na lista, selecione o diário criado com o processo de divisão.
3. Selecione **Linhas**.

    - Verifique as linhas de diário criadas.  
    - Uma transação de ajuste de aquisição é criada para o ativo original diminuir o valor por porcentagem especificada durante o processo de divisão.  
    - Uma transação de aquisição é criada para o novo ativo para a mesma quantidade.  

4. Selecione **Lançar**.

