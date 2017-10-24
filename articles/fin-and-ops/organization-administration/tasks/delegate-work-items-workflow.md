--- 
title: Delegar itens de trabalho em um fluxo de trabalho
description: "Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4765fec0cdce0e2f8859c979ff97d20aa6b20bfa
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="delegate-work-items-in-a-workflow"></a>Delegar itens de trabalho em um fluxo de trabalho

[!include[task guide banner](../../includes/task-guide-banner.md)]

Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários. Este procedimento ajuda a configurar o sistema para delegar automaticamente seus itens de trabalho a outro usuário.



A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="set-up-automatic-delegation"></a>Configurar delegação automática
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


