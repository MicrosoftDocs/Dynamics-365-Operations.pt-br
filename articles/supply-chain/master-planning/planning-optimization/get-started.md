---
title: Introdução ao planejamento mestre
description: Este artigo explica como começar a usar a funcionalidade de planejamento mestre no Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 958de3f9ae6ead6cb6914bd3b7a4560e768013ab
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740320"
---
# <a name="get-started-with-master-planning"></a>Introdução ao planejamento mestre

[!include [banner](../../includes/banner.md)]

O planejamento mestre no Supply Chain Management é fornecido por um serviço externo denominado Suplemento de Otimização de Planejamento para Microsoft para Dynamics 365 Supply Chain Management. Este tópico explica como obter e configurar este serviço.

## <a name="availability"></a>Disponibilidade

A otimização de planejamento está disponível atualmente nos seguintes ambientes do Azure: Estados Unidos, Canadá, Brasil, Europa, França, Reino Unido, Austrália, Pacífico Asiático, Japão e Índia. Se você tentar instalar o suplemento de outra região geográfica, o LCS mostrará uma mensagem informando que esse ambiente não é suportado. Para obter mais informações sobre regiões do Azure e regiões relacionadas, consulte [Regiões do Azure](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

Observe que a otimização de planejamento não oferece suporte a implantações locais do Dynamics 365 Supply Chain Management.

## <a name="licensing"></a>Licenciamento

Se você puder executar o planejamento mestre usando a licença atual, não terá de comprar uma licença adicional para começar a usar a Otimização de Planejamento.

## <a name="install-and-enable-planning-optimization"></a>Instalar e habilitar a otimização de planejamento

Para usar a otimização de planejamento, certifique-se de que o sistema atenda a todos os pré-requisitos, habilite sua chave de licença e instale o suplemento de otimização de planejamento para o Dynamics 365 Supply Chain Management.

### <a name="prerequisites"></a>Pré-requisitos

Antes de instalar o suplemento de otimização de planejamento, é preciso atender aos seguintes pré-requisitos:

- É necessário executar o Supply Chain Management em um ambiente de alta disponibilidade habilitado para LCS, camada 2 ou superior (não um ambiente OneBox), com o Dynamics 365 Supply Chain Management versão 10.0.7 ou posterior. Se você tentar instalar o suplemento em um ambiente do OneBox, a instalação não será concluída e será necessário cancelar a instalação.

- O sistema deve estar configurado para integração do Power Platform. Para obter mais informações, consulte [integração do Microsoft Power Platform com os aplicativos de finanças e operações](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

### <a name="enable-the-planning-optimization-license"></a>Habilitar a licença da otimização de planejamento

Para usar a otimização de planejamento, é necessário habilitar a chave de configuração. Para fazer isso:

1. Coloque seu sistema em modo de manutenção, conforme descrito em [Modo de manutenção](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Acesse **Administração de sistema \> Configurar \> Configuração de licença**.
1. Na guia **Chaves de configuração**, marque a caixa de seleção **Otimização de planejamento**.
1. Desative o modo de manutenção, conforme descrito em [Modo de manutenção](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="install-the-planning-optimization-add-in"></a>Instalar o suplemento de otimização de planejamento

É necessário instalar o suplemento do seu projeto do LCS e ativar a funcionalidade Otimização de Planejamento da interface do usuário do Supply Chain Management.

Para instalar o suplemento de otimização de planejamento:

1. Entre no LCS e abra o ambiente desejado.
1. Acesse **Detalhes completos**.
1. Role para baixo até a Guia Rápida **Suplementos de ambiente**.
1. Selecione **Instalar um novo suplemento**.
1. Selecione **Otimização de Planejamento**.
1. Acompanhe o guia de instalação e concorde com os termos e condições.
1. Selecione **Instalar**.
1. Na guia rápida **Suplementos de ambiente**, você verá que a otimização de planejamento está instalando.
1. Após alguns minutos, **Instalando** deve mudar para **Instalado** (talvez você precise atualizar a página). Quando instalado, você estará pronto para ativar a Otimização do Planejamento no Dynamics 365 Supply Chain Management.

A finalidade principal da instalação do suplemento de otimização de planejamento é conectar o serviço e o ambiente. Portanto, você deve instalar o suplemento separadamente em cada ambiente no qual usará a otimização do planejamento, independentemente do código movido entre os ambientes.

## <a name="integrate-planning-optimization-with-your-system"></a>Integrar a otimização de planejamento ao seu sistema

Para configurar se o Suplemento Otimização do Planejamento deve ser usado para o planejamento mestre, Acesse **Planejamento mestre** \> **Configuração** \> **Parâmetros de Otimização do Planejamento**.

### <a name="connection-status"></a>Status da conexão

O status de conexão indica o status atual da conexão entre o Supply Chain Management e o serviço Otimização de Planejamento. A tabela a seguir mostra os valores possíveis.

| Status da conexão | Descrição | A Otimização de Planejamento pode ser usada? |
|---|---|---|
| Conectado | Uma conexão foi estabelecida entre o serviço Otimização de Planejamento e o Supply Chain Management. | Sim |
| Habilitando conexão | Uma solicitação para ativar a conexão ao serviço Otimização de Planejamento está em andamento. | Não |
| Desconectado | Não há nenhuma conexão com o serviço Otimização de Planejamento. A conexão pode ser ativada do LCS, como descrito anteriormente neste artigo. | Número |
| Desabilitando a conexão | Uma solicitação para desativar a conexão ao serviço Otimização de Planejamento está em andamento. | Não |
| Obtendo status | O sistema está aguardando informações de status do serviço Otimização de Planejamento. | Não |

### <a name="the-use-planning-optimization-option"></a>A opção Usar Otimização de Planejamento

A configuração da opção **Usar Otimização de Planejamento** determina qual mecanismo de planejamento é usado para o planejamento mestre:

- **Sim** – a Otimização de Planejamento é usada para o planejamento mestre.
- **Não** – o mecanismo de planejamento mestre preterido é usado para planejamento mestre.

Esse cenário se aplica a todas as entidades legais (empresas). Não é possível utilizar a Otimização de Planejamento em algumas entidades legais e o mecanismo de planejamento mestre preterido em outras entidades legais.

> [!NOTE]
> Se os trabalhos em lotes de planejamento existentes criados para o mecanismo de planejamento mestre preterido forem disparados quando a opção **Usar Otimização de Planejamento** estiver definida como **Sim**, esses trabalhos falharão.

### <a name="integration-with-the-setup"></a>Integração com a configuração

Se Otimização de Planejamento estiver ativado, o planejamento mestre será feito usando o Suplemento Otimização de Planejamento. Neste caso, os resultados do planejamento mestre e os recursos são afetados.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
