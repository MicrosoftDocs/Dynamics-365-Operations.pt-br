---
title: Dicas de Visibilidade de Estoque
description: Este tópico fornece algumas dicas que você deve considerar ao configurar e usar o Suplemento de Visibilidade de Estoque.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: f5fb4c7cb941b352bbc6e2fcf5347244e1c8a40c
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920790"
---
# <a name="inventory-visibility-tips"></a>Dicas de Visibilidade de Estoque

[!include [banner](../includes/banner.md)]

Veja algumas dicas que você deve considerar ao configurar e usar o Suplemento de Visibilidade de Estoque:

- No momento, o Suplemento de Visibilidade de Estoque oferece suporte somente a ambientes Microsoft Dataverse criados com o Microsoft Dynamics Lifecycle Services (LCS). Se seu ambiente do Dataverse foi criado de alguma outra forma (por exemplo, usando o centro de administração do Power Apps) e se ele está vinculado ao seu ambiente do Dynamics 365 Supply Chain Management, primeiro você peça à equipe de produto Visibilidade de Estoque para corrigir o problema de mapeamento. Você pode entrar em contato com a equipe em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). A equipe informará quando seu ambiente estiver pronto para a instalação da Visibilidade de Estoque.
- Se você tiver mais de um ambiente LCS, crie outro aplicativo Azure Active Directory (Azure AD) para cada ambiente. Se você usar a mesma ID de aplicativo e ID de locatário para instalar o Suplemento de Visibilidade de Estoque para ambientes diferentes, ocorrerá uma saída de token para ambientes mais antigos. Somente a última instância do Suplemento de Visibilidade de Estoque instalada será válida.
- No momento, a Visibilidade de Estoque não tem suporte para ambientes hospedados na nuvem. Ela só tem suporte para ambientes de nível 2+.
- No momento, a interface de programação de aplicativo (API) oferece suporte à consulta de até 100 itens individuais por valor de `ProductID`. Diversos valores `SiteID` e `LocationID` também podem ser especificados em cada consulta. O limite máximo é definido como `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- A fonte de dados `fno` é reservada para o Supply Chain Management. Se o Suplemento de Visibilidade de Estoque estiver integrado a um ambiente do Supply Chain Management, recomendamos que você não exclua as configurações relacionadas a `fno` na [fonte de dados](inventory-visibility-configuration.md#data-source-configuration).
- No momento, a [configuração da partição](inventory-visibility-configuration.md#partition-configuration) consiste em duas dimensões base (`SiteId` e `LocationId`) que indicam como os dados são distribuídos. As operações na mesma partição podem oferecer melhor desempenho a um custo menor. A solução inclui essa configuração de partição por padrão. Portanto, *você não precisa defini-la*. Não personalize a configuração de partição padrão. Se você excluí-la ou alterá-la, provavelmente causará um erro inesperado.
- As dimensões base definidas na configuração da partição não devem ser definidas na [configuração de hierarquia de índice de produtos](inventory-visibility-configuration.md#index-configuration).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
