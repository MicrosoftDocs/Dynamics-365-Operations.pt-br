---
title: Sincronizar contratos de projeto e projetos diretamente no Project Service Automation para o Finance and Operations
description: Este tópico descreve o modelo e as tarefas subjacentes usadas para sincronizar contratos de projeto e projetos diretamente do Microsoft Dynamics 365 Project Service Automation para o Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 76c62f3a503ff2a8c93143390fc91ef81fbf7d0f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250452"
---
# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Sincronizar contratos de projeto e projetos diretamente no Project Service Automation para o Finance and Operations

[!include[banner](../includes/banner.md)]

Este tópico descreve o modelo e as tarefas subjacentes usadas para sincronizar contratos de projeto e projetos diretamente do Dynamics 365 Project Service Automation para o Dynamics 365 Finance.

> [!NOTE] 
> Se estiver usando o Enterprise edition 7.3.0, instale o KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Fluxo de dados do Project Service Automation para o Finance

> [!NOTE]
> Antes de usar a solução de integração do Project Service Automation para o Finance, você deve estar familiarizado com o recurso de Integração de Dados do Dynamics 365.

A solução de integração do Project Service Automation para o Finance utiliza o recurso Integração de Dados para sincronizar dados nas instâncias do Project Service Automation e do Finance. O modelo de integração disponível com o recurso Integração de Dados permite o fluxo de dados sobre contratos de projeto, projetos, linhas de contrato de projeto e marcos de linha do contrato de projeto do Project Service Automation para o Finance.

A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance.

