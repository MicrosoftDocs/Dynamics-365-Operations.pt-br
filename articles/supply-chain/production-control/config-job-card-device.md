---
title: Configurar o cartão de trabalho para dispositivos
description: Este tópico descreve as várias opções para configurar o dispositivo de ficha de trabalho.
author: johanhoffmann
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch, JmgRegistrationTouchUserConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 2ccfbadb48e2ecd274e68201bbbc7858ab01203a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836581"
---
# <a name="configure-job-card-for-devices"></a>Configurar o cartão de trabalho para dispositivos

[!include [banner](../includes/banner.md)]

O dispositivo de ficha de trabalho é usado pelos funcionários de chão de fábrica para registrar o trabalho diário; por exemplo, quando os trabalhos são iniciados, relatar comentários sobre trabalhos, registrar atividades indiretas e relatar a ausência. Esses registros são a base para controlar o progresso e o custo em ordens de produção e para calcular a base para o pagamento dos trabalhadores. Este tópico descreve as várias opções para configurar dispositivos de ficha de trabalho.

## <a name="enable-new-features-in-feature-management"></a>Habilitar novos recursos no gerenciamento de recursos

Algumas das configurações descritas neste tópico devem ser habilitadas no sistema para que elas possam ser disponibilizadas para você. Use a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar qualquer ou todos os recursos a seguir, conforme a necessidade.

### <a name="generate-license-plate"></a>Gerar placa de licença

Para disponibilizar este recurso, habilite os seguintes recursos no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (em ordem):

1. Placa de licença para relatório de conclusão adicionada ao Dispositivo de ficha de trabalho
1. Habilitar a geração automática do número da placa de licença ao concluir o relatório de conclusão no dispositivo de ficha de trabalho

### <a name="print-label"></a>Imprimir etiqueta

Para disponibilizar este recurso, habilite os seguintes recursos no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (em ordem):

1. Placa de licença para relatório de conclusão adicionada ao Dispositivo de ficha de trabalho
1. Imprimir etiqueta do Dispositivo de Ficha de Trabalho

### <a name="allow-locking-of-touch-screen"></a>Permitir o bloqueio da tela de toque

Para disponibilizar este recurso, habilite o seguinte recurso no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Recurso para bloqueio de dispositivo de ficha de trabalho e terminal de ficha de trabalho para que eles possam ser limpos

## <a name="manage-your-device-configurations"></a>Gerenciar suas configurações de dispositivo

Para definir configurações de dispositivo, vá para **Controle de produção > Configuração > Execução de fabricação > Configurar ficha de trabalho para dispositivos**. A página **Configurar ficha de trabalho para dispositivos** é aberta, que mostra uma lista das configurações existentes. Aqui, você pode fazer o seguinte: 

- Selecione qualquer configuração de dispositivo listada na coluna à esquerda para exibi-la e editá-la.
- Selecione **Novo** no Painel de Ações para adicionar uma nova configuração de dispositivo à lista. Insira um nome no campo **Configuração** para identificar a nova configuração. O valor inserido aqui deve ser exclusivo entre todas as configurações de dispositivo e você não poderá editá-lo posteriormente.

Consulte as seções a seguir para obter detalhes sobre cada configuração para configurar dispositivos de ficha de trabalho.

## <a name="general-settings"></a>Configurações gerais

A Guia Rápida **Geral** permite configurar cada uma das várias opções disponíveis para a configuração de dispositivo selecionada. As seguintes configurações estão disponíveis:

