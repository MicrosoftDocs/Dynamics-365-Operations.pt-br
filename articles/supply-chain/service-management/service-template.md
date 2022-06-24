---
title: Modelos de Serviço
description: Você pode definir um contrato de serviço como um modelo e copiar posteriormente as linhas do modelo para outro contrato ou ordem de serviço.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7c99e56751230a7b8881dc55c1d460674cc6f0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850471"
---
# <a name="service-templates"></a>Modelos de Serviço

[!include [banner](../includes/banner.md)]

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

## <a name="related-articles"></a>Artigos relacionados

[Copiar linhas de modelos de serviço](copy-service-template-lines.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]