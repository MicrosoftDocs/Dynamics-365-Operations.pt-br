---
title: Configurar Insights Operacionais
description: Este artigo descreve como configurar e usar o recurso Insights Operacionais no Microsoft Dynamics 365 Commerce.
author: ashishMSFT
ms.date: 12/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: ca0d31e403275d6131fa6d53f0a7b46a7ddb651d
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832113"
---
# <a name="set-up-operational-insights"></a>Configurar Insights Operacionais

[!include [banner](../includes/banner.md)]

Este artigo descreve como configurar e usar o recurso Insights Operacionais no Microsoft Dynamics 365 Commerce.

O Insights Operacionais é um recurso do Dynamics 365 Commerce projetado para melhorar a visibilidade dos clientes sobre a integridade e a funcionalidade comercial do serviço, enviando telemetria diretamente para uma conta do Application Insights do cliente.

Ao habilitar o recurso Insights Operacionais para seus ambientes no Commerce headquarters, você pode coletar uma lista de eventos da Commerce Scale Unit (CSU) e dos seus dispositivos de ponto de venda (PDV). Esses eventos podem ajudá-lo a compreender melhor a forma como os sistemas estão sendo executados e permitem monitorar métricas técnicas e comerciais importantes.

Mesmo que não queira coletar essa telemetria o tempo todo, você poderá se beneficiar ao habilitar ou desabilitar rapidamente a coleta em ambientes específicos. Dessa forma, a telemetria pode ajudá-lo a solucionar problemas ou realizar a depuração durante o desenvolvimento ou em produção.

## <a name="access-logs-in-application-insights"></a>Acessar logs no Application Insights

Para acessar os logs de eventos de diagnóstico para os componentes CSU e PDV do Commerce pelo Application Insights, conclua os procedimentos nesta seção.

### <a name="minimum-version-requirements-for-csu"></a>Requisitos de versão mínimos para CSU

O CSU tem os seguintes requisitos mínimos de versão:

- 10.0.23 (Retail Server versão 9.33.22062.15 e posterior)
- 10.0.24 (Retail Server versão 9.34.22062.14 e posterior)
- 10.0.25 (Retail Server versão 9.35.22062.13 e posterior)
- 10.0.26 e posterior (todas as versões)

### <a name="enable-diagnostic-events-in-application-insights"></a>Habilitar eventos de diagnóstico no Application Insights

> [!IMPORTANT]
> Se você tiver usado anteriormente uma versão preliminar do Insights Operacionais, deverá usar o procedimento a seguir para habilitar esse recurso. Dessa forma, você garante que o acesso confiável e seguro a eventos continue.

Para habilitar eventos de diagnóstico de componente do Commerce, você precisa ter uma conta do Application Insights. Você pode usar uma conta existente ou [criar uma nova conta](/azure/azure-monitor/app/create-workspace-resource#create-workspace-based-resource). Por motivos de privacidade de dados, recomendamos que você use contas separadas do Application Insights para ambientes de produção, áreas restritas e desenvolvimento. Depois de criar uma conta, você precisa habilitar o recurso **Insights Operacionais** no headquarters.

Para habilitar os eventos de diagnóstico no Application Insights, siga estas etapas.

1. No headquarters, abra o espaço de trabalho **Gerenciamento de recursos** e habilite o recurso **Insights Operacionais**.
1. Acesse **Administração do sistema \> Configuração \> Insights Operacionais**.
1. Na guia **Configuração**, defina a opção **Eventos de canal do Commerce** como **Sim**.
1. Na guia **Ambientes**, insira o **ID do ambiente do LCS** e os valores do **Modo de ambiente** de cada um em que você planeja usar o Application Insights. Você pode encontrar o ID do ambiente na página **Detalhes do ambiente** para ele no Microsoft Dynamics Lifecycle Services. Essa etapa é necessária para ajudar a evitar que eventos de diagnóstico sejam inadvertidamente enviados ao ambiente errado quando as operações de cópia de banco de dados forem executadas.
1. Na guia **Registro do Application Insights**, especifique o valor da **Chave de instrumentação** do Application Insights e o valor correspondente **Modo de ambiente**, onde você planeja usar cada conta do Application Insights.
1. Depois de concluir a configuração anterior, execute o trabalho **CDX 1110**. Você pode aguardar que o trabalho seja executado de acordo com a agenda ou pode executá-lo manualmente.
1. No Lifecycle Services, vá para **Detalhes do ambiente \> Commerce \> Gerenciar**, selecione uma instância do CSU e selecione **Reiniciar**. Repita esta etapa para cada CSU.
1. Repita as etapas anteriores para cada ambiente em que você planeja usar o Application Insights.

> [!NOTE]
> - Os eventos de telemetria no recurso Insights Operacionais estão sujeitos a alterações. Recomendamos que você use eventos do Insights Operacionais para realizar uma análise preliminar e solução de problemas por conta própria, não para definir painéis ou alertas. Se você usar eventos para fins que não sejam a solução de problemas por autoatendimento, recomendamos que valide e atualize suas consultas após cada lançamento de CSU/PDV.
> - A partir do Commerce versão 10.0.29, os procedimentos desta seção também habilitam o fluxo de eventos do Insights Operacionais de PDV para sua conta do Application Insights. Para obter mais informações, consulte o [Insights Operacionais para PDV – eventos e consultas](https://download.microsoft.com/download/9/2/b/92be35b0-0e24-4a4d-940d-6f4db29791c0/Operational-Insights-Commerce-POS-events-queries.pdf).

#### <a name="use-the-dllhostexeconfig-file-to-control-pos-operational-insights-events"></a>Use o arquivo DLLHost.exe.config para controlar eventos do Insights Operacionais de PDV

Para usar o arquivo DLLHost.exe.config para controlar eventos do Insights Operacionais de PDV, siga estas etapas.

1. Em um editor de texto, abra o arquivo **DLLhost.exe.config** em **C:\\Arquivos de Programas (x86)\\Microsoft Dynamics 365\\70\\Retail Modern POS\\ClientBroker**.
1. Na seção **diagnosticsSection**, remova o elemento XML do coletor com o nome de classe **Microsoft.Dynamics.Retail.Diagnostics.OperationalInsights.OperationalInsightsLogger**.
1. Salve o arquivo.

### <a name="disable-diagnostic-events-in-application-insights"></a>Desabilitar eventos de diagnóstico no Application Insights

> [!IMPORTANT]
> Se você quer desabilitar eventos de diagnóstico e não enviá-los ao Application Insights, conclua o procedimento a seguir. Você pode desabilitar o recurso no Gerenciamento de recursos.

Para desabilitar os eventos de diagnóstico no Application Insights, siga estas etapas.

1. No headquarters, acesse **Administração do sistema \> Insights Operacionais**.
1. Na guia **Configuração**, defina a opção **Eventos de canal do Commerce** como **Não**.
1. Depois de concluir a configuração anterior, execute o trabalho **CDX 1110**. Você pode aguardar que o trabalho seja executado de acordo com a agenda ou pode executá-lo manualmente.
1. No Lifecycle Services, vá para **Detalhes do ambiente \> Commerce \> Gerenciar**, selecione uma instância do CSU e selecione **Reiniciar**. Repita esta etapa para cada CSU.
1. Repita as etapas anteriores para cada ambiente em que você planeja desabilitar o Application Insights.

Para desabilitar eventos de diagnóstico para um único ambiente, exclua a chave de instrumentação na guia **Registro do Application Insights** da página **Insights Operacionais**. Em seguida, conclua as etapas 3 e 4 do procedimento anterior.

> [!NOTE]
> No Commerce versão 10.0.29 e posteriores, as etapas desta seção também desabilitam o fluxo de eventos do Insights Operacionais de PDV para sua conta do Application Insights. 
