---
title: Sequência numérica de gerenciamento de transporte
description: Este tópico descreve como configurar sequências numéricas para gerenciamento de transporte.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b7bb6c9338808828a41801a85a1b93b420e9c75b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004720"
---
# <a name="transportation-management-number-sequence"></a>Sequência numérica de gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Use a página **Sequências numéricas** no módulo de gerenciamento de transporte para configurar vários números profissionais. Os números profissionais são usados pelas transportadoras para organizar e rastrear o andamento de cada remessa.

## <a name="create-a-number-sequence-for-a-pro-number"></a>Criar uma sequência numérica para um número progressivo

Para criar uma sequência numérica para um número progressivo, faça o seguinte:

1. Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Sequências numéricas**.
1. Selecione **Novo** para criar uma sequência numérica.
1. Digite uma ID exclusiva e um nome descritivo para a sequência numérica.
1. No campo **Tipo de sequência numérica**, *Número progressivo* é a única opção.
1. No campo **Dígito de verificação**, *Dígito de verificação* é a única opção e é configurado como um mecanismo genérico.
1. Na FastTab **Sequência**, fornaça informações sobre a sequência.
1. Feche a página.

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a>Vincular uma sequência numérica a uma transportadora

Para vincular uma sequência numérica a uma transportadora, faça o seguinte:

1. Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Transportadoras**.
1. Selecione uma transportadora.
1. Selecione **Editar**.
1. Na FastTab **Visão geral**, selecione uma opção no campo **Sequência numérica progressiva**.
1. Feche a página.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]