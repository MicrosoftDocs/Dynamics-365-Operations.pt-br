---
title: Previsões, ordens de serviço e projetos
description: Este tópico explica previsões e integração de ordens de serviço com o módulo Gerenciamento e contabilidade do projeto no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886807"
---
# <a name="forecasts-work-orders-and-projects"></a>Previsões, ordens de serviço e projetos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

No Gerenciamento de Ativos, a integração ao módulo **Gerenciamento e contabilidade do projeto** é feita para otimizar o controle de custos, permitindo que os usuários controlem os custos nas previsões de tipo de trabalho de manutenção e trabalhos de ordem de serviço.

Para controlar previsões de tipo de trabalho de manutenção, duas configurações devem ser feitas:

1. Selecione um projeto no campo **Gerenciamento de ativos** > **Configuração** > **Parâmetros de gerenciamento de ativos** > link **Ativos** > Guia Rápida **Projeto** > **Projeto de previsão de manutenção**.

2. Em **Padrões do tipo de trabalho de manutenção**, quando você cria uma linha padrão do tipo de trabalho de manutenção, um número de atividade é criado automaticamente para a linha (**Gerenciamento de ativos** > **Configuração** > **Trabalhos** > **Padrões do tipo de trabalho de manutenção**).

As previsões de tipo de trabalho de manutenção têm duas finalidades: você pode controlar custos nas previsões de tipo de trabalho de manutenção no módulo **Gerenciamento e contabilidade do projeto**. Além disso, as previsões são transferidas automaticamente para um projeto de trabalho de ordem de serviço quando você seleciona um tipo de trabalho de manutenção em um trabalho de ordem de serviço.

Para controlar custos em trabalhos de ordem de serviço, você deve primeiro configurar projetos de ordem de serviço. Consulte a seção [Configuração do projeto da ordem de serviço](../setup-for-work-orders/work-order-project-setup.md) para obter uma descrição do procedimento.

## <a name="work-order-job-projects"></a>Projetos de trabalho de ordem de serviço

Quando você cria um trabalho de ordem de serviço em uma ordem de serviço, o projeto da ordem de serviço é determinado pela configuração do projeto principal das ordens de serviço em **Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto**.

Os projetos de trabalho da ordem de serviço são criados usando uma combinação das seguintes informações da ordem de serviço:

- O tipo de ordem de serviço selecionado na ordem de serviço 
- O local funcional relacionado ao ativo no trabalho da ordem de serviço
- O tipo de ativo relacionado ao ativo no trabalho da ordem de serviço  
- A hora prevista de início e término definida na ordem de serviço  

É possível que nem todas as informações mencionadas acima sejam encontradas em uma ordem de serviço. Portanto, a pesquisa de um projeto principal da ordem de serviço é feita por meio da combinação de dados disponível e seleção da ID do projeto que corresponde aos dados da ordem de serviço.

Exemplo: na figura abaixo, a configuração do tipo de ativo "Motor de Caminhão" significa que todo trabalho de ordem de serviço criado com esse tipo de ativo será um subprojeto da ID do projeto "000186".

![Figura 1](media/01-integration-to-pma.png)

A finalidade da ID do projeto no trabalho da ordem de serviço e o número da atividade relacionada (**Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** > selecione a ordem de serviço na lista > Guia Rápida **Detalhes da linha** > campo **ID do projeto** e campo **Número da atividade**) é controlar os custos relacionados ao trabalho da ordem de serviço e o ativo selecionado no trabalho da ordem de serviço, no módulo **Gerenciamento e contabilidade do projeto**. 

Na figura abaixo, você verá uma visão geral gráfica dos projetos de ordem de serviço e atividades de projeto relacionadas.

![Figura 2](media/02-integration-to-pma.png)

