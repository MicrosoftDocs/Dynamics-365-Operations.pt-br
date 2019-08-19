---
title: Solicitações de manutenção
description: Este tópico fornece uma visão geral sobre o gerenciamento de solicitações de manutenção no Asset Management
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 56d4abee451e6e22b9b9cc2fd36a13648202e7df
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847427"
---
# <a name="maintenance-requests"></a>Solicitações de manutenção

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

As solicitações de manutenção são anotações ou declarações criadas para notificar um gerente ou planejador de que um ativo pode exigir um trabalho de manutenção ou de reparo, mas sem a criação de uma ordem de serviço. Se o conteúdo de uma solicitação de manutenção for considerado válido, uma ordem de serviço será criada com base na solicitação de manutenção.

As solicitações de serviço podem ser criadas para qualquer ativo no Asset Management. Diversos tipos de solicitações de serviço podem ser criados, dependendo de como sua empresa usa solicitações de manutenção. Eis alguns exemplos:

- Solicitações de manutenção
- Observação
- Correções ou aprimoramentos
- Investimentos
- Reparo de depósito (esse tipo é usado quando você recebe ativos de outro local para efetuar um trabalho de manutenção ou de reparo e então devolve o ativo após a conclusão do trabalho).

## <a name="view-maintenance-requests"></a>Exibir solicitações de manutenção

Para exibir solicitações de manutenção, selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção**, **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional**. Cada página de listagem mostra algumas das informações relacionadas a uma solicitação de manutenção.

![Figura 1](media/01-manage-maintenance-requests.png)

> [!NOTE]
> Use a página de listagem **Minhas solicitações de manutenção de local funcional** para exibir uma lista de solicitações de manutenção que contenham um ou mais locais funcionais aos quais você está relacionado como trabalhador ou ativos instalados em locais funcionais aos quais você está relacionado como trabalhador. Para obter informações sobre como configurar locais funcionais em funcionários de manutenção, consulte [Funcionários de manutenção e grupos de funcionários](../setup-for-objects/workers-and-worker-groups.md).
> 
> Embora as informações de conta de cliente estejam disponíveis no Asset Service Management (manutenção externa), elas não estão disponíveis no Asset Management (manutenção interna).

Para abrir a exibição de detalhes de um registro, na página de listagem **Todas as solicitações de manutenção**, na exibição de grade, selecione um link na coluna **Solicitação de manutenção**.

![Figura 2](media/02-manage-maintenance-requests.png)

Os botões no Painel de Ação estão organizados em guias. A tabela a seguir descreve brevemente os botões relacionados ao Asset Management.

| Nome do botão                      | Descrição |
|----------------------------------|-------------|
| Edição                             | Edite a solicitação de manutenção selecionada. |
| Novos                              | Crie uma nova solicitação de manutenção. |
| Excluir                           | Exclua a solicitação de manutenção selecionada. |
| Grupo de ordens de serviço                  | Conecte a solicitação de manutenção selecionada a um grupo de ordens de serviço. |
| Ordem de serviço                       | Crie uma ordem de serviço com base na solicitação de manutenção. |
| Falha do ativo                      | Clique em **Falhas de ativo**, onde você poderá criar um registro de falha sobre a solicitação de manutenção selecionada. |
| Ordens de serviço                      | Mostre uma lista de todas as ordens de serviço conectadas à solicitação de manutenção selecionada. |
| Atualizar o estado da solicitação de manutenção | Atualize o estado da solicitação de manutenção. |
| Log de estados de ciclo de vida              | Exiba um log que mostre os estados de ciclo de vida de solicitação de manutenção selecionada. |
| Detalhes da solicitação de manutenção      | Imprima um relatório que mostre detalhes da solicitação de manutenção selecionada. |
| Enviar ativo de empréstimo                  | Selecione um ativo de empréstimo que deve ser uma substituição temporária para o ativo selecionado na solicitação de manutenção selecionada. |
| Devolver o ativo de empréstimo                | Registre o ativo de empréstimo como devolvido. |

