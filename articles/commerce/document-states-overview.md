---
title: Estados de documento e de ciclo de vida
description: Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: edb81efc45fc5e7eed32cb7d9b8fda5ade987dd4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914878"
---
# <a name="document-states-and-lifecycle"></a>Estados de documento e de ciclo de vida

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Descrições de estado do documento

O tópico [Elementos da página](page-elements-overview.md) lista vários tipos de documentos no sistema de gerenciamento do conteúdo (CMS). Esses tipos de documentos podem ter vários estados na ferramenta de criação. Os estados de documento ajudam a evitar conflitos de dados e a aplicar o controle de versão. Eles determinam quem pode alterar os documentos, quando documentos podem ser alterados e, quando as alterações podem ser exibidas por outros contatos.

A tabela a seguir mostra os estados possíveis de documento de elementos de página em Comércio.

| Estado do documento | Descrição |
|---|---|
| Com Check-out | Quando um item de CMS está com check-out para você, ele não pode ser editado por outros usuários autenticados do sistema. Quaisquer alterações feitas ao item são visíveis apenas por você. |
| Com Check-in | Quando um item de CMS realiza check-in, as alterações são visíveis para outros usuários autenticados do sistema e esses usuários poderão efetuar check-out do item e editá-lo. Cada check-in cria uma registro de versão do documento no histórico do item. |
| Publicado | Quando um item de CMS é publicado, ele é enviado em seu site e torna-se perceptível na Internet por usuários externos não autenticados. Os itens podem ser publicados somente se o check-in tiver sido efetuado. |
| Salvo | Mudanças que foram realizadas a um item de CMS com check-out podem ser salvos ao CMS antes do item ser verificado ou publicado. Essas alterações salvas não são visíveis para outros usuários autenticados do sistema até o item ter o check-in realizado. Eles não estão visíveis para os usuários externos até que o item seja publicado. |
| Descartar check-out | Quando um item feito o check-out de CMS for rejeitado, alterações salvas serão excluídas e o item volta para versão na qual o check-in foi realizado recentemente. |

## <a name="additional-resources"></a>Recursos adicionais

[Maneiras de adicionar conteúdo](add-manage-content.md)

[Glossário do modelo de página](page-elements-overview.md)

[Trabalhar com grupos de publicações](publish-groups.md)

[Trabalhar com módulos](work-with-modules.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Personalizar a navegação do site](customize-site-navigation.md)