Quando um trabalho de ordem de serviço é criado em uma ordem de serviço, um projeto de ordem de serviço é criado automaticamente para o trabalho. As dimensões financeiras do ativo relacionadas ao trabalho da ordem de serviço são transferidas automaticamente para o projeto da ordem de serviço. A atividade de projeto criada para um trabalho de ordem de serviço tem informações relacionadas a ele anexadas em relação ao tipo de trabalho de manutenção, variante do tipo de trabalho de manutenção e comércio. Esses dados são úteis se, por exemplo, você criar uma ordem de compra usando uma ordem de serviço (consulte [Compras](../work-orders/procurement.md)) ou se você usar o módulo **Gerenciamento e contabilidade do projeto** para registro de horário.  

Se o ativo foi instalado em um local funcional e, depois, em outro local funcional, as dimensões financeiras relacionadas ao novo local funcional são atualizadas automaticamente no ativo. Posteriormente, ao criar um trabalho de ordem de serviço para o ativo, o projeto da ordem de serviço obtém automaticamente as dimensões financeiras que agora estão relacionadas ao ativo. Isso significa que, quando você usa locais funcionais, os custos sempre podem ser controlados nos locais funcionais nos quais um ativo foi instalado a qualquer momento. A atualização automática das dimensões financeiras garante total rastreabilidade dos custos para controle e geração de relatórios do projeto.  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Projetos de ordem de serviço, estados de ciclo de vida da ordem de serviço, fases de projeto e tipos de projeto

Para garantir o uso correto dos estados de ciclo de vida da ordem de serviço e fases de projeto relacionadas em ordens de serviço, considere as dependências em relação ao módulo **Gerenciamento e contabilidade do projeto**:

- No módulo **Gerenciamento e contabilidade do projeto**, as fases de projeto são configuradas nos tipos de projeto em **Parâmetros de gerenciamento e contabilidade de projetos**.  
- Em **Parâmetros de gerenciamento e contabilidade de projetos**, lembre-se de marcar as caixas de seleção relevantes das fases de projeto para todos os tipos de projeto que você usará. Na figura abaixo, cinco fases **Criado** - **Estimado** - **Agendado** - **Em andamento** - **Concluído** foram selecionadas para os tipos de projeto "Tempo e material" e "Interno". Essas cinco fases são relevantes para trabalhos de manutenção interna e manutenção de serviços.  
- Em **Gerenciamento de Ativos**, tipos de projeto são definidos pelos grupos de projetos configurados no formulário **Configuração do projeto da ordem de serviço** > link **Grupo de projetos**.  
- A configuração dos grupos de projetos em **Configuração do projeto da ordem de serviço** é usada na criação de ordens de serviço. Quando uma ordem de serviço é criada, um projeto de ordem de serviço é criado automaticamente para a ordem de serviço.  
- Cada uma das fases do ciclo de vida da ordem de serviço deve ter uma fase de projeto relacionada.  
- A fase do projeto relacionada a um estado de ciclo de vida da ordem de serviço deve ser definida como uma fase ativa para o grupo de projetos definido no projeto da ordem de serviço. O projeto da ordem de serviço é criado automaticamente em uma ordem de serviço.  
- Quando você cria uma ordem de serviço, a alocação automática de um projeto de ordem de serviço é baseada na configuração em **Configuração do projeto da ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto**).  

Associações entre grupos de projetos de ordem de serviço, tipos de projetos relacionados, fases de projeto e estados de ciclo de vida da ordem de serviço são mostradas nas figuras abaixo.  

![Figura 3](media/03-integration-to-pma.png)

![Figura 4](media/04-integration-to-pma.png)

![Figura 5](media/05-integration-to-pma.png)

Consulte [Configuração do projeto da ordem de serviço](../setup-for-work-orders/work-order-project-setup.md) para saber como configurar projetos de ordem de serviço e [Estados do ciclo de vida da ordem de serviço](../setup-for-work-orders/work-order-lifecycle-states.md) para saber como criar estados de ciclo de vida da ordem de serviço.

A figura abaixo mostra uma visão geral gráfica dos vários projetos criados no módulo **Gerenciamento de ativos** para permitir a integração com o **Gerenciamento e contabilidade do projeto**, bem como os processos de trabalho aos quais os projetos são relacionados.

![Figura 6](media/06-integration-to-pma.png)

