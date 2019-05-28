---
title: Dimensões financeiras e contas principais de idiomas da direita para a esquerda
description: Este tópico descreve algumas das decisões de implementação que devem ser considerados ao usar um idioma da direita para a esquerda, e você deve configurar dimensões financeiras e contas principais.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9609c052083dc3157618584da9311211ea036eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1555585"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>Dimensões financeiras e contas principais de idiomas da direita para a esquerda

[!include [banner](../includes/banner.md)]

Este tópico descreve algumas das decisões de implementação que devem ser considerados ao usar um idioma da direita para a esquerda, e você deve configurar dimensões financeiras e contas principais.

Dimensões financeiras e contas são componentes-chave principais da fase de planejamento para uma implementação. Após dimensões financeiras e contas principais serem criadas no sistema, elas são usadas nas páginas **Configurar estruturas de conta**, **Estruturas de regra avançada** e **Configuração de dimensão financeira para integração de aplicativos**. A ordem definida nas páginas é usada no sistema para a entrada de dados e o consumo. Em alguns locais no sistema, dimensões financeiras e contas principais são exibidas em dois campos separados. Entretanto, em outros locais como, diários, dimensões financeiras e contas principais aparecem como uma única sequência de caracteres.

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Práticas recomendadas para configurar dimensões financeiras e contas principais em um sistema da direita para a esquerda

-   Quando você selecionar o delimitador de gráficos de contas, selecione uma das duas opções de delimitador: hífen duplo (--), barra dupla (||) ou ponto duplo (..), ou sublinhado duplo (\_\_).
-   Ao criar valores de dimensão financeira e conta principal, use números somente e caracteres da direita para a esquerda de idioma.
-   Evite o delimitador gráfico selecionado de contas nos valores da dimensão financeira e conta principal.

Ao executar essas práticas recomendadas, você ajuda a garantir representação consistente do pedido definido pelo usuário ao longo do sistema.



