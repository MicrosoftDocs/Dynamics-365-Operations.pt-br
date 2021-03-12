---
title: Configurando consignação
description: Este tópico explica como configurar operações de estoque de entrada de consignação.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: bcc5ce7d9b9031fe8e9589798e07162106277767
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987270"
---
# <a name="set-up-consignment"></a>Configurando consignação

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar operações de estoque de entrada de consignação.

Estoque em consignação é o estoque a que pertence a um fornecedor, mas está armazenado em seu site. Quando estiver pronto para consumir ou usar o estoque, você obterá sobre a propriedade de estoque. Este tópico descreve a configuração necessária habilitar processos de consignação. Para obter mais informações sobre processos de consignação, consulte [Configurar a consignação](consignment.md).

## <a name="inventory-owners"></a>Proprietários de estoque
Para registrar o estoque físico de entrada em consignação, você precisa definir o proprietário do fornecedor. Isso é feito na página **Proprietário de estoque**. Quando você seleciona uma **Conta de fornecedor** isso gera valores padrão para os campos **Nome** e **Proprietário**. O valor no campo **Proprietário** ficará visível ao fornecedor, para que você possa alterá-lo se os nomes de contas do fornecedor não forem fáceis para os contatos externos reconhecerem. É possível editar o campo **Proprietário**, mas somente até o ponto em que você salvar o registro **Proprietário de estoque**. O campo **Nome** é preenchido com o nome do participante da conta do fornecedor está associada, e este não pode ser alterada.

[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)

## <a name="tracking-dimension-group"></a>Grupo de dimensões de rastreamento
Itens que estejam prestes a ser usado nos processos de consignação devem ser associados com **Grupo de dimensão de rastreamento** a qual **Proprietário** a dimensão é definida como **Ativo**. A dimensão do proprietário deve sempre **Estoque físico** e **Estoque financeiro** as opções selecionadas. **Plano de cobertura por dimensão** nunca é selecionado.

[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)

## <a name="inventory-ownership-change-journal"></a>Diário de alteração de propriedade de estoque
O diário **Alteração de propriedade de estoque** é usado para registrar a transferência de posse de estoque consignado do fornecedor para a entidade legal que o está consumindo. Como qualquer diário de estoque, deve ser identificado com um nome de diário de estoque. Esses nomes são criados na página **Nomes de diário de estoque**, e o **Tipo de diário** deve ser definido como **Alteração de propriedade**.

[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)

## <a name="vendor-collaboration-in-consignment-processes"></a>Colaboração de fornecedor em processos de consignação
Se os fornecedores serão usando a interface de colaboração de fornecedor, pode usar isso para monitorar o consumo de estoque no site. Para obter mais informações sobre como configurar fornecedores para usar a colaboração do fornecedor, consulte [Segurança do usuário no portal de fornecedor](../procurement/configure-security-vendor-portal-users.md).
