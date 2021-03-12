---
title: Delegar itens de trabalho em um fluxo de trabalho
description: Se você planeja se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho, poderá delegar ou reatribuir seus itens de trabalho a outros usuários.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48d8fd06217d318fa8208e11ffa5624f6be25be1
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796697"
---
# <a name="delegate-work-items-in-a-workflow"></a>​Delegar itens de trabalho em um fluxo de trabalho​

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a>Delegar um item de trabalho manualmente

Para delegar um item de trabalho específico, selecione a opção **Delegar** no menu **Fluxo de Trabalho** e insira o usuário a ser delegado junto com um comentário. Isso atribuirá novamente o item de trabalho para que esse usuário possa concluí-lo.

## <a name="manually-delegate-multiple-work-items"></a>Delegar manualmente vários itens de trabalho

Vários itens de trabalho podem ser delegados em conjunto na página **Itens de trabalho atribuídos a mim**. Os seguintes tipos de fluxo de trabalho estão qualificados para delegação em massa: Fluxo de trabalho de aprovação do contrato de compra, Fluxo de trabalho da ordem de compra, Revisão da requisição de compra e Fluxo de trabalho da fatura de fornecedor. O recurso **Delegar vários itens de trabalho** é desabilitado por padrão e pode ser habilitado em **Espaços de trabalho > Gerenciamento de recursos**. Entre em contato com o administrador do sistema para obter ajuda para habilitar este recurso.
1.  Vá para **Comum > Comum > Itens de trabalho > Itens de trabalho atribuídos a mim**.
2.  Selecione os itens de trabalho que serão delegados.
3.  Clique no menu **Delegar itens de trabalho**.
4.  No campo **Usuário**, selecione o usuário ao qual delegar os itens de trabalho.
5.  No campo **Comentário**, insira um comentário que explique o motivo de você estar delegando os itens de trabalho.
6.  Clique no botão **Delegar itens de trabalho** para concluir a delegação.

## <a name="automatically-delegate-work-items"></a>Delegar itens de trabalho automaticamente

Se pretende se ausentar do escritório ou ficar indisponível para executar ações em itens de trabalho por um período, você poderá delegar novos itens de trabalho automaticamente para outros usuários na página **Opções de usuário**.

### <a name="set-up-automatic-delegation"></a>Configurar delegação automática
1. Vá para **Comum > Configuração > Opções do usuário**.
2. Clique na guia **Fluxo de trabalho**. Verifique se a seção Delegação está expandida. Para configurar o sistema para delegar automaticamente seus itens de trabalho a outros usuários, você deve criar a regra de delegação, que especifique quando determinados tipos de itens de trabalho serão delegados. Siga estas etapas para criar uma regra de delegação.  
3. Clique em **Adicionar**.
4. No campo **Escopo**, selecione uma opção:
    - Tudo - delega todos os itens de trabalho atribuídos a você.
    - Módulo – Delega apenas os itens de trabalho relacionados a um tipo específico de fluxo de trabalho. Se você selecionar essa opção, deverá selecionar o tipo de fluxo de trabalho no campo **Nome**.
    - Fluxo de Trabalho – Delega apenas os itens de trabalho relacionados a um fluxo de trabalho específico. Se você selecionar essa opção, deverá selecionar o fluxo de trabalho no campo **Nome**.  
5. No campo **Nome**:
    - Para o escopo **Módulo**, selecione o módulo de destino.
    - Para o escopo **Fluxo de trabalho**, selecione o fluxo de trabalho de destino.
6. No campo **Delegar**, selecione o usuário para delegar os itens de trabalho. Use os campos **Data/hora inicial** e **Data/hora final** para especificar quando você quer que os itens de trabalho sejam delegados automaticamente.  
7. No campo **Data/hora inicial**, insira uma data e hora.
8. No campo **Data/hora final**, insira uma data e hora.
9. Marque a caixa de seleção **Habilitado** para ativar a regra de delegação. 
10. No campo **Comentário**, insira um comentário que explique o motivo de você estar delegando os itens de trabalho.
