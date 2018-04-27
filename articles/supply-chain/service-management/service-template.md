---
title: "Modelos de Serviço"
description: "Você pode definir um contrato de serviço como um modelo e copiar posteriormente as linhas do modelo para outro contrato ou ordem de serviço."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 09f2da382cd7f3e0e3d4bfa389e9cdf74f00b501
ms.openlocfilehash: ade518095b77141fb31b597a955dd23aaae119d7
ms.contentlocale: pt-br
ms.lasthandoff: 02/27/2018

---

# <a name="service-templates"></a>Modelos de Serviço

[!INCLUDE [banner](../includes/banner.md)]

Você pode definir um contrato de serviço como um modelo e copiar posteriormente as linhas do modelo para outro contrato ou ordem de serviço.

## <a name="example"></a>exemplo

Um cliente ao qual você presta serviços possui elevadores idênticos em cinco locais diferentes.

Você deseja configurar cinco contratos de serviço para o cliente, um para cada local.
Para limitar o trabalho de configuração repetitivo e garantir que as informações de configuração dos contratos sejam idênticas, você cria um contrato de serviço e especifica-o como modelo para o trabalho relacionado aos elevadores.

Agora, você poderá copiar as linhas do modelo para os cinco novos contratos de serviço de modo que cada contrato seja preenchido com essas linhas.

## <a name="create-a-template"></a>Criar um modelo

Ao criar um modelo de serviço, você cria um contrato de serviço com as linhas necessárias e, depois, associa o contrato a um grupo de modelos de serviço.

> [!NOTE]
> É possível definir um contrato de serviço como um modelo somente quando não há ordens de serviço associadas a ele. Além disso, nenhuma ordem de serviço pode ser gerada a partir de um contrato definido como modelo.

## <a name="copy-template-lines"></a>Copiar Linhas do Modelo

Você pode copiar linhas de um modelo de serviço para outro contrato de serviço ou para uma ordem de serviço.

Quando você copia linhas de um modelo para ordens ou contratos de serviço, os grupos de modelos são exibidos em um modo de exibição de árvore em que cada grupo pode ser expandido. Essa exibição permite que você visualize cada modelo e cada linha do modelo.

É mais fácil determinar as linhas do modelo de serviço que você deseja copiar agrupando os modelos com nomes que indiquem o seu uso.

## <a name="related-topics"></a>Tópicos relacionados

[Copiar linhas de modelos de serviço](copy-service-template-lines.md)

