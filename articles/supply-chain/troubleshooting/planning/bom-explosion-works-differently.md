---
title: O detalhamento da BOM se comporta de forma diferente para ordens de produção confirmadas e estimadas
description: O detalhamento da lista de materiais se comporta de maneira diferente para ordens de produção confirmadas e estimadas para trabalho criado manualmente
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 94d4b00ea30396923a61b2748cf1aaeedc0af8af
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475577"
---
# <a name="bom-explosion-behaves-differently-for-firmed-and-estimated-production-orders"></a>O detalhamento da BOM se comporta de forma diferente para ordens de produção confirmadas e estimadas

## <a name="symptoms"></a>Sintomas

Quando uma ordem de produção é firmada, os itens não são detalhados quando você detalha a lista de materiais (BOM). No entanto, quando você cria manualmente uma ordem de serviço e estima a ordem de produção, os itens são detalhados.

### <a name="resolution"></a>Resolução

O detalhamento que ocorre quando a ordem de produção é firmada apontará para a ordem planejada, mas não parece que a ordem planejada está atualmente firmada neste caso. No entanto, se a ordem de produção foi estimada, o detalhamento é acionado a partir da ordem de produção liberada, onde não existe ordem planejada.
