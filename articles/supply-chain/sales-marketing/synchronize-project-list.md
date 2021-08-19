---
title: Sincronizar lista de projetos do Supply Chain Management com o Field Service
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 920c3741ab45f4ae88ea5febba583d34b5a1230cd25316226db850730927798d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717834"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Sincronizar lista de projetos do Supply Chain Management com o Field Service

[!include[banner](../includes/banner.md)]

Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar projetos do Dynamics 365 Supply Chain Management com o Dynamics 365 Field Service.

[![Sincronização de processos empresariais entre o Supply Chain Management e o Field Service.](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Modelos e tarefas
O modelo a seguir e as tarefas subjacentes são usados para executar a sincronização de projetos do Supply Chain Management com o Field Service.

**Modelo na integração de dados**
- Projetos (Supply Chain Management para Field Service)

**Tarefas no projeto de integração de dados**
- Projetos

As seguintes tarefas de sincronização necessárias antes da sincronização a lista de projetos:
- Contas (Sales para Supply Chain Management) 

## <a name="entity-set"></a>Conjunto de entidades
| Field Service           | Gerenciamento da Cadeia de Fornecedores  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projetos                |

## <a name="entity-flow"></a>Fluxo de entidades
Os projetos são criados no Supply Chain Management. Os projetos com **Tipo de projeto** definido como **Tempo e material** e **Estágio de projeto** definido como **Em andamento** serão sincronizados com a entidade **Projeto Externo** no Field Service, incluindo número do projeto, nome do projeto, estágio do projeto e informações da conta do cliente. A lista **Projeto Externo** é usada para emparelhar ordens de serviço do Field Service com projetos do Supply Chain Management.

## <a name="field-service-crm-solution"></a>Solução Field Service CRM
A entidade **Projeto Externo** obtém todos os projetos do Supply Chain Management. O campo **Projeto externo** foi adicionado à entidade **Ordem de trabalho**. Este campo é uma pesquisa, portanto, ao marcar sua ordem de serviço com um projeto, a ordem de venda será conectada a um projeto no Supply Chain Management. Depois que o **Status do sistema** mudar de **Aberto - Em Andamento (690.970.000)** para a um status superior, o campo **Projeto externo** será bloqueado e você não poderá mais adicionar, remover ou alterar o valor.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento
### <a name="supply-chain-management"></a>Gerenciamento da Cadeia de Fornecedores
Habilitar o controle de alterações para projetos da entidade Dados.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados


### <a name="projects-supply-chain-management-to-field-service-projects"></a>Projetos (Supply Chain Management para Field Service): Projetos

[![Mapeamento de modelo na Integração de dados.](./media/FSProject1.png)](./media/FSProject1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]