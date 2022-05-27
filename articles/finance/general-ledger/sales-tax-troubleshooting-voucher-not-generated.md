---
title: O comprovante não é gerado
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudar quando um comprovante deve ser gerado, mas não é.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: eb45b79fa710699cfa267e7c6359ba3ce761d62d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693217"
---
# <a name="voucher-isnt-generated"></a>O comprovante não é gerado

[!include [banner](../includes/banner.md)]

Se um comprovante deve ser gerado, mas a página **Transações de comprovante** não mostrar nenhum comprovante, siga as etapas nas seções a seguir, conforme necessário, para solucionar esse problema.

[![Página Transações de comprovante que não tem comprovantes.](./media/voucher-not-generated-Picture1.png)](./media/voucher-not-generated-Picture1.png)

## <a name="check-the-tax-applicability"></a>Verificar a aplicabilidade do imposto

1. Acesse **Imposto** \> **Tarefas periódicas** \> **Entradas no diário-razão auxiliar ainda não transferidas**.
2. Se houver um registro de diário, selecione-o e, em seguida, selecione **Transferir agora**.

    [![Botão Transferir agora na página Entradas no diário-razão auxiliar ainda não transferidas.](./media/voucher-not-generated-Picture2.png)](./media/voucher-not-generated-Picture2.png)

3. Abra a página **Transações de comprovante** novamente para ver se o comprovante foi gerado.

## <a name="determine-whether-customization-exists"></a>Determinar se há personalização

Se você concluiu as etapas na seção anterior, mas não encontrou nenhum problema, determine se há personalização. Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
