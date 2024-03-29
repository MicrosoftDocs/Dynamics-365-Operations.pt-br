---
title: Passar itens devolvidos para inspeção
description: Ao registrar um item devolvido, determine que o item deve ser enviado para inspeção antes de ser devolvido ao estoque ou descartado de alguma outra maneira.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 959df8e1ecbc493dc11e4793120f352b94b8b635
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676737"
---
# <a name="pass-returned-items-on-to-inspection"></a>Passar itens devolvidos para inspeção 

[!include [banner](../includes/banner.md)]


Ao registrar um item devolvido, você pode determinar que o item deve ser enviado para inspeção antes de ser devolvido ao estoque ou descartado de alguma outra maneira.

1.  Clique em **Gerenciamento de estoque** \> **Diários** \> **Chegada de item** \> **Chegada de item**.
    
    \-ou-
    
    Clique em **Gerenciamento de estoque** \> **Diários** \> **Chegada de item** \> **Entrada de produção**.

2.  No formulário **Diário de localização**, registre o recebimento de um item normalmente.
    

    > [!NOTE]
    > <P>Para obter informações sobre como registrar o recebimento de itens devolvidos, consulte <A href="register-the-receipt-of-returned-items.md">Registrar o recebimento de itens devolvidos</A></P>



3.  Na guia **Valores padrão**, na área **Modo de manuseio**, selecione a caixa **Gerenciamento de quarentena**.

Isso informará ao sistema para criar uma ordem de quarentena e a pessoa ou o departamento que realiza inspeções responderá a essa ordem usando o formulário **Ordem de quarentena**.

## <a name="see-also"></a>Consulte também

[Submeter itens devolvidos à inspeção](take-returned-items-through-inspection.md)

[Especificar o destino dos itens devolvidos](specify-how-to-dispose-of-returned-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]