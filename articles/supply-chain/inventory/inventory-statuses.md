---
title: Status do estoque
description: Este artigo descreve como você pode usar o status de estoque para categorizar e manter o controle de estoque.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c4cad56389c7a8fd6d37591c1ff335fff715707
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001815"
---
# <a name="inventory-statuses"></a>Status do estoque

[!include [banner](../includes/banner.md)]

Este artigo descreve como você pode usar o status de estoque para categorizar e manter o controle de estoque.

## <a name="set-up-and-use-inventory-statuses"></a>Configurar e usar status de estoque

Você pode usar status de estoque para categorizar o estoque. Em seguida, você pode iniciar ações apropriadas, como o trabalho de reabastecimento ou de abastecimento.

Veja a seguir alguns exemplos de formas de uso dos status do estoque:

- Crie status de estoque para o estoque disponível e para as transações de entrada e de saída.
- Especifique um status de estoque padrão para transações de depósito.
- Altere o status de estoque para itens antes da chegada, durante a chegada ou quando os itens são inseridos durante a movimentação do estoque.
- Use um status de estoque para a definição de preços dos itens que foram devolvidos e para planejar a cobertura do item durante o planejamento mestre.

O status de estoque é uma das dimensões do grupo de dimensão de armazenamento. Os status do estoque podem ser categorizados como disponível ou não disponível e você pode usar o parâmetro **Bloqueio de estoque** para bloquear os itens que possuem um status de estoque indisponível. Os itens com um status bloqueado são considerados um estoque físico e não podem ser usados em uma ordem de produção, ordem de venda, ordem de transferência ou transação de saída.

Você pode usar itens de depósito com o status de estoque disponível ou indisponível para o trabalho de entrada. Por exemplo, você cria um status disponível que é chamado *Pronto*, um status indisponível que é chamado *Danificado* e um status bloqueado que é chamado *Bloqueado*. Quando você cria uma ordem de compra para itens recebidos ou devolvidos, se os item forem danificados ou interrompidos, é possível alterar o status do estoque dos itens para *Danificado* na linha da ordem de compra. Depois que os itens são recebidos, o status é automaticamente definido como *Bloqueado*. Se você pesquisa os itens danificados usando um dispositivo móvel, o Supply Chain Management pode usar diretivas de local e modelos de trabalho para mostrar informações sobre um local apropriado ou intervalo de locais onde você pode armazenar esses itens. Para itens devolvidos, um tipo de problema de *Reserva* é criado na página **Transações do inventário**.

Para o trabalho de saída, use itens com status de estoque disponível. Se você tiver itens com um status de *Quebrado* e o planejamento mestre for executado nesses itens, os itens serão considerados faltantes e o estoque será reabastecido automaticamente.

Depois de configurar um status de estoque, você pode definir o status de estoque padrão para um local, item e depósito. Você também pode definir um status padrão de venda, transferência e ordens de compra. O status padrão para ordens de venda e a ordem de transferência de saída não pode ter a opção **Bloqueio de estoque** definida como *Sim*. O status de estoque que é herdado das configurações padrão em um site, depósito, item, ordem de compra, ordem de transferência ou ordem de vendas pode ser alterado usando o dispositivo móvel ou na ordem de compra, na ordem de venda ou na linha da ordem de transferência.

Para planejar a cobertura de itens com um status de estoque disponível, selecione a opção **Plano de cobertura por dimensão** para uma dimensão de armazenamento na página **Grupos de dimensão de armazenamento**. Quando você abre o assistente **Cobertura de item**, os itens com um status disponível aparecem na página **Status**. Para criar configurações de cobertura para esses itens, selecione a ID do status de estoque para os status de estoque disponíveis. Com base nas configurações de cobertura, você pode calcular os requisitos dos itens e fazer a previsão de fornecimento e demanda de itens disponíveis durante o planejamento mestre. Não é possível criar uma configuração de cobertura de item com um status de estoque bloqueado. Como alternativa, use a página **Cobertura do item** para criar ou modificar os parâmetros de cobertura do item.

## <a name="change-inventory-statuses"></a>Alterar status de estoque

Você pode alterar os status de estoque usando a página **Disponibilidade por localização** ou a tarefa periódica *Alteração de status do estoque*.

- Ao usar a tarefa periódica *Alteração de status do estoque*, você pode selecionar os registros a serem incluídos e definir a tarefa a ser executada no lote no intervalo desejado.
- Para alterar o status do estoque como um processo ad hoc, vá para a página **Disponibilidade por localização**, selecione os registros relevantes e, em seguida, selecione o botão **Alteração de status do estoque**.

> [!NOTE]
> O recurso *Alterar o status de estoque de itens controlados por dimensões de rastreamento* permite alterar o status de estoque de itens controlados por dimensões de rastreamento, incluindo a capacidade de atualizar somente os registros selecionados. Use o [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar o recurso conforme necessário. Quando o recurso estiver habilitado, você poderá fazer o seguinte:
>
> - Na página **Disponibilidade por localização**, agrupar linhas com base nas dimensões mostradas usando o botão **Exibir dimensões** e alterar o status das linhas selecionadas.
> - Na página **Disponibilidade por localização**, selecionar vários registros e, em seguida, usar o botão **Alteração de status do estoque** para alterar todos eles de uma só vez.
> - Na tarefa periódica **Alteração de status do estoque**, filtrar por dimensões de rastreamento.
