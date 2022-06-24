---
title: Introdução a locais funcionais
description: Este artigo oferece uma visão geral de locais funcionais em Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationEditSubLocations, EntAssetFunctionalLocationLookup, EntAssetFunctionalLocationRename, EntAssetFunctionalLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a1c8c4db9aee68584ab35949745132091a34a58
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882827"
---
# <a name="introduction-to-functional-locations"></a>Introdução a locais funcionais

[!include [banner](../../includes/banner.md)]

 

Este artigo oferece uma visão geral de locais funcionais em Gerenciamento de Ativos. Os locais funcionais são elementos de uma estrutura técnica, como unidades funcionais em um sistema. Os locais funcionais são criados hierarquicamente e você instala ativos neles. A configuração de locais funcionais na sua empresa depende dos requisitos da empresa.

Estes são alguns exemplos de como você pode usar locais funcionais:

- **Funcional** – Os locais funcionais podem ser orientados ao usuário e usados para gerenciar ativos que têm comportamento semelhante.
- **Relacionado a processo** – Os locais funcionais podem ser orientados a fluxo de trabalho.
- **Espacial** – Os locais funcionais podem representar localizações geográficas ou sites.

Cada local funcional é gerenciado independentemente em Gerenciamento de Ativos. Estes são alguns dos recursos úteis de locais funcionais:

- Configure especificações de local funcional.
- Configure requisitos de especificação de ativos.
- Configure sequências de manutenção para manutenção preventiva e reativa.
- Gerenciar ativos instalados.
- Rastreie solicitações de ativos e ordens de serviço relacionadas a ativos instalados.
- Rastreie falhas registrados em ativos.
- Rastreie custos de manutenção nos ativos que estão relacionados a um local funcional em determinado momento.

Os locais funcionais fornecem o rastreamento de ativos em relação a solicitações, ordens de serviço, registros de falhas, avaliações de condição, registros de interrupção de produção e registros de contador de ativos.

> [!NOTE]
> Se um ativo for instalado em vários locais funcionais no seu tempo de vida, os custo poderão ser relativos a cada local. Ou seja, os custos de ativos são sempre relacionadas ao local funcional no qual o ativo foi instalado em algum momento.

Os locais funcionais **não** são flexíveis. Portanto, após configurar uma hierarquia de locais funcionais, você não poderá mover locais ao redor dela. 

Depois de criar uma hierarquia de locais funcionais, a próxima etapa será instalar ativos nela. Para obter mais informações, consulte [Instalar ativos em locais funcionais](../functional-locations/install-objects-on-functional-locations.md).

## <a name="all-functional-locations"></a>Todos os locais funcionais

Selecione **Gerenciamento de ativos** \> **Comum** \> **Locais funcionais** \> **Todos os locais funcionais** para abrir a página de lista **Todos os locais funcionais**. Esta página mostra todos os locais funcionais e algumas das informações relacionadas a cada um. Para exibir apenas locais funcionais ativos, selecione **Locais funcionais ativos**. Para exibir somente os locais funcionais aos quais você está relacionado como um trabalhador, selecione **Meus locais funcionais ativos**. (Essa relação é configurada na página **Trabalhadores**. Para obter mais informações, consulte [Trabalhadores de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).)

Na página de lista **Todos os locais funcionais**, selecione um link na coluna **Local funcional** para exibir os detalhes do registro selecionado. Para editar o local funcional, selecione o botão **Editar**. A exibição de detalhes mostra informações detalhadas relacionadas ao local. Ela também incluem um painel **Informações relacionadas** à direita. Esse painel mostra a hierarquia de locais funcionais. Você pode expandir e recolher o painel **Informações relacionadas**.

Os botões no Painel de Ação estão organizados em guias. A tabela a seguir descreve brevemente os botões relacionados ao Asset Management.

| Nome do botão                         | Descrição                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Edição                                | Alterne entre o modo de edição e o modo de exibição da página.                                                                                         |
| Novos                                 | Crie um novo local funcional.                                                                                                            |
| Excluir                              | Exclua o local funcional selecionado.                                                                                                     |
| Renomear                              | Renomeie o local funcional selecionado.                                                                                                     |
| Copie a estrutura do local funcional  | Copie a hierarquia de locais funcionais.                                                                                                      |
| Instalar ativo                       | Instale um ativo, incluindo ativos filho, no local funcional.                                                                        |
| Substituir ativo                       | Substitua a hierarquia de ativos por outra hierarquia de ativos no local funcional.                                                         |
| Controle de Custo                        | Abra a página **Controle de custos do local funcional**, em que você pode criar um cálculo de custo para o local funcional selecionado.                |
| Controle de horas                        | Abra a página **Controle de horas do local funcional**, em que você pode criar um cálculo de custo para o local funcional selecionado.                |
| Ativos                              | Abra a página **Todos os ativos**, em que você pode exibir uma lista de ativos que estão relacionados ao local funcional selecionado.                      |
| Solicitações                            | Abra a página **Solicitações ativas**, em que você pode exibir uma lista de solicitações que estão relacionadas ao local funcional selecionado.               |
| Ordens de serviço                         | Abra a página **Ordens de serviço ativas**, em que você pode exibir uma lista de ordens de serviço que estão relacionadas ao local funcional selecionado.         |
| Falhas                              | Abra a página **Falhas de ativos**, em que você pode exibir uma lista de registros de falhas de ativos que estão relacionados ao local funcional selecionado. |
| Atualizar o estado do local funcional    | Atualize o estado do local funcional selecionado.                                                                                        |
| Log de estados de ciclo de vida                 | Exiba um log que mostre os estados do local funcional selecionado.                                                                        |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]