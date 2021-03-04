---
title: Lançar diário de entrada para produtos devolvidos
description: Lançar diário de entrada para produtos devolvidos.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e07542a369506b810704012bd1b07557b79f50d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422359"
---
# <a name="post-arrival-journal-for-returned-products"></a>Lançar diário de entrada para produtos devolvidos 

[!include [banner](../includes/banner.md)]


Para processar uma devolução, primeiro valide a quantidade devolvida, atualize o campo de quantidade no diário de entrada de itens. Em seguida, selecione um código de disposição ou indique que os itens devolvidos precisam ser inspecionados. Depois de completar essas etapas, você pode lançar o diário de entrada de item para a ordem de devolução.

1.  Clique em **Gerenciamento de estoque** \> **Periódico** \> **Visão geral de entrada**.

2.  No filtro **Nome de instalação**, selecione **Devolver ordem**.

3.  Se a lista de recebimentos for longa, use os campos na área **Variação** para restringi-la.

4.  Localize a linha da ordem de devolução que deseja lançar, selecione a caixa **Selecionar para entrada** correspondente e clique em **Iniciar entrada**.

5.  Clique em **Diários** \> **Mostrar entradas a partir de recebimentos** para abrir o formulário **Diário de localização**.
    

    > [!TIP]
    > <P>Para exibir informações detalhadas, selecione um diário e clique em <STRONG>Linhas</STRONG>.</P>


6.  Faça as atualizações necessárias e clique em **Lançar**.

Depois que o diário é lançado, os itens devolvidos são registrados no estoque e o formulário **Devolver ordem** indica que os itens chegaram no depósito.

## <a name="see-also"></a>Consulte também

[Diário de localização (formulário)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]