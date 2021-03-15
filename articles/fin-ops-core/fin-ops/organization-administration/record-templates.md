---
title: Visão geral de modelos de registro
description: Este artigo introduz o conceito de modelos de registro e explica como podem ser usados para criar registros que compartilham informações.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca9ddaed0c4aad6aeb3877384778d33f83e6e4aa
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796841"
---
# <a name="record-templates-overview"></a>Visão geral de modelos de registro

[!include [banner](../includes/banner.md)]

Este artigo introduz o conceito de modelos de registro e explica como podem ser usados para criar registros que compartilham informações.

Os modelos de registro podem ajudar a criar registros mais rapidamente. No entanto, é possível criar apenas modelos de registro para alguns tipos de registro.

Por exemplo, digamos que você esteja inserindo informações de aluguel para uma empresa de aluguel de carros localizada em San Francisco. Como é provável que a maioria dos clientes sejam da área de San Francisco, seria interessante já preencher automaticamente os valores dos campos **Estado**, **País** e **Cidade** no formulário de aluguel.

> [!NOTE]
> Você pode aplicar modelos apenas nas áreas às quais você tem acesso. No entanto, todos os títulos de modelo são visíveis para você ao criar um novo registro, e também para outros usuários, se você está criando modelos que serão disponibilizados para todos os usuários. Considere isso ao nomear modelos. Por exemplo, evite o uso de nomes que incluam palavras como "comissão" se for confidencial que alguns funcionários da empresa recebem salários com base em comissões.

Quando um ou mais modelos aos quais você tem acesso existem para um formulário específico, e você tenta criar um novo registro no formulário, a página **Selecione um modelo para** é exibida. Quando você seleciona um modelo da lista, o novo registro é criado e contém as informações padrão baseadas no modelo que você selecionou. Se você não deseja usar modelos ao criar novos registros, marque a caixa de seleção **Não perguntar novamente** na página **Selecionar um modelo para**. Para exibir a caixa de diálogo de seleção de modelos novamente, clique em um registro com o botão direito do mouse, clique em **Informações sobre registro** e em **Mostrar seleção de modelo**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]