---
title: Usar fluxos de trabalho de aprovação de arrendamento
description: Este artigo explica como usar fluxos de trabalho para aprovar arrendamentos de ativos e como rastrear o status e o histórico dos fluxos de trabalho.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4205b83919f0b3c30a4b5d8e3290af230f538f39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906432"
---
# <a name="use-lease-approval-workflows"></a>Usar fluxos de trabalho de aprovação de arrendamento

[!include [banner](../includes/banner.md)]

Este artigo explica como usar fluxos de trabalho para aprovar arrendamentos de ativos e como rastrear o status e o histórico dos fluxos de trabalho. Os fluxos de trabalho ajudam a proporcionar consistência ao gerenciamento de aprovações de arrendamento, fornecendo um conjunto padrão de etapas de aprovação e atribuindo usuários específicos que aprovem cada etapa do processo. Um aprovador pode aprovar um arrendamento, rejeitá-lo, solicitar uma alteração nele ou atribuí-lo a outro usuário para aprovação. Os fluxos de trabalho também podem trazer mais visibilidade para o processo de aprovação, permitindo que você controle o status e o histórico. Além disso, é possível exibir uma lista de trabalho centralizada que liste as tarefas e aprovações atribuídas a aprovadores específicos.

Antes de usar esse procedimento, certifique-se de que pelo menos o fluxo de trabalho de aprovação de arrendamento tenha sido criado. Se não houver nenhum fluxo de trabalho, crie um. Para obter informações sobre como configurar um fluxo de trabalho, consulte [Configurar fluxos de trabalho de aprovação de arrendamento](set-up-lease-wrkflw.md).

1. Envie um arrendamento para aprovação. Na página **Detalhes do registro** do arrendamento, selecione **Fluxo de trabalho** e, em seguida, selecione **Enviar**.
2. Na caixa de diálogo exibida, você pode adicionar um comentário. O aprovador designado verá esse comentário juntamente com o arrendamento. Ao terminar de inserir o comentário, selecione **Enviar**. O arrendamento é enviado para o sistema de fluxo de trabalho e o aprovador o recebe para aprovação.
3. Para exibir os arrendamentos designados para aprovação, Acesse **Módulos \> Comum \> Itens de trabalho \> Itens de trabalho atribuídos a mim**.
4. Na página **Itens de trabalho atribuídos a mim**, selecione o link **ID do Arrendamento** para o arrendamento que você deseja exibir. A página exibida depende dos registros de arrendamento e dos detalhes do arrendamento aos quais você tem acesso.
5. Quando terminar de exibir o arrendamento, selecione **Fluxo de trabalho** e decida qual ação deve ser executada. As opções incluem **Aprovar**, **Rejeitar**, **Solicitar alteração**, **Delegar** e **Cancelado**. Você também pode selecionar **Exibir histórico** para exibir o histórico de aprovação para o arrendamento selecionado.
6. Depois de selecionar uma ação, insira um comentário para descrever a ação. Quando tiver terminado de inserir o comentário, selecione a ação **Aprovado** na lista.
7. Para exibir as ações de aprovação, volte para a página **Detalhes do arrendamento** na página **Resumo do arrendamento** e selecione **Fluxo de trabalho \> Exibir histórico**.

    Você pode exibir as atividades de fluxo de trabalho na página **Histórico do fluxo de trabalho**. Esta página mostra as etapas do fluxo de trabalho que foram executadas no arrendamento específico. Você também pode usar o campo **Itens de trabalho** para exibir o status dos itens de trabalho atribuídos.

8. Para interromper um fluxo de trabalho, na página **Histórico do fluxo de trabalho**, selecione **Recuperar**. Na caixa de diálogo mostrada, insira um comentário e selecione **OK**.
9. Para desativar um fluxo de trabalho ou ativar um fluxo de trabalho criado anteriormente, acesse **Arrendamento de ativo \> Configuração \> Fluxo de trabalho de arrendamento**. Em seguida, na página **Fluxo de trabalho de arrendamento**, selecione **Fluxo de trabalho \> Versões**. Para tornar um fluxo de trabalho atual inativo, selecione o arrendamento ativo na caixa de diálogo da versão do arrendamento e, em seguida, selecione **Tornar inativo**. Para ativar um fluxo de trabalho existente, selecione o fluxo de trabalho e selecione **Tornar ativo**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
