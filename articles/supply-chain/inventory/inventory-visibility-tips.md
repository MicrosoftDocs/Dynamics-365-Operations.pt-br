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
ms.openlocfilehash: 1f6ade36ac184a3c8bf790fc0d899ea01d90c8d2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952406"
---
# <a name="inventory-visibility-tips"></a>Dicas de Visibilidade de Estoque

[!include [banner](../includes/banner.md)]

Veja algumas dicas que você deve considerar ao configurar e usar o Suplemento de Visibilidade de Estoque:

- No momento, o Suplemento de Visibilidade de Estoque oferece suporte somente a ambientes Microsoft Dataverse criados com o Microsoft Dynamics Lifecycle Services (LCS). Se seu ambiente do Dataverse foi criado de alguma outra forma (por exemplo, usando o centro de administração do Power Apps) e se ele está vinculado ao seu ambiente do Dynamics 365 Supply Chain Management, primeiro você peça à equipe de produto Visibilidade de Estoque para corrigir o problema de mapeamento. Você pode entrar em contato com a equipe em [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). A equipe informará quando seu ambiente estiver pronto para a instalação da Visibilidade de Estoque.
- Se você tiver mais de um ambiente LCS, crie outro aplicativo Azure Active Directory (Azure AD) para cada ambiente. Se você usar a mesma ID de aplicativo e ID de locatário para instalar o Suplemento de Visibilidade de Estoque para ambientes diferentes, ocorrerá uma saída de token para ambientes mais antigos. Somente a última instância do Suplemento de Visibilidade de Estoque instalada será válida.
- No momento, a Visibilidade de Estoque não tem suporte para ambientes hospedados na nuvem. Ela só tem suporte para ambientes de nível 2+.
- No momento, a interface de programação de aplicativo (API) oferece suporte à consulta de até 100 itens individuais por valor de `ProductID`. Diversos valores `SiteID` e `LocationID` também podem ser especificados em cada consulta. O limite máximo é definido como `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- A API em massa pode retornar um máximo de 512 registros para cada solicitação.
- A fonte de dados `fno` é reservada para o Supply Chain Management. Se o Suplemento de Visibilidade de Estoque estiver integrado a um ambiente do Supply Chain Management, recomendamos que você não exclua as configurações relacionadas a `fno` na [fonte de dados](inventory-visibility-configuration.md#data-source-configuration).
- A Visibilidade de Estoque não pode alterar dados para a fonte de dados `fno`. O fluxo de dados é unidirecional, o que significa que todas as alterações de quantidade para a fonte de dados `fno` devem ser provenientes do seu ambiente do Supply Chain Management. Portanto, não é possível usar a API para enviar solicitações de alteração ou reserva disponíveis para a fonte de dados `fno`.
- Se você adicionar uma ou mais novas medidas ao seu ambiente do Supply Chain Management, também deverá adicioná-las na Visibilidade do Estoque. No entanto, todas as alterações de quantidade para novas medidas devem ser originadas no seu ambiente do Supply Chain Management.
- No momento, a [configuração da partição](inventory-visibility-configuration.md#partition-configuration) consiste em duas dimensões base (`SiteId` e `LocationId`) que indicam como os dados são distribuídos. As operações na mesma partição podem oferecer melhor desempenho a um custo menor. A solução inclui essa configuração de partição por padrão. Portanto, *você não precisa defini-la*. Não personalize a configuração de partição padrão. Se você excluí-la ou alterá-la, provavelmente causará um erro inesperado.
- As dimensões base definidas na configuração da partição não devem ser definidas na [configuração de hierarquia de índice de produtos](inventory-visibility-configuration.md#index-configuration).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
