---
title: Atualizar guias de integração no Dynamics 365 Talent - Onboard
description: Este tópico explica como atualizar guias de integração no Microsoft Dynamics 365 Talent - Onboard e como enviar alterações nos guias existentes.
author: andreabichsel
manager: ''
ms.date: 06/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6175061456a03228043ea13767845cf4b54d6b2e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460376"
---
# <a name="update-onboarding-guides"></a>Atualizar guias de integração

[!include [banner](includes/banner.md)]

Se tiver que fazer alterações nos guias de integração no Microsoft Dynamics 365 Talent: Onboard, você poderá atualizá-los e enviar as alterações, mesmo que já tenha enviado os guias. Você tem duas opções para atualizar um guia de integração:

- Editar o guia de integração diretamente e salvar suas alterações.
- Editar o modelo de integração e enviar as alterações para todos os guias de integração que foram criados com base nele.

## <a name="edit-an-onboarding-guide-directly"></a>Editar um guia de integração diretamente

1. No menu esquerdo, selecione **Guias**.
2. Selecionar o guia que deseja editar.
3. Faça todas as alterações desejadas e selecione o botão **Salvar** (o símbolo de disco).

    ![[Salvar alterações em um guia de integração](./media/onboard-save.png)](./media/onboard-save.png)

O Onboard enviará ao novo contratado um e-mail que indica quais foram as alterações. Para fácil identificação, uma etiqueta **Novo** aparecerá próxima a cada alteração.

## <a name="update-multiple-guides-by-editing-the-onboarding-template"></a>Atualizar várias guias editando o modelo de integração

1. No menu esquerdo, selecione **Modelos**.
2. Em **Meus modelos**, selecione o modelo que deseja editar.
3. Faça todas as alterações desejadas e selecione o botão **Salvar** (o símbolo de disco).
4. Para enviar as alterações para todos os guias baseados no modelo, selecione **Enviar estas alterações**.

    ![[Enviar as alterações de um modelo de integração para todos os guias criados com base nele](./media/onboard-push-changes.png)](./media/onboard-push-changes.png)

As alterações serão visíveis para novas contratações que abrem os guias de integração. Porém, o Onboard não enviará alertas de email para novas contratações para que elas saibam que o guia de integração foi alterado. Para fácil identificação, uma etiqueta **Novo** aparecerá próxima a cada alteração. 
