---
title: Não é possível inserir a versão ativa da BOM e os números de rota
description: Se o depósito e o site padrão já estiverem definidos para um produto selecionado, você não será solicitado a inserir a versão ativa da BOM e os números de rota.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 241618d70f01c85df946a48493f5d84e0964218e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475533"
---
# <a name="cant-insert-bill-of-material-and-route-when-creating-a-new-production-order"></a>Não é possível inserir a lista de materiais e a rota ao criar uma nova ordem de produção

## <a name="symptoms"></a>Sintomas

Quando você cria uma ordem de produção, depois de inserir o número do item, os campos **Local** e **Depósito** são automaticamente configurados para o local e depósito padrão definidos na página **Configurações de ordem padrão** para o item de produtos acabados. Além disso, o número ativo da BOM e da rota são inseridos automaticamente; portanto, não será exibida a mensagem a seguir que solicita esses valores:

> Inserir versão ativa para lista de materiais e rota?

## <a name="resolution"></a>Resolução

Você não será solicitado a inserir os números de BOM e de rota se selecionar um produto para o qual um local e depósito já estão definidos na página **Configurações de ordem padrão**. Você só receberá a solicitação se esses valores não forem definidos para o produto selecionado.
