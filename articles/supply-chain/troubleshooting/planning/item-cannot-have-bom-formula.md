---
title: O item não pode ter uma lista de materiais ou fórmula
description: Ao tentar firmar uma ordem, você recebe uma mensagem de erro durante a validação do item. Ela afirma que o item não pode ter uma lista de materiais (BOM) ou fórmula.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294011"
---
# <a name="item-cant-have-a-bom-or-formula"></a>O item não pode ter uma lista de materiais ou fórmula

Código de erro: PRO2614

## <a name="symptoms"></a>Sintomas

Ao tentar firmar uma ordem, você recebe a seguinte mensagem de erro durante a validação do item:

> O item não pode ter uma BOM ou uma fórmula

## <a name="resolution"></a>Resolução

Os itens que possuem uma lista de materiais (BOM) ou fórmula devem ser do tipo *Item de planejamento*, *BOM* ou *fórmula*. Para alterar o tipo de um item, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o produto relevante.
1. Na FastTab **Engenharia**, definida o campo **Tipo de produção** como *Item de planejamento*, *BOM* ou *Fórmula*.
