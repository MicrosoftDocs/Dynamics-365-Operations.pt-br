---
title: Configurar um dispositivo para executar a interface de execução de piso de produção
description: A interface de execução de piso de produção é configurada para todos os dispositivos no piso de produção. Geralmente, as empresas configuram cada dispositivo de forma diferente, dependendo da finalidade à qual o dispositivo serve. Por exemplo, uma empresa pode ter um dispositivo na área da recepção, onde os trabalhadores registram a entrada e a saída, e outro no chão de fábrica, onde os trabalhadores gerenciam seus trabalhos.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution, HcmWorker, JmgProductionFloorExecutionDeviceConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 503ba8ae95119f3ce9533f81cdd16c34cf3a9223
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574536"
---
# <a name="set-up-a-device-to-run-the-production-floor-execution-interface"></a>Configurar um dispositivo para executar a interface de execução de piso de produção

[!include [banner](../includes/banner.md)]

A interface de execução de piso de produção é configurada para todos os dispositivos no piso de produção. Geralmente, as empresas configuram cada dispositivo de forma diferente, dependendo da finalidade à qual o dispositivo serve. Por exemplo, uma empresa pode ter um dispositivo na área da recepção, onde os trabalhadores registram a entrada e a saída, e outro no chão de fábrica, onde os trabalhadores gerenciam seus trabalhos.

## <a name="set-the-configuration-and-filters-for-a-specific-device"></a>Definir a configuração e os filtros para um dispositivo específico

Para definir a configuração e os filtros de trabalho para um dispositivo, entre na página **Execução de piso de produção** usando uma conta com uma função de segurança que inclua o direito *Manter supervisor de tempo*. (Entre as funções de segurança prontas para uso, somente o *Supervisor de chão de fábrica* tem esse direito). Em seguida, siga estas etapas.

1. Acesse o dispositivo que deseja configurar e entre no Microsoft Dynamics 365 Supply Chain Management como um supervisor de chão de fábrica. (Use uma conta que inclua o direito *Manter de supervisor de tempo*).
1. Verifique se há uma configuração disponível para o dispositivo que você está configurando. Se não houver nenhuma configuração, uma configuração padrão será fornecida. Para obter mais informações sobre como definir uma configuração, consulte [Configurar a interface de execução de piso de produção](production-floor-execution-configure.md).
1. Acesse **Controle de produção \> Execução de fabricação \> Execução de piso de produção**.

    Se a interface de execução de piso de produção já tiver sido configurada pelo menos uma vez no dispositivo atual, será exibida uma página de entrada. Caso contrário, será exibida uma página de boas-vindas.

1. Na página de entrada ou na página de boas-vindas, selecione **Configurar**.
1. Selecione uma configuração na lista.
1. Selecione **Avançar**.
1. Selecione um ou mais filtros para aplicar ao dispositivo atual. Esses filtros ajudarão a garantir que apenas trabalhos relevantes sejam mostrados no dispositivo. Para definir um filtro, selecione o tipo de filtro para abrir uma lista de valores e, em seguida, selecione o valor a ser filtrado. Os filtros a seguir estão disponíveis:

    - **Unidade de produção** – esse filtro é o filtro de nível mais alto. Em geral, ele se refere a uma grande área de trabalho com vários grupos de recursos e recursos individuais.
    - **Grupo de recursos** – esse filtro é um filtro de nível intermediário. Normalmente, ele se refere a uma coleção de recursos relacionados em uma área limitada do espaço de trabalho. Se você selecionar um filtro de **Unidade de produção** primeiro, a lista de grupos de recursos mostrará somente grupos dessa unidade. Caso contrário, mostrará todos os grupos de recursos disponíveis.
    - **Recurso** – esse é o filtro mais específico. Em geral, ele se refere a um computador específico ou a outro recurso único. Se você selecionar um filtro de **Grupo de recursos** e/ou **Unidade de produção** primeiro, a lista de recursos mostrará somente os recursos desse grupo e/ou unidade. Caso contrário, mostrará todos os recursos disponíveis.

1. Selecione **OK**.
1. A página de entrada é exibida e seu dispositivo está pronto para uso.

## <a name="allow-a-worker-to-override-the-default-filters"></a>Permitir que um trabalhador substitua os filtros padrão

Você pode conceder permissão a trabalhadores específicos para alterar as configurações de filtro em qualquer dispositivo usado. Para os trabalhadores com essa permissão, a interface de execução de piso de produção fornece um botão **Filtro** nas páginas **Todos os trabalhos** e **Trabalho ativo**.

> [!NOTE]
> Se um trabalhador alterar um filtro, o novo filtro será aplicado a partir desse ponto para todos os usuários que entrarem no dispositivo.

Para permitir que um trabalhador substitua os filtros de trabalho padrão que foram configurados para um dispositivo, siga estas etapas.

1. Acesse **Hora e atendimento \> Configuração \> Tempo de registro dos trabalhadores**.
1. Selecione um trabalhador na lista para abrir a página **Trabalhadores com registro de tempo** desse trabalhador.
1. Na guia **Registro de tempo**, defina a opção **Definir filtros** como *Sim*.

## <a name="run-the-interface-in-full-screen-mode"></a>Executar a interface no modo de tela inteira

Geralmente, você executará a interface de execução de piso de produção em um dispositivo usado exclusivamente para essa finalidade. Portanto, pode fazer sentido executar a interface no modo de tela inteira, sem mostrar nenhum cromo de navegação e/ou navegador.

- Para ocultar o painel de navegação mostrado no Supply Chain Management, adicione o seguinte texto ao final da URL na barra de endereços do navegador: `\&limitednav=true`.
- Para ocultar também a barra de endereços do navegador, use o modo de tela inteira nativo do navegador. (Para obter instruções, consulte a documentação do navegador).

A parte superior da ilustração a seguir mostra como a interface é exibida por padrão. A parte inferior mostra como ele aparece no modo de tela inteira quando o painel de navegação está oculto.

![Interface padrão versus de tela inteira.](media/pfei-full-screen.png "Interface padrão versus de tela inteira")

## <a name="extend-the-session-past-12-hours"></a>Estender a sessão além de 12 horas

Por padrão, a interface de execução de piso de produção se desconecta automaticamente se ninguém usá-la em 12 horas. Um usuário do Supply Chain Management deverá entrar novamente. No entanto, você pode estender o tempo limite para até 90 dias.

Para estender o limite de tempo, entre no Supply Chain Management e Acesse **Administração do sistema \> Usuários \> Extensões de sessão**. Especifique a conta de usuário do Supply Chain Management usada para entrar no dispositivo e o número de horas em que a sessão deverá permanecer ativa.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]