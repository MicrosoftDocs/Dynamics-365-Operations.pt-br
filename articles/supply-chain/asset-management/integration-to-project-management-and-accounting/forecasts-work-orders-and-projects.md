---
title: Previsões, ordens de serviço e projetos
description: Este tópico explica previsões e integração de ordens de serviço com o módulo Gerenciamento e contabilidade do projeto no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjCostInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f062b5463b54e9bcf32ed6f17263811c4bb24138
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021007"
---
# <a name="forecasts-work-orders-and-projects"></a>Previsões, ordens de serviço e projetos

[!include [banner](../../includes/banner.md)]

 

No Gerenciamento de Ativos, a integração com o módulo **Gerenciamento e contabilidade do projeto** ajuda a otimizar o controle de custos, permitindo que os usuários controlem os custos nas previsões de tipo de trabalho de manutenção e trabalhos da ordem de serviço.

O rastreamento de previsões de tipo de trabalho de manutenção requer duas configurações:

1. Selecione um projeto em **Gerenciamento de ativos** > **Configuração** > **Parâmetros de gerenciamento de ativos** e, na guia **Ativos** > na Guia Rápida **Projeto**, no campo **Projeto de previsão de manutenção**, selecione um projeto.

2. Ao criar uma linha padrão de tipo de trabalho de manutenção, um número de atividade é criado automaticamente para a linha na página **Padrões do tipo de trabalho de manutenção** (**Gerenciamento de ativos** > **Configuração** > **Trabalhos** > **Padrões do tipo de trabalho de manutenção**).

As previsões de tipo de trabalho de manutenção têm duas finalidades: 

- Você pode controlar os custos em previsões de tipo de trabalho de manutenção no módulo **Gerenciamento e contabilidade do projeto**. 
- As previsões são transferidas automaticamente para um projeto de trabalho de ordem de serviço quando você seleciona um tipo de trabalho de manutenção em um trabalho da ordem de serviço.

Para controlar custos em trabalhos de ordem de serviço, você deve primeiro configurar projetos de ordem de serviço. Para obter mais informações, consulte [Configuração do projeto da ordem de serviço](../setup-for-work-orders/work-order-project-setup.md).

## <a name="work-order-job-projects"></a>Projetos de trabalho de ordem de serviço

Quando você cria um trabalho de ordem de serviço em uma ordem de serviço, o projeto da ordem de serviço é determinado pela configuração do projeto principal das ordens de serviço na página **Configuração do projeto da ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto**).

Os projetos de trabalho da ordem de serviço são criados usando uma combinação das seguintes informações da ordem de serviço:

- O tipo de ordem de serviço selecionado na ordem de serviço 
- O local funcional relacionado ao ativo no trabalho da ordem de serviço
- O tipo de ativo relacionado ao ativo no trabalho da ordem de serviço  
- As horas previstas de início e término definidas na ordem de serviço  

Algumas dessas informações não pode ser encontradas em uma ordem de serviço. Portanto, a pesquisa de um projeto principal da ordem de serviço é feita por meio da combinação de dados disponíveis e a seleção da ID do projeto que corresponde aos dados da ordem de serviço.

Por exemplo, na ilustração a seguir, por causa da maneira como o tipo de ativo **Motor de Caminhão** está configurado, cada trabalho da ordem de serviço criado com o tipo de ativo **Motor de Caminhão** será um subprojeto do projeto com a ID 000186.

![Figura 1](media/01-integration-to-pma.png)

A finalidade da ID do projeto no trabalho da ordem de serviço e o número de atividade relacionado é rastrear os custos relacionados ao trabalho da ordem de serviço e o ativo selecionado nela, no módulo **Gerenciamento e contabilidade de projeto**. (Para exibir a ID de projeto e o número da atividade, selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** e selecione a ordem de serviço. Na Guia Rápida **Detalhes da linha**, o campo **ID do projeto** mostra a ID do projeto e o campo **Número da atividade** mostra o número da atividade.) Para obter mais informações sobre controle de custos no Gerenciamento de Ativos, consulte [Controle de custo e data](../controlling-and-reporting/cost-and-date-control.md).

A ilustração a seguir mostra uma visão geral gráfica dos projetos de ordem de serviço e das atividades de projeto relacionadas.

![Figura 2](media/02-integration-to-pma.png)