- **Quantidade de relatório em registro de saída** - defina isso como **Sim** para que os funcionários relatem comentários sobre os trabalhos em andamento durante o registro de saída. Quando definido como **Não**, os funcionários não serão solicitados.
- **Bloquear funcionário** - quando esta opção for definida como **Não**, cada trabalhador será desconectado imediatamente depois de criar um registro (como um novo trabalho) e, depois, o dispositivo retornará à página de logon. Quando esta opção for definida como **Sim**, cada trabalhador permanecerá conectado ao dispositivo de ficha de trabalho. No entanto, o trabalhador ainda poderá fazer logout manualmente para permitir que outro trabalhador efetue login enquanto o dispositivo de ficha de trabalho continuar sendo executado na mesma conta de usuário do sistema. Para obter mais informações sobre esses tipos de contas, consulte [Usuários atribuídos](#assigned-users).
- **Scanner de código de barras** - defina isso como **Sim** para fornecer uma opção no dispositivo de ficha de trabalho que permita aos trabalhadores registrar o início de um novo trabalho examinando um código de barras.
- **Use o tempo real de registro** - defina isso como **Sim** para definir a hora para cada novo registro ser igual ao tempo exato que o registro foi enviado por um trabalhador. Defina como **Não** para usar o tempo de logon. Em geral, você desejará definir isso como **Sim** se tiver habilitado as opções **Bloquear funcionário** e/ou **Trabalhador único**, em que os trabalhadores em geral permanecem registrados por períodos mais longos.
- **Trabalhador único** - defina esta opção como **Sim** se apenas um trabalhador usar cada dispositivo de ficha de trabalho no qual essa configuração está ativa. Quando esta opção é selecionada, a opção **Bloquear funcionário** é automaticamente definida como **Sim**. Além disso, esta opção remove a necessidade (e a capacidade) de o trabalhador efetuar login usando uma ID de crachá (ou semelhante). Em vez disso, o trabalhador entra no Supply Chain Management usando uma conta de usuário do sistema vinculada a um *Trabalhador com tempo registrado* (da tabela *trabalhadores*) e faz logon no dispositivo de ficha de trabalho como esse trabalhador ao mesmo tempo.  Para obter mais informações sobre esses tipos de contas, consulte [Usuários atribuídos](#assigned-users).
- **Permitir que os trabalhadores definam filtros pessoais** - defina esta opção como **Sim** para permitir que os trabalhadores filtrem os trabalhos exibidos no dispositivo. O trabalhador pode modificar valores para qualquer um dos três critérios de filtro: **Unidade de produção**, **Grupo de recursos** e **Recurso**. Somente os trabalhos que forem agendados em recursos que correspondam aos critérios de filtragem selecionados aparecerão no dispositivo. Você também pode atribuir valores padrão para qualquer um ou todos esses critérios; eles serão aplicados mesmo se essa opção não estiver selecionada.
- **Permitir bloqueio da tela sensível ao toque** - Configure esta opção como **Sim** para permitir que os trabalhadores bloqueiem a tela sensível ao toque do dispositivo da ficha de trabalho para que possam corrigi-lo. Quando habilitado, um botão **Bloquear tela para correção** é adicionado à página de logon do dispositivo. Quando um trabalhador seleciona esse botão, a tela sensível ao toque trava temporariamente para evitar a entrada não intencional e um temporizador de contagem regressiva é exibido. Agora, o trabalhador pode limpar com segurança o dispositivo e a tela. Quando a contagem regressiva é concluída, a tela de toque é automaticamente desbloqueada novamente.
- **Duração do bloqueio de tela** - quando a opção **Permitir bloqueio da tela sensível ao toque** estiver habilitada, use esta opção para especificar o número de segundos de bloqueio da tela sensível ao toque para correção. A duração deve ser entre 5 e 120 segundos.
- **Unidade de produção** - Selecione uma unidade de produção a ser aplicada como um critério de filtro padrão para a lista de trabalhos mostrada para cada trabalhador. Somente os trabalhos que são agendados em recursos agrupados na unidade de produção selecionada serão exibidos inicialmente pelo dispositivo. Se **Permitir que os trabalhadores definam filtros pessoais** estiver habilitado, os funcionários poderão editar esse valor; caso contrário, esse filtro sempre se aplicará quando a configuração desse dispositivo estiver ativa.
- **Grupo de recursos** - Selecione um grupo de recursos a ser aplicado como um critério de filtro padrão para a lista de trabalhos mostrada para cada trabalhador. Somente os trabalhos agendados em recursos agrupados no grupo de recursos selecionado serão exibidos inicialmente pelo dispositivo. Se **Permitir que os trabalhadores definam filtros pessoais** estiver habilitado, os funcionários poderão editar esse valor; caso contrário, esse filtro sempre se aplicará quando a configuração desse dispositivo estiver ativa.
- **Recurso** - Selecione um recurso a ser aplicado como um critério de filtro padrão para a lista de trabalhos mostrada para cada trabalhador. Somente os trabalhos agendados no recurso selecionado serão exibidos inicialmente pelo dispositivo. Se **Permitir que os trabalhadores definam filtros pessoais** estiver habilitado, os funcionários poderão editar esse valor; caso contrário, esse filtro sempre se aplicará quando a configuração desse dispositivo estiver ativa.
- **Gerar placa de licença** - Defina esta opção como **Sim** para gerar uma nova placa de licença cada vez que um trabalhador usar o dispositivo de ficha de trabalho para relatar como concluído. O número da placa de licença é gerado a partir de uma sequência numérica configurada na página **Parâmetros de gerenciamento de depósito**. Quando definido como **Não**, os trabalhadores devem especificar uma placa de licença existente ao relatar como concluído.
- **Imprimir etiqueta** - Defina esta opção como **Sim** para imprimir uma etiqueta da placa de licença quando um trabalhador usar o dispositivo de ficha de trabalho para relatar como concluído. A configuração da etiqueta é configurada no roteamento de documentos, conforme descrito no [Layout de roteamento de documentos para etiquetas da placa de licença](../warehousing/document-routing-layout-for-license-plates.md).

<a name="assigned-users"></a>

## <a name="assigned-users"></a>Usuários atribuídos

Use a Guia Rápida **Usuários atribuídos** para associar um ou mais usuários do sistema à configuração do dispositivo atual. Cada usuário do sistema pode ter apenas uma configuração de dispositivo de trabalho atribuída.

Ao configurar um dispositivo, um trabalho de TI costuma entrar no Supply Chain Management usando uma conta de usuário do sistema. Daí em diante, a configuração do dispositivo de trabalho associada a esse usuário do sistema se aplicará, desde que o usuário do sistema permaneça conectado. Essas contas de usuário do sistema são normalmente limitadas para permitir o acesso somente à página de dispositivo de ficha de trabalho e nenhuma outra parte do Supply Chain Management.

Depois que o usuário do sistema estiver conectado e a configuração do dispositivo de trabalho for carregada, os trabalhadores poderão entrar no dispositivo de ficha de trabalho usando a conta de *trabalhador com tempo registrado* (por exemplo, digitalizando um código de barras em seu crachá) para que possam iniciar novos trabalhos e criar outros tipos de registros. Vários trabalhadores podem entrar e sair durante o dia, enquanto a mesma configuração de dispositivo permanece em vigor nessa máquina porque o usuário do sistema permanece conectado ao Supply Chain Management no dia.

No entanto, como citado anteriormente, quando você usa uma configuração de dispositivo com a opção **Trabalhador único**, os próprios funcionários costumam entrar no Supply Chain Management usando um usuário do sistema vinculado à conta de *trabalhador com tempo registrado* deles; portanto, eles carregam a configuração de dispositivo e entram como um trabalhador no dispositivo de ficha de trabalho ao mesmo tempo.

## <a name="additional-resources"></a>Recursos adicionais

[Relatar como concluído no dispositivo de ficha de trabalho](report-finished-job-device.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]