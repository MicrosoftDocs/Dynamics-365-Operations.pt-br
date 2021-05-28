---
title: Não é possível aplicar um modelo a um produto liberado
description: Não é possível aplicar um modelo a um produto liberado.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026262"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a>Não é possível aplicar um modelo para criar um produto liberado

Número de KB: 4612097

## <a name="symptoms"></a>Sintomas

Ao criar um novo produto liberado usando a caixa de diálogo **Novo produto liberado**, você pode selecionar um modelo. O modelo deve fornecer configurações padrão para muitos campos do novo produto liberado. No entanto, alguns ou todos os campos não são definidos após a seleção do modelo.

## <a name="cause"></a>Causa

Muitas páginas no Microsoft Dynamics 365 Supply Chain Management permitem que você crie um modelo que estabelece as configurações iniciais para os registros mostrados nessas páginas. Você pode criar um desses modelos, selecionando **Informações sobre registro** na guia **Opções** do Painel de Ações. No entanto, os produtos liberados são muito mais complexos do que a maioria dos outros tipos de registros. Embora você possa selecionar **Informações sobre registro** na página **Produtos liberados** para criar um modelo e, embora possa selecionar esse modelo ao criar um produto liberado, o modelo não fornecerá os valores de campo esperados para o novo produto liberado. Portanto, não é possível usar os modelos de "informações sobre registro" para produtos liberados. Em vez disso, você deve criar modelos de produto dedicados.

## <a name="resolution"></a>Resolução

Para criar um modelo de produto, use o menu **Modelo** da guia **Produto** do Painel de Ações, não o botão **Informações sobre registro** na guia **Opções**.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. No Painel de Ações, na guia **Produto**, no grupo **Novo**, selecione **Modelo** e selecione **Criar modelo pessoal** ou **Criar modelo compartilhado**, conforme apropriado.