[![Fluxo de dados da integração do Project Service Automation com o Finance](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Modelos e tarefas

Para acessar os modelos disponíveis, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.

Os seguintes modelos e as tarefas subjacentes são usados para sincronizar contratos de projeto e projetos do Project Service Automation para o Finance:

### <a name="integrating-with-dynamics-365-project-service-automation-v2x"></a>Integração com o Dynamics 365 Project Service Automation v2.x
- **Nome do modelo na Integração de dados:** projetos e contratos (do PSA para o Fin and Ops)
- **Nome das tarefas no projeto:**

    - Contratos de projeto do PSA para o Fin and Ops
    - Projetos do PSA para o Fin and Ops
    - Linhas de contrato de projeto do PSA para o Fin and Ops
    - Marcos de linhas de contrato de projeto do PSA para o Fin and Ops
  
### <a name="integrating-with-dynamics-365-project-service-automation-v3x"></a>Integração com o Dynamics 365 Project Service Automation v3.x
Há uma alteração do esquema no Project Service Automation que afeta o modelo do marco de linha de contrato do projeto e o uso da versão v2 do modelo é necessário para integrar o Project Service Automation v3.x com o Dynamics 365.

- **Nome do modelo na Integração de dados:** projetos e contratos (do PSA 3.x para o Fin and Ops) - v2
- **Nome das tarefas no projeto:**

    - Contratos de projeto do PSA para o Fin and Ops
    - Projetos do PSA para o Fin and Ops
    - Linhas de contrato de projeto do PSA para o Fin and Ops
    - Marcos de linhas de contrato de projeto do PSA para o Fin and Ops

Antes da sincronização de contratos de projeto e de projetos, você deve sincronizar contas.

## <a name="entity-set"></a>Conjunto de entidades

| Project Service Automation       | Finanças                                                |
|----------------------------------|--------------------------------------------------------|
| Ordens                           | Entidade de integração para contrato do projeto                |
| Projetos                         | Entidade de integração para o projeto                         |
| Linhas da ordem                      | Entidade de integração para linhas de contrato do projeto           |
| Marcos de linha de contrato do projeto | Entidade de integração para marcos de linha de contrato do projeto |

## <a name="entity-flow"></a>Fluxo de entidades

Os contratos do projeto são gerenciados no Project Service Automation e são sincronizados com o Finance como contratos do projeto. Como parte do modelo de integração, você pode definir a fonte de integração no Finance para o contrato do projeto.

Projetos por tempo e material e de preço fixo são gerenciados no Project Service Automation e são sincronizados para o Finance como projetos. Como parte da integração do modelo, você pode definir a fonte de integração no Finance para o contrato do projeto.

As linhas de contrato do projeto são gerenciadas no Project Service Automation e são sincronizadas com o Finance como regras de cobrança de contrato do projeto. Se o método de cobrança for diferente do tipo de projeto padrão, a sincronização atualizará o tipo de projeto para o projeto da linha de contrato e grupo de projetos.

Os marcos de linha de contrato do projeto são gerenciados no Project Service Automation e são sincronizados para o Finance como marcos de regra de cobrança de contrato do projeto.

## <a name="project-service-automation-to-finance-integration-solution"></a>Solução de integração do Project Service Automation com o Finance

O campo **ID do contrato de projeto** está disponível na página **Contratos de projetos**. Este campo é uma chave natural e exclusiva para dar suporte à integração.

Quando uma novo contrato de projeto for criado, se um valor **ID do contrato do projeto** ainda não existir, ele será automaticamente gerado por meio de uma sequência numérica. O valor consiste em **ORD** seguido de uma sequência numérica crescente e de um sufixo de seis caracteres. Este é um exemplo: **ORD-01022-Z4M9Q0**.

O campo **Número do Projeto** está disponível na página **Projetos**. Este campo é uma chave natural e exclusiva para dar suporte à integração.

Quando um novo projeto for criado, se um valor **Número do Projeto** ainda não existir, ele será automaticamente gerado por meio de uma sequência numérica. O valor consiste em **PRJ** seguido de uma sequência numérica crescente e de um sufixo de seis caracteres. Este é um exemplo: **PRJ-01049-CCNID0**.

Quando a solução de integração do Project Service Automation com o Finance for aplicada, um script de atualização definirá o campo **ID de contrato do projeto** para contratos de projeto existentes e o campo **Número do Projeto** para projetos existentes no Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

- Antes da sincronização de contratos de projeto e de projetos, você deve sincronizar contas.
- No conjunto de conexões, adicione um mapeamento de campo-chave de integração de **msdyn\_organizationalunits** para **msdyn\_name \[Name\]**. Talvez seja necessário primeiro adicionar um projeto ao conjunto e conexões. Para obter mais informações, consulte [Integrar dados em Common Data Service para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- No conjunto de conexões, adicione um mapeamento de campo-chave de integração de **msdyn\_projects** para **msdynce\_projectnumber \[Project Number\]**. Talvez seja necessário primeiro adicionar um projeto ao conjunto e conexões. Para obter mais informações, consulte [Integrar dados em Common Data Service para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- **SourceDataID** para contratos de projetos e projetos pode ser atualizado para um valor diferente ou removido do mapeamento. O valor do modelo padrão é **Project Service Automation**.
- O mapeamento **PaymentTerms** deve ser atualizado de modo que reflita condições de pagamento válidas no Finance. Você também pode remover o mapeamento da tarefa do projeto. O mapa do valor padrão tem valores padrão para dados de demonstração. A tabela a seguir mostra os valores no Project Service Automation.

    | Alíquota | descrição   |
    |-------|---------------|
    | 1     | Líquido 30        |
    | 2     | 2% 10, Líquido 30 |
    | 3     | Líquido 45        |
    | 4     | Líquido 60        |

## <a name="power-query"></a>Power Query

Você deverá usar o Microsoft Power Query para Excel para filtrar dados se as seguintes condições forem atendidas:

- Você tem ordens de venda no Dynamics 365 Sales.
- Você tem várias unidades organizacionais no Project Service Automation. Essas unidades organizacionais serão mapeadas várias entidades legais no Finance.

Se você precisar usar o Power Query, consulte as seguintes diretrizes:

- O modelo de projetos e contratos (do PSA para o Fin and Ops) tem um filtro padrão que inclua apenas as ordens de venda do tipo **Item de trabalho (msdyn\_ordertype = 192350001)**. Esse filtro ajuda a garantir que os contratos do projeto não sejam criados para ordens de venda no Finance. Se você criar seu próprio modelo, adicione esse filtro.
- Crie um filtro do Power Query que inclua apenas as organizações de contrato que devam ser sincronizadas para a entidade legal do conjunto de conexões de integração. Por exemplo, os contratos de projeto que você tem com a unidade organizacional do contrato da Contoso nos EUA devem ser sincronizados com a entidade legal de USSI, mas os contratos de projeto que você tem com a unidade organizacional do contrato da Contoso Global devem ser sincronizados com a entidade legal de USMF. Caso você não adicione esse filtro ao mapeamento da tarefa, todos os contratos de projeto serão sincronizados para a entidade legal definida para o conjunto de conexões, independentemente da unidade organizacional do contrato.

## <a name="template-mapping-in-data-integration"></a>Mapeamento de modelo na Integração de dados

> [!NOTE] 
> Os campos **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** e **AddressZipCode** não são incluídos no mapeamento padrão para contratos do projeto. Você poderá adicionar os mapeamentos se precisar que esses dados sejam sincronizados para contratos do projeto.
>
> Os campos **Descrição**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber** e **ProjectType** não são incluídos no mapeamento padrão de projetos. Você poderá adicionar os mapeamentos se precisar que esses dados sejam sincronizados para projetos.

A ilustração a seguir mostra exemplos de mapeamentos da tarefa de modelo na Integração de dados. O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance.

[![Mapeamento de modelo](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Mapeamento de modelo](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Mapeamento de modelo](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Mapeamento de modelo](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

#### <a name="project-contract-line-milestone-mapping-in-the-projects-and-contracts-psa-3x-to-dynamics---v2-template"></a>Mapeamento de marco de linha de contrato de projeto nos Projetos e Contratos (PSA 3.x para o Dynamics) - modelo v2:

[![Mapeamento de modelo](./media/ProjectContractLineMilestoneMapping_v2.jpg)](./media/ProjectContractLineMilestoneMapping_v2.jpg)
