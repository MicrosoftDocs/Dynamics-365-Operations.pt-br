---
title: Diversas transações de inventário para números de lote quando Mediante atualização física está desabilitado
description: Diversas transações de inventário são criadas quando você ajusta a linha do pedido de compra para itens em que a opção Mediante atualização física do grupo de número de lote está definida como Não.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b8aef8835e90b7437bb7833c13c3d287d4ca836bf1fefc01bfeafef1c93329bc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768585"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a>Diversas transações de inventário para números de lote quando Mediante atualização física está desabilitado

Número da base de dados de conhecimento: 4613390

## <a name="symptoms"></a>Sintomas

Diversas transações de inventário são criadas quando você ajusta a linha do pedido de compra para itens em que a opção **Mediante atualização física** do grupo de número de lote está definida como *Não*.

Quando você criar um item em que a opção **Mediante atualização física** do grupo de número de lote está definida como *Não*, o sistema cria automaticamente um novo número de lote se você modificar uma quantidade da linha de compra e salvar a página do pedido de compra.

## <a name="resolution"></a>Resolução

A configuração **Mediante atualização física** para os grupos de número de lote funciona da seguinte forma:

- Quando a opção estiver definida como *Sim*, novos números de lote serão criados somente após uma atualização física (por exemplo, quanto os itens foram enviados ou recebidos).
- Quando a opção estiver definida como *Não*, um novo número de lote será criado sempre que uma atualização aplicável ocorrer (por exemplo, quando uma nova quantidade for adicionada ao pedido de compra).
