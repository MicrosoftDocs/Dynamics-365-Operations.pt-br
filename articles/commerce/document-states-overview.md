---
title: Estados de documento e de ciclo de vida
description: Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
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
ms.openlocfilehash: 8aad7ef8425e46182c669686710dfc178abc418f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410194"
---
# <a name="document-states-and-lifecycle"></a>Estados de documento e de ciclo de vida

[!include [banner](includes/banner.md)]

Este tópico abrange vários estados do documento de elementos de página no Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Descrições de estado do documento

O tópico [Elementos da página](page-elements-overview.md) lista vários tipos de documentos no sistema de gerenciamento do conteúdo (CMS). Esses tipos de documentos podem ter vários estados na ferramenta de criação. Os estados de documento ajudam a evitar conflitos de dados e a aplicar o controle de versão. Eles determinam quem pode alterar os documentos, quando documentos podem ser alterados e, quando as alterações podem ser exibidas por outros contatos.

A tabela a seguir mostra os estados possíveis de documento de elementos de página em Comércio.

| Estado do documento      | Ação para criação de site        | descrição                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Check-out efetuado         | Selecione **Editar**.           | O documento aplicável foi enviado para você. Enquanto um documento está nesse estado, ele não pode ser alterado por outros usuários do sistema autenticados e todas as alterações feitas no documento são visíveis somente para você. |
| Salvo               | Selecione **Salvar**.           | As alterações feitas em um documento com check-out são salvas no banco de dados, mas o documento ainda não foi verificado ou publicado. As alterações salvas não são visíveis para outros usuários autenticados do sistema até o autor selecionar **Terminar edição**. Eles não estão visíveis para os usuários externos até que o item seja publicado. |
| Descartar check-out | Selecione **Descartar edições**.  | Todas as alterações no documento com check-out são descartadas, e o item é revertido para a última versão com check-in. |
| Check-in efetuado          | Selecione **Concluir edição**. | O check-in do documento editado será feito. Todas as alterações são visíveis para outros usuários do sistema autenticados, e esses usuários podem editar o documento. Cada check-in cria uma registro de versão do documento no histórico do item. |
| Publicado           | Selecione **Publicar**.        | O documento é publicado, e as alterações são enviadas para seu local dinâmico e tornam-se detectáveis por usuários externos. Os itens podem ser publicados somente se tiverem sido feitos check-in primeiro, selecionando **Concluir edição**. |

## <a name="additional-resources"></a>Recursos adicionais

[Maneiras de adicionar conteúdo](add-manage-content.md)

[Glossário do modelo de página](page-elements-overview.md)

[Trabalhar com grupos de publicações](publish-groups.md)

[Habilitar e usar o compartilhamento entre canais](cross-channel-sharing.md)

[Trabalhar com módulos](work-with-modules.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Personalizar a navegação do site](customize-site-navigation.md)
