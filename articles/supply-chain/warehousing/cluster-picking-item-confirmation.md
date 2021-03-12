---
title: Confirmação de produto para a separação do cluster
description: Este tópico descreve como você configura a verificação do item com a separação do cluster.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8f81d760e8c181891aeba92834577e8869fbdd8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001115"
---
# <a name="product-confirmation-for-cluster-picking"></a>Confirmação de produto para a separação do cluster

[!include [banner](../includes/banner.md)]

A separação do cluster permite que você escolha itens para várias ordens simultaneamente. Quando a separação do cluster é aplicada, confirmação do item é importante para verificar os itens adicionados aos clusters. Você pode verificar os itens na separação do cluster durante o processo de separação do cluster.

## <a name="where-it-applies"></a>Aplica-se a

A verificação do item da separação do cluster funciona da mesma maneira que quando você verifica itens em processos de separação não cluster. A configuração é baseada na configuração de código de barras de produto.

## <a name="set-up-item-verification-with-cluster-picking"></a>Configurar verificação do item com separação de cluster

1. No item de menu do dispositivo móvel, abra o formulário de configuração para a confirmação de trabalho: **Gerenciamento de depósito** > **Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Itens de menu do dispositivo móvel**.
1. Do item de menu de dispositivo móvel, abra a **Configuração de confirmação de trabalho**.

|        Opção        |                                    descrição                                    |
|----------------------|-----------------------------------------------------------------------------------|
| Confirmação do produto | Permite a você verificar cada peça de estoque do dispositivo móvel quando examinado. |
