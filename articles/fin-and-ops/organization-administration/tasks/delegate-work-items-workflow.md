---
title: Delegar itens de trabalho em um fluxo de trabalho
description: Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509443"
---
# <a name="delegate-work-items-in-a-workflow"></a>​Delegar itens de trabalho em um fluxo de trabalho​

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a>Delegar um item de trabalho manualmente

Para delegar um item de trabalho específico, selecione a opção **Delegar** no menu **Fluxo de Trabalho** e insira o usuário a ser delegado junto com um comentário. Isso atribuirá novamente o item de trabalho para que esse usuário possa concluí-lo.

## <a name="automatically-delegate-work-items"></a>Delegar itens de trabalho automaticamente

Se pretende se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho por um período, você poderá delegar novos itens de trabalho automaticamente para outros usuários na página **Opções de usuário**.

### <a name="set-up-automatic-delegation"></a>Configurar delegação automática
1. Vá para Comum > Configuração > Opções do usuário.
2. Clique na guia Fluxo de trabalho.
    * Certifique-se de que a seção Delegação está expandida.    Para configurar o sistema para delegar automaticamente seus itens de trabalho a outros usuários, você deve criar a regra de delegação, que especifique quando determinados tipos de itens de trabalho serão delegados. Siga estas etapas para criar uma regra de delegação.  
3. Clique em Adicionar.
4. No campo Escopo, selecione uma opção.
    * Tudo - delega todos os itens de trabalho atribuídos a você.    Módulo – Delega apenas os itens de trabalho relacionados a um tipo específico de fluxo de trabalho. Se você selecionar essa opção, selecione o tipo de fluxo de trabalho no campo Nome.    Fluxo de Trabalho – Delega apenas os itens de trabalho relacionados a um fluxo de trabalho específico. Se você selecionar essa opção, selecione o fluxo de trabalho no campo Nome.  
5. No campo Delegar, selecione o usuário para delegar os itens de trabalho.
    * Use os campos Data/hora inicial e Data/hora final para especificar quando você quer que os itens de trabalho sejam delegados automaticamente.  
6. No campo Data/hora inicial, insira uma data e hora.
7. No campo Data/hora final, insira uma data e hora.
8. Marque a caixa de seleção Habilitado para ativar a regra de delegação.
    * Se você selecionou Módulo o como o Escopo, em seguida, você deve selecionar o módulo no campo Nome.    Se você selecionou Fluxo de Trabalho como o Escopo, em seguida, você deve selecionar fluxo de trabalho específico para delegar no campo Nome.  
9. No campo Comentário, insira um comentário que explique o motivo pelo qual você está delegando os itens de trabalho.