Quando um trabalho de ordem de serviço é criado em uma ordem de serviço, um projeto de ordem de serviço é criado automaticamente para o trabalho. As dimensões financeiras do ativo relacionadas ao trabalho da ordem de serviço são transferidas automaticamente para o projeto da ordem de serviço.

A atividade de projeto criada para um trabalho da ordem de serviço tem informações relacionadas anexadas a ela. Essas informações tratam do tipo de trabalho de manutenção, da variação do tipo de trabalho de manutenção e do comércio. Elas serão úteis se, por exemplo, você criar uma ordem de compra usando uma ordem de serviço (consulte [Compras](../work-orders/procurement.md)) ou se você usar o módulo **Gerenciamento e contabilidade do projeto** para registro de horário.

Se o ativo foi instalado em um local funcional mas, depois, foi instalado em outro local funcional, as dimensões financeiras relacionadas ao novo local funcional são atualizadas automaticamente no ativo. Em seguida, quando você cria um trabalho da ordem de serviço para o ativo, o projeto da ordem de serviço do trabalho da ordem de serviço obtém as dimensões financeiras que agora estão relacionadas ao ativo automaticamente. Portanto, quando você usa locais funcionais, os custos sempre podem ser controlados nos locais funcionais nos quais um ativo foi instalado a qualquer momento. A atualização automática das dimensões financeiras ajuda a garantir total rastreabilidade dos custos para controle e geração de relatórios do projeto.

## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Projetos de ordem de serviço, estados de ciclo de vida da ordem de serviço, fases de projeto e tipos de projeto

Para ajudar a garantir o uso correto dos estados de ciclo de vida da ordem de serviço e fases de projeto relacionadas em ordens de serviço, considere as dependências em relação ao módulo **Gerenciamento e contabilidade do projeto**:

- No módulo **Gerenciamento e contabilidade do projeto**, as fases de projeto são configuradas nos tipos de projeto na página **Parâmetros de gerenciamento e contabilidade de projetos**.  
- Na página **Parâmetros de gerenciamento e contabilidade de projetos**, use as caixas de seleção para escolher as fases de projeto relevantes para todos os tipos de projeto que você usará. Nas ilustrações a seguir, cinco fases (**Criado**, **Previsto**, **Agendado**, **Em processamento** e **Concluído**) foram selecionadas para os tipos de projeto **Tempo e material** e **Interno**. Essas cinco fases são relevantes para trabalhos de manutenção interna e trabalhos de manutenção de serviços.
- No módulo **Gerenciamento de Ativos**, os tipos de projeto são definidos pelos grupos de projetos que você configurou na página **Configuração do projeto da ordem de serviço** > guia **Grupo de projetos** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto**).  
- Os grupos de projetos configurados na página **Configuração do projeto da ordem de serviço** são usados ao criar ordens de serviço. Quando uma ordem de serviço é criada, um projeto de ordem de serviço é criado automaticamente para a ordem de serviço.  
- Cada estado de ciclo de vida da ordem de serviço deve ter uma fase de projeto relacionada.  
- A fase do projeto relacionada a um estado de ciclo de vida da ordem de serviço deve ser definida como uma fase ativa para o grupo de projetos definido no projeto da ordem de serviço. O projeto da ordem de serviço é criado automaticamente em uma ordem de serviço.
- Quando você cria uma nova ordem de serviço, a alocação automática de um projeto da ordem de serviço é baseada na configuração da página **Configuração do projeto da ordem de serviço**.  

As ilustrações a seguir mostram as associações entre grupos de projetos da ordem de serviço, tipos de projetos relacionados, fases de projeto e estados de ciclo de vida da ordem de serviço.

![Figura 3](media/03-integration-to-pma.png)

![Figura 4](media/04-integration-to-pma.png)

![Figura 5](media/05-integration-to-pma.png)

Para obter informações sobre como configurar projetos da ordem de serviço, consulte [Configuração do projeto da ordem de serviço](../setup-for-work-orders/work-order-project-setup.md). Para obter informações sobre como criar estados de ciclo de vida da ordem de serviço, consulte [Estados de ciclo de vida da ordem de serviço](../setup-for-work-orders/work-order-lifecycle-states.md).

A ilustração a seguir mostra uma visão geral gráfica de vários projetos criados no módulo **Gerenciamento de ativos** para permitir a integração com o módulo **Gerenciamento e contabilidade de projeto**. Ela também mostra os processos de trabalho aos quais os projetos estão relacionados.

![Figura 6](media/06-integration-to-pma.png)

