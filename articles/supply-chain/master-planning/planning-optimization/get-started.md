---
title: Introdução à Otimização de Planejamento
description: Este tópico explica como começar a usar a funcionalidade Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 54ad180b7f4691ead3563b077eadadc3b9b20588
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422629"
---
# <a name="get-started-with-planning-optimization"></a>Introdução à Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Como [anunciado anteriormente](https://docs.microsoft.com/dynamics365/supply-chain/get-started/removed-deprecated-features-scm-updates#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), a Otimização de Planejamento está agendada para substituir o mecanismo de planejamento mestre existente.

Se estiver usando o mecanismo de planejamento mestre interno no momento, você deverá começar a planejar a migração para a Otimização de Planejamento agora. É importante iniciar o processo de migração imediatamente porque suas operações poderão ser afetadas quando a substituição for imposta. Para evitar problemas de última hora quando a substituição for imposta, é altamente recomendável que você conclua a migração antes de 1º de dezembro de 2020. 

No momento, a funcionalidade Otimização de Planejamento não dá suporte a todos os recursos disponíveis no mecanismo de planejamento interno do Supply Chain Management. Portanto, é importante que você avalie se o conjunto de recursos disponível no momento na Otimização de Planejamento atenderá aos seus requisitos. No momento, a funcionalidade Otimização de Planejamento não está ativada por padrão no Dynamics Lifecycle Services (LCS), de modo que você tem a oportunidade de fazer a avaliação antes do recurso ser ativado.

> [!NOTE]
> Você precisará solicitar uma exceção da migração para a Otimização de Planejamento se o processo de planejamento mestre não incluir a produção (ordens de produção planejadas geradas pelo planejamento mestre) e se precisar do mecanismo de planejamento mestre interno além da versão 10.0.15. A partir da versão 10.0.16, um erro será mostrado nos ambientes durante a execução do planejamento mestre interno sem a geração de ordens de produção planejadas. A Otimização de Planejamento deverá ser usada para todas as novas implantações que não gerem ordens de produção planejadas durante o planejamento mestre. Os proprietários de ambientes existentes que executam o mecanismo de planejamento mestre interno sem a geração de ordens de produção planejadas receberão um email com detalhes sobre o processo de exceção. Recomendamos que você trabalhe com um parceiro para avaliar e planejar a migração para a Otimização de Planejamento.

Antes de ativar a Otimização de Planejamento, recomendamos enfaticamente que você avalie os resultados da análise de ajuste da Otimização de Planejamento. Para obter mais informações, consulte [Introdução à análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).

### <a name="availability"></a>Disponibilidade
A otimização de planejamento está disponível atualmente nos seguintes ambientes do Azure: Estados Unidos, Canadá, Europa, Reino Unido e Austrália. Se você tentar instalar o suplemento de outra região geográfica, o LCS mostrará uma mensagem informando que esse ambiente não é suportado.

Observe que a otimização de planejamento não oferece suporte a implantações locais do Dynamics 365 Supply Chain Management.

### <a name="licensing"></a>Licenciamento

Se você puder executar o planejamento mestre usando a licença atual, não terá de comprar uma licença adicional para começar a usar a Otimização de Planejamento.

### <a name="install-the-add-in"></a>Instalar o suplemento

Para usar a Otimização de Planejamento, instale o Suplemento Otimização de Planejamento para o Dynamics 365 Supply Chain Management. Você pode acessar o suplemento do seu projeto do LCS e ativar a funcionalidade Otimização de Planejamento da interface do usuário (IU) do Supply Chain Management.

> [!NOTE]
> A necessidade de Otimização do Planejamento é um ambiente de alta disponibilidade habilitado para LCS, camada 2 ou superior (não um ambiente OneBox), com o Dynamics 365 Supply Chain Management versão 10.0.7 ou posterior. Se você tentar instalar o suplemento em um ambiente do OneBox, a instalação não será concluída e será necessário cancelar a instalação.

1. Entre no LCS e abra o ambiente desejado.
1. Vá para **Detalhes completos**.
1. Role para baixo até a Guia Rápida **Suplementos de ambiente**.
1. Selecione **Instalar um novo suplemento**.
1. Selecione **Otimização de Planejamento**.
1. Acompanhe o guia de instalação e concorde com os termos e condições.
1. Selecione **Instalar**.
1. Na Guia Rápida **Suplementos de ambiente**, você deverá ver que a Otimização do Planejamento está instalando.
1. Após alguns minutos, **Instalando** deve mudar para **Instalado** (talvez você precise atualizar a página). Quando instalado, você estará pronto para ativar a Otimização do Planejamento no Dynamics 365 Supply Chain Management.

A finalidade principal da instalação do suplemento de otimização de planejamento é conectar o serviço e o ambiente. Portanto, você deve instalar o suplemento separadamente em cada ambiente no qual usará a otimização do planejamento, independentemente do código movido entre os ambientes.

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

Se Otimização de Planejamento estiver ativado, o planejamento mestre será feito usando o Suplemento Otimização de Planejamento. Neste caso, os resultados do planejamento mestre e os recursos são afetados.

## <a name="additional-resources"></a>Recursos adicionais

[Termos e condições para a versão prévia](https://go.microsoft.com/fwlink/?linkid=2015274)

[Visão geral de Otimização de Planejamento](planning-optimization-overview.md)

[Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)

[Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)

[Aplicar filtros a um plano](plan-filters.md)

[Cancelar um trabalho de planejamento](cancel-planning-job.md)
