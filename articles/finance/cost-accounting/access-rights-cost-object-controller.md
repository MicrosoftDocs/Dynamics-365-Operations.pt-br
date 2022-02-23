---
title: ​Direitos de acesso de controladores de objeto de custo
description: Este tópico fornece informações sobre direitos de acesso para controladores do objeto de custo.
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fd1ed875e5c6e3f8ada3b13ea8cc05f98526691d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440384"
---
# <a name="access-rights-for-cost-object-controllers"></a>​Direitos de acesso de controladores de objeto de custo

[!include [banner](../includes/banner.md)]

O espaço trabalho **Controle de custos** é uma empresa central onde os gerentes podem exibir o desempenho de seus objetos de custo. Este espaço de trabalho permite que os gerentes consumam dados da contabilidade de custo mesmo que não sejam contadores. Por motivo de segurança, gerentes somente podem consultar os dados da contabilidade de custo relacionados a objetos específicos de custo pelos quais eles são responsáveis.

Existem quatro funções exclusivas na contabilização de custos.

| Nome da função               | Licença      |
|-------------------------|--------------|
| Gerenciador de contabilização de custos | Atividade     |
| Contador de custos         | Operations   |
| Contador de custos   | Operations   |
| Controlador do objeto de custo  | Membros da equipe |

Este tópico explica como atribuir a função **Controlador do objeto de custo** a um gerente.

Quando a função **Controlador do objeto de custo** for designada a um gerente, ele poderá executar as seguintes tarefas:

- Acessar o espaço de trabalho **Controle de custo** (no cliente).

    - Detalhar e ter acesso de exibição às páginas que suportam a experiência detalhada.

- Acessar o espaço de trabalho **Controle de custo** (no aplicativo móvel).

> [!NOTE]
> A função **Controlador do objeto de custo** não controla os objetos de custo pelo qual o usuário pode acessar e exibir dados. A segurança em nível de linha é fornecida por meio das hierarquias de dimensões e de hierarquia de lista de acesso.

## <a name="grant-access-rights"></a>Conceder direitos de acesso
O exemplo a seguir mostra como pode ser uma hierarquia de dimensões.

**Detalhes de hierarquias de dimensão**

| Nome de hierarquia de dimensões | Dimensão    | Nome do tipo de hierarquia de dimensões      | Acessar hierarquia de lista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organização             | Centros de custos | Hierarquia de classificação de dimensões | **Sim**               |

Você pode usar a Guia Rápida **Usuários** no designer de hierarquia para inserir uma ou várias ids de usuário em cada nó.

|                                   | Usuários            | Intervalos de membros de dimensão   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| **Nós**                         | **ID do Usuário**      | **Membro da dimensão de origem** | **Membro da dimensão de destino** |
| Organização                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Administrador                 | Abril            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanças   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RH        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produção            | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Embalagem | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Montagem  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> Os contadores devem ser atribuídos ao nível de hierarquia superior para que possam consultar todas as entradas na contabilização de custo.

Antes da hierarquia da lista de acesso e de suas configurações de segurança serem aplicadas, a opção **Habilitar acesso de visualização para membros de dimensão de objeto de custo** deve ser definida como **Sim** na guia **Geral** da página **Parâmetros de contabilização de custos** (**Contabilização de custo** > **Configuração** > **Parâmetros**).

As configurações da hierarquia da lista de acesso são usadas para controlar os dados que são mostrados nas seguintes áreas:

- Espaço de trabalho **Controle de custo** (no cliente):

    - Dados nas páginas usadas para o detalhamento

- Espaço de trabalho **Controle de custo** (no aplicativo móvel):

    - Saldos em cartões

- Microsoft Power BI:

    - Dados mostrados em visualizações do Power BI
    - Visualizações de dados do Power BI incorporadas no cliente do Dynamics 365 Finance

> [!IMPORTANT]
> - Antes que a hierarquia da lista de acesso possa afetar os dados no Power BI, a hierarquia da lista de acesso e a segurança em nível de linha no Power BI devem ser emparelhadas. Para obter mais informações, consulte [Configurar segurança para o pacote de conteúdo de contabilização de custo](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - Esta seção mostra os pré-requisitos que devem estar em vigor para usar o espaço de trabalho **Controle de custos**.

Recursos adicionais

- [Espaço de trabalho de controle de custos](cost-control-workspace.md)
- [Hierarquia da dimensão](dimension-hierarchy.md)
- [Configurar segurança para o pacote de conteúdo de contabilização de custo](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)
