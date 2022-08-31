---
title: Dicas de visibilidade de estoque
description: Este artigo fornece algumas dicas que você deve considerar ao configurar e usar o Suplemento de Visibilidade de Estoque.
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
ms.openlocfilehash: 3bdd161815a15d5c39b3c0afc176a288c8d9055a
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306075"
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
- Sua [configuração de hierarquia de índice de produtos](inventory-visibility-configuration.md#index-configuration) deve incluir pelo menos uma hierarquia de índice (por exemplo, contendo a dimensão base `Empty`); caso contrário, as consultas falharão com o erro "Nenhuma hierarquia de índice foi definida".
- A fonte de dados `@iv` é uma fonte de dados predefinida e as medidas físicas definidas em `@iv` com o prefixo `@` são medidas predefinidas. Essas medidas são uma configuração predefinida para o recurso de alocação e, portanto, não são alteradas nem excluídas, ou você provavelmente encontrará erros inesperados ao usar o recurso de alocação.
- Você pode adicionar novas medidas físicas à medida calculada predefinida `@iv.@available_to_allocate`, mas não deve alterar seu nome.
- Se você restaurar um banco de dados do Supply Chain Management, o banco de dados restaurado poderá conter dados que não são mais consistentes com os dados antes sincronizados pela visibilidade de estoque para o Dataverse. Essa inconsistência de dados pode causar erros do sistema e outros problemas. Portanto, é importante sempre limpar todos os dados relacionados à visibilidade do estoque do Dataverse antes de restaurar um banco de dados do Supply Chain Management. Para obter detalhes, consulte [Limpar dados de visibilidade de estoque do Dataverse antes de restaurar o banco de dados do Supply Chain Management](inventory-visibility-setup.md#restore-environment-database).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
