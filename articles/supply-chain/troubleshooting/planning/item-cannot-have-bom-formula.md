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
ms.openlocfilehash: 1e946adc3a04db60bf15ac7bb44163085e1c19802872964877d3929b1f79bf7d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730097"
---
# <a name="item-cant-have-a-bom-or-formula"></a>O item não pode ter uma lista de materiais ou fórmula

Código de erro: PRO2614

## <a name="symptoms"></a>Sintomas

Ao tentar firmar uma ordem, você recebe a seguinte mensagem de erro durante a validação do item:

> O item não pode ter uma BOM ou uma fórmula

## <a name="resolution"></a>Resolução

Os itens que possuem uma lista de materiais (BOM) ou fórmula devem ser do tipo *Item de planejamento*, *BOM* ou *fórmula*. Para alterar o tipo de um item, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o produto relevante.
1. Na FastTab **Engenharia**, definida o campo **Tipo de produção** como *Item de planejamento*, *BOM* ou *Fórmula*.
