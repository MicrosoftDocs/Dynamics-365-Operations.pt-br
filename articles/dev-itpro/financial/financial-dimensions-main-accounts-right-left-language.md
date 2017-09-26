---
title: "Dimensões financeiras e contas principais de um idioma da direita para a esquerda"
description: "Este tópico descreve algumas das decisões de implementação que devem ser considerados ao usar um idioma da direita para a esquerda, e você deve configurar dimensões financeiras e contas principais."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: e28d3b318c2efa0b9d0da1154692f8e64c553e64
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="financial-dimensions-and-main-accounts-in-a-right-to-left-language"></a>Dimensões financeiras e contas principais de um idioma da direita para a esquerda

[!include[banner](../includes/banner.md)]


Este tópico descreve algumas das decisões de implementação que devem ser considerados ao usar um idioma da direita para a esquerda, e você deve configurar dimensões financeiras e contas principais.

Dimensões financeiras e contas são componentes-chave principais da fase de planejamento para uma implementação. Após dimensões financeiras e contas principais serem criadas no sistema, elas são usadas nas páginas **Configurar estruturas de conta**, **Estruturas de regra avançada** e **Configuração de dimensão financeira para integração de aplicativos**. A ordem definida nas páginas é usada no sistema para a entrada de dados e o consumo. Em alguns locais no sistema, dimensões financeiras e contas principais são exibidas em dois campos separados. Entretanto, em outros locais como, diários, dimensões financeiras e contas principais aparecem como uma única sequência de caracteres.

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Práticas recomendadas para configurar dimensões financeiras e contas principais em um sistema da direita para a esquerda

-   Quando você selecionar o delimitador de gráficos de contas, selecione uma das duas opções de delimitador: hífen duplo (--), barra dupla (||) ou ponto duplo (..), ou sublinhado duplo (\_\_).
-   Ao criar valores de dimensão financeira e conta principal, use números somente e caracteres da direita para a esquerda de idioma.
-   Evite o delimitador gráfico selecionado de contas nos valores da dimensão financeira e conta principal.

Ao executar essas práticas recomendadas, você ajuda a garantir representação consistente do pedido definido pelo usuário ao longo do sistema.




