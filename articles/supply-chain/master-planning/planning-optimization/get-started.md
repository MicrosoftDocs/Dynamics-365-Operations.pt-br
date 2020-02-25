---
title: Introdução à Otimização de Planejamento
description: Este tópico explica como começar a usar a funcionalidade Otimização de Planejamento.
author: ChristianRytt
manager: AnnBe
ms.date: 01/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 3e0371c6addc0412dc2fc105891b012941e92a06
ms.sourcegitcommit: e5a3c85a322a9216b8f176536d664fef40ae0bec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2020
ms.locfileid: "2971455"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a>Introdução à Otimização de Planejamento

No momento, a funcionalidade Otimização de Planejamento não dá suporte a todos os recursos disponíveis no mecanismo de planejamento do Microsoft Dynamics 365 Supply Chain Management. Portanto, é importante que você avalie se o conjunto de recursos disponível no momento na Otimização de Planejamento atenderá aos seus requisitos. Por padrão, a funcionalidade Otimização de Planejamento não está ativada no Dynamics Lifecycle Services (LCS) por padrão. Portanto, você tem uma oportunidade de fazer sua avaliação antes de ativá-la.

Eventualmente, a Otimização de Planejamento substituirá o mecanismo de planejamento interno do Supply Chain Management.

Antes de ativar a Otimização de Planejamento, recomendamos enfaticamente que você avalie os resultados da análise de ajuste da Otimização de Planejamento. Para obter mais informações, consulte [Introdução à análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Licenciamento

Se você puder executar o planejamento mestre usando a licença atual, não terá de comprar uma licença adicional para começar a usar a Otimização de Planejamento.

### <a name="install-the-add-in"></a>Instalar o suplemento

Para usar a Otimização de Planejamento, instale o Suplemento Otimização de Planejamento para o Dynamics 365 Supply Chain Management. Você pode acessar o suplemento do seu projeto do LCS e ativar a funcionalidade Otimização de Planejamento da interface do usuário (IU) do Supply Chain Management.

1. Entre no LCS e abra o ambiente desejado.
1. Vá para **Detalhes completos**.
1. Role para baixo até a FastTab **Suplementos de ambiente**.
1. Selecione **Instalar um novo suplemento**.
1. Selecione **Otimização de Planejamento**.
1. Acompanhe o guia de instalação e concorde com os termos e condições.
1. Selecione **Instalar**.
1. Na FastTab **Suplementos de ambiente**, você deverá ver que a Otimização do Planejamento está instalando.
1. Após alguns minutos, **Instalando** deve mudar para **Instalado** (talvez você precise atualizar a página). Quando instalado, você estará pronto para ativar a Otimização do Planejamento no Dynamics 365 Supply Chain Management.

### <a name="planning-optimization-integration"></a>Integração da Otimização de Planejamento

Para configurar se o Suplemento Otimização do Planejamento deve ser usado para o planejamento mestre, vá para **Planejamento mestre** \> **Configuração** \> **Parâmetros de Otimização do Planejamento**.

#### <a name="connection-status"></a>Status da conexão

O status de conexão indica o status atual da conexão entre o Supply Chain Management e o serviço Otimização de Planejamento. A tabela a seguir mostra os valores possíveis.

| Status da conexão | Descrição | A Otimização de Planejamento pode ser usada? |
|---|---|---|
| Conectado | Uma conexão foi estabelecida entre o serviço Otimização de Planejamento e o Supply Chain Management. | Sim |
| Habilitando conexão | Uma solicitação para ativar a conexão ao serviço Otimização de Planejamento está em andamento. | Não |
| Desconectado | Não há nenhuma conexão com o serviço Otimização de Planejamento. A conexão pode ser ativada do LCS, como descrito anteriormente neste tópico. | Não |
| Desabilitando a conexão | Uma solicitação para desativar a conexão ao serviço Otimização de Planejamento está em andamento. | Não |
| Obtendo status | O sistema está aguardando informações de status do serviço Otimização de Planejamento. | Não |

#### <a name="the-use-planning-optimization-option"></a>A opção Usar Otimização de Planejamento

A configuração da opção **Usar Otimização de Planejamento** determina qual mecanismo de planejamento é usado para o planejamento mestre:

- **Sim** – a Otimização de Planejamento é usada para o planejamento mestre.
- **Não** – o mecanismo de planejamento interno do Supply Chain Management é usado para o planejamento mestre.

> [!NOTE]
> Se os trabalhos em lotes de planejamento existentes criados para o mecanismo de planejamento interno do Supply Chain Management forem disparados quando a opção **Usar Otimização de Planejamento** estiver definida como **Sim**, esses trabalhos falharão.

### <a name="integration-with-the-setup"></a>Integração com a configuração

Se a versão prévia da Otimização de Planejamento estiver ativada, o planejamento mestre será feito usando o Suplemento Otimização de Planejamento. Neste caso, os resultados do planejamento mestre e os recursos são afetados.

## <a name="related-resources"></a>Recursos relacionados

[Termos e condições para a versão prévia](https://go.microsoft.com/fwlink/?linkid=2015274)

[Visão geral da Otimização de Planejamento](planning-optimization-overview.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)
