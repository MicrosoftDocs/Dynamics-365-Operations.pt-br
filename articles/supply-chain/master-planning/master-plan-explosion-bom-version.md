---
title: "Detalhamento de uma versão da BOM"
description: "Este artigo explica um cenário de planejamento mestre que envolve detalhamento de uma versão da lista de materiais (BOM)."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 80c9fa6ec98bd2cdc3edd5329e2a619ef9cc8cb2
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="explosion-of-a-bom-version"></a>Detalhamento de uma versão da BOM

[!include [banner](../includes/banner.md)]

Este artigo explica um cenário de planejamento mestre que envolve detalhamento de uma versão da lista de materiais (BOM).

Um detalhamento da demanda de uma versão da lista de materiais (BOM) cria uma demanda para cada item de linha da BOM em um site específico e, possivelmente, em um depósito específico. Em uma BOM específica do site, um determinado depósito pode ser definido para cada linha de BOM. Além disso, para cada linha de BOM, as configurações de dimensão do item determinam se o depósito é necessário. A demanda resultante para cada item de linha de BOM se torna, então, o ponto de partida para detalhamento de demanda adicional. Este cenário de planejamento mestre envolve estas condições:

-   A dimensão do site é obrigatória e deve ser inserida na transação de demanda.
-   A dimensão do site é consistente. Portanto, o site para demanda de nível inferior é o mesmo site na transação de demanda inicial.

A ilustração a seguir mostra como ocorre o processo de detalhamento da demanda do planejamento mestre. ![Explosão de demanda usando a versão da BOM](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a>Recursos adicionais
--------

[Planejamento mestre – como a versão da BOM é determinada](master-plan-bom-version-determined.md)

[Planejamento mestre e funcionalidade multissite](master-plan-multisite-functionality.md)




