---
title: Despesas intercompanhia
description: Um trabalhador contratado por uma entidade legal em uma organização pode executar o trabalho para outra entidade legal na mesma organização. Nessa situação, será possível usar o recurso de despesas intercompanhia para atribuir as despesas do trabalhador para a entidade legal à qual o trabalho foi realizado.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390875"
---
# <a name="intercompany-expenses"></a>Despesas intercompanhia

[!include [banner](../includes/banner.md)]

Um trabalhador contratado por uma entidade legal em uma organização pode executar o trabalho para outra entidade legal na mesma organização. Nessa situação, será possível usar o recurso de despesas intercompanhia para atribuir as despesas do trabalhador para a entidade legal à qual o trabalho foi realizado. A entidade legal que emprega o trabalhador é chamada de entidade legal de empréstimo. As entidade legal para a qual o trabalhador incorre as despesas é chamada de entidade legal de empréstimo. 

Antes que um trabalhador possa criar e enviar despesas de trabalho executadas para uma pessoa jurídica diferente, na entidade legal do empréstimo, na página **Parâmetros de gerenciamento de despesas** , selecione a opção **Permitir linhas de despesa intercompanhia** . 

## <a name="tax-posting-for-intercompany-expenses"></a>Lançamento de imposto para despesas intercompanhia

[!include [banner](../includes/banner.md)]

Se você deseja usar grupos de impostos associados à entidade legal de empréstimo (origem) em vez da entidade legal de empréstimo (destino) no seu relatório de despesas, será necessário configurá-lo na configuração do imposto sobre vendas da contabilidade. Quando o parâmetro da contabilidade **Entidade legal para lançamento de imposto intercompanhia** é definido como **Origem** e **Aplicar regras de tributação de imposto sobre vendas** está definido como **Não**, a combinação de impostos para a entidade legal de empréstimo será usada. Quando o mesmo parâmetro é definido como **Destino**, a combinação de impostos para a entidade legal de empréstimo será usada. Para entidades legais nos Estados Unidos, quando o parâmetro é definido como **origem**, o campo **Imposto sobre vendas a receber** também deve ser configurado na página **Novos grupos de lançamento contábil**. O mecanismo de contabilidade usará as informações deste campo para entrada contábil relacionada ao imposto.   
O comportamento é consistente para linhas de despesas lançadas com ou sem um projeto.  
