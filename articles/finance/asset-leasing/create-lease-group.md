---
title: Criar um grupo de arrendamento
description: Este artigo explica como configurar grupos de arrendamento. Os grupos de arrendamento são necessários para criar novos arrendamentos.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: cd1a6f61346233bf205657917c65fccd82167f7f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895012"
---
# <a name="create-a-lease-group"></a>Criar um grupo de arrendamento

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar grupos de arrendamento. Os grupos de arrendamento são necessários para criar novos arrendamentos. Os registros de arrendamento estão associados a cada grupo de arrendamento. Os registros de arrendamento determinam os registros padrão que devem ser criados para cada arrendamento. Você pode atribuir contas específicas a um grupo de arrendamento na página **Parâmetros de lançamento de arrendamento**.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>Criar um registro de arrendamento e adicionar um grupo de arrendamento

1. Acesse **Arrendamento de ativo \> Configuração \> Grupos de arrendamento**.
2. No Painel de ações, selecione **Novo** para adicionar um grupo de arrendamento. Uma linha é adicionada à grade.
3. Na nova linha, no campo **Grupo de arrendamento**, insira um valor.
4. No campo **Descrição**, insira um valor.

As informações inseridas são adicionadas ao campo **Grupo de arrendamento** na página **Adicionar arrendamento**.

## <a name="associate-a-book-with-a-lease-group"></a>Associar um registro a um grupo de arrendamento

Depois de criar grupos de arrendamento, você pode atribuir registros a cada grupo. Ao criar um arrendamento e atribuí-lo a um grupo de arrendamento, o sistema cria um conjunto de agendas para cada registro associado a esse grupo de arrendamento.

> [!NOTE]
> Os registros devem ser configurados antes que possam ser atribuídos a um grupo de arrendamento.

1. Acesse **Arrendamento de ativo \> Configuração \> Grupo de arrendamento**.
2. Selecione um grupo de arrendamento e, em seguida, selecione **Registros**.
3. Selecione **Novo** e, no campo **Tipo de registro**, selecione o registro a ser atribuído ao grupo de arrendamento. Caso seja necessário considerar um arrendamento de maneiras diferentes, você pode atribuir vários registros a um grupo de arrendamento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
