---
title: Configurar a interface de execução de piso de produção
description: Este artigo descreve como criar uma ou mais configurações para a interface de execução do piso de produção. Quando você abre a interface de execução de piso de produção, ela carrega automaticamente uma configuração selecionada e um filtro de trabalho específicos do navegador e do dispositivo. Na configuração, você define as políticas que devem ser aplicáveis para um uso específico.
author: johanhoffmann
ms.date: 11/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 641b293617df608bc07b97c077dbcd05664f8e2a
ms.sourcegitcommit: 4abf9b375fed6885ea11a425c524958fea29c3b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2022
ms.locfileid: "9748677"
---
# <a name="configure-the-production-floor-execution-interface"></a>Configurar a interface de execução de piso de produção

[!include [banner](../includes/banner.md)]

Os trabalhadores de chão de fábrica usam a interface de execução de piso de produção para registrar o trabalho diário, como eles iniciam um trabalho, fazem comentários sobre trabalhos registram atividades indiretas e relatam uma ausência. Esses registros são a base para controlar o progresso e o custo em ordens de produção e para calcular a base para o pagamento dos trabalhadores.

Quando você abre a interface de execução de piso de produção, ela carrega automaticamente uma configuração selecionada e um filtro de trabalho específicos do navegador e do dispositivo. Na configuração, você define as políticas que devem ser aplicáveis para um uso específico. Aqui estão alguns exemplos de uso:

- Em um dispositivo no hall da empresa, os funcionários registram a entrada quando entram no escritório e a saída quando vão embora.
- Em um dispositivo no chão de fábrica, os operadores de máquina registram-se quando iniciam e concluem trabalhos. Eles também registram pausas e atividades indiretas.

Este artigo descreve as várias opções de configuração de uma interface de execução de piso de produção para cada dispositivo em uso no seu site.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>Ativar a interface de execução de piso de produção e seus recursos opcionais relacionados

A interface de execução de chão de produção e várias configurações opcionais descritas neste artigo devem ser ativadas no sistema para que você possa usá-las. Use a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar um ou todos os recursos descritos nas subseções a seguir, conforme necessário.

### <a name="the-production-floor-execution-interface"></a>A interface de execução de piso de produção

Este é o principal recurso descrito neste artigo e é um pré-requisito para todos os outros recursos mencionados nesta seção. A partir do Supply Chain Management 10.0.25, ele é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Execução de piso de produção* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="generate-license-plates"></a>Gerar placas de licença

Estes recursos disponibilizam a funcionalidade de placas de licença para a interface de execução de piso de produção. Se você quiser usá-los, ative os seguintes recursos no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (nesta ordem):

1. *Placa de licença para relatório de conclusão adicionada ao Dispositivo de ficha de trabalho*<br>(A partir do Supply Chain Management versão 10.0.21, este recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.25, este recurso é obrigatório.)
1. *Habilitar a geração automática do número da placa de licença ao concluir o relatório de conclusão no dispositivo de ficha de trabalho*<br>(A partir do Supply Chain Management versão 10.0.25, este recurso é obrigatório.)

### <a name="print-labels"></a>Imprimir etiquetas

Estes recursos disponibilizam a funcionalidade de impressão de etiquetas para a interface de execução de piso de produção. Se você quiser usá-los, ative os seguintes recursos no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (nesta ordem):

1. *Placa de licença para relatório de conclusão adicionada ao Dispositivo de ficha de trabalho*<br>(A partir do Supply Chain Management versão 10.0.21, este recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.25, este recurso é obrigatório.)
1. *Imprimir etiqueta do Dispositivo de Ficha de Trabalho*<br>(A partir do Supply Chain Management versão 10.0.25, este recurso é obrigatório.)

### <a name="allow-locking-the-touch-screen"></a>Permitir o bloqueio da tela touch

Esse recurso permite que os trabalhadores bloqueiem a tela touchscreen para que possam corrigi-la.

A partir da versão 10.0.21 do Supply Chain Management, este recurso está ativado por padrão. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão ativar ou desativar essa funcionalidade procurando o *Recurso para bloqueio de dispositivo de cartão de trabalho e terminal de cartão de trabalho para que eles possam ser limpos* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>Funcionalidade de gerenciamento de ativos para a interface de execução de piso de produção

Este recurso adiciona uma guia de gerenciamento de ativos à interface de execução de piso de produção. Os trabalhadores podem usar essa guia para selecionar um ativo que esteja conectado a um recurso de máquina dentro do filtro selecionado da lista de trabalhos. Para o ativo de máquina selecionado, o trabalhador pode exibir o estado e a integridade com base em valores de contador para até quatro contadores selecionados.

A partir da versão 10.0.25 do Supply Chain Management, este recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão ativar ou desativar essa funcionalidade pesquisando o recurso *Funcionalidade de gerenciamento de ativos para a interface de execução de chão de produção* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="job-search"></a>Pesquisa de trabalho

Este recurso permite adicionar um campo de pesquisa à lista de trabalhos. Os trabalhadores podem encontrar um trabalho específico inserindo a ID do trabalho ou encontrar todos os trabalhos para uma ordem específica inserindo a ID da ordem. Os trabalhadores podem inserir a ID usando um teclado ou digitalizando um código de barras.

A partir da versão 10.0.25 do Supply Chain Management, este recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão ativar ou desativar essa funcionalidade pesquisando o recurso *Pesquisa de trabalho para a interface de execução do chão de produção* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="report-on-co-products-and-by-products"></a>Relatar sobre coprodutos e subprodutos

Este recurso permite que os trabalhadores usem a interface de execução de piso de produção para relatar o progresso das ordens de lote. Isso inclui um relatório sobre coprodutos e subprodutos.

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir da versão 10.0.29 do Supply Chain Management, o recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade, pesquisando o recurso *Relatório sobre coprodutos e subprodutos da interface de execução do chão de produção* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="display-full-serial-batch-and-license-plate-numbers"></a>Exibir números completos de série, de lote e de placa de licença

Esse recurso oferece uma experiência melhor para exibir listas de números de placas de licença, de lote e de série na interface de execução de produção. A exibição é alterada de uma exibição de cartão que mostra um número limitado de caracteres para uma exibição de lista que fornece espaço suficiente para mostrar os valores completos. A lista também oferece a capacidade de procurar números específicos.

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir do Supply Chain Management versão 10.0.25, o recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão ativar ou desativar essa funcionalidade, pesquisando o recurso *Mostrar números de série, de lote e da placa de licença completos na interface de execução de chão de produção* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

A partir da versão 10.0.25 do Supply Chain Management, este recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade, pesquisando o recurso *Mostrar números de série, de lote e da placa de licença completos na interface de execução da área de produção* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="register-material-consumption"></a>Registrar consumo de materiais

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

Esse recurso permite que os trabalhadores usem a interface de execução do piso de produção para registrar o consumo de materiais, os números de lote e os números de série. Alguns fabricantes, especialmente no setor de processamento, devem registrar explicitamente a quantidade de material que é consumido para cada ordem de produção ou lote. Por exemplo, os trabalhadores podem usar uma escala para avaliar a quantidade de material que é consumido conforme trabalham. Para garantir a rastreabilidade total do material, essas organizações também devem registrar os números de lote que foram consumidos para produzir cada produto.

Existem duas versões deste recurso. Um oferece suporte a itens que *não estão* habilitados para usar processos de gerenciamento de depósito (WMS). O outro dá suporte a itens que *estão* habilitados para usar o WMS. Para usar essa funcionalidade, ative um ou ambos os seguintes recursos no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (nesta ordem), dependendo da existência de itens habilitados para o WMS:

- *Registrar consumo de material na interface de execução do piso de produção (não WMS)*
- *(Versão preliminar) Registrar consumo de materiais na interface de execução de piso de produção (habilitado para WMS)*

> [!IMPORTANT]
> Só é possível usar o recurso que não seja do WMS. Se você usar o WMS, deverá habilitar os dois recursos.

### <a name="report-on-catch-weight-items"></a>Relatório sobre itens de peso variável

Os trabalhadores podem usar a interface de execução de piso de produção para relatar o progresso de ordens de lote para itens de peso variável. As ordens de lote são criadas com base em fórmulas, que podem ser definidas para ter itens de peso variável como itens de fórmula, coprodutos e subprodutos. Uma fórmula também pode ser definida para ter linhas de fórmula para ingredientes definidos para peso variável. Os itens de peso variável usam duas unidades de medida para rastrear o estoque: quantidade de peso variável e quantidade de estoque. Por exemplo, no setor de alimentos, a carne na caixa pode ser definida como um item de peso variável, em que a quantidade em peso variável é usada para controlar o número de caixas e a quantidade de estoque é usada para rastrear o peso das caixas.

Para usar essa funcionalidade, ative o seguinte recurso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Relatório de itens de peso variável da interface de execução do piso de produção*

### <a name="the-my-day-dialog"></a>A caixa de diálogo "Meu dia"

A caixa de diálogo **Meu dia** oferece aos trabalhadores uma visão geral dos registros diários e dos saldos atuais de tempo pago, hora extra paga, ausência e ausência paga.

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir da versão 10.0.29 do Supply Chain Management, o recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade, pesquisando o recurso *Exibição "Meu dia" da interface de execução de chão de produção* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="teams"></a>Times

Quando vários trabalhadores são designados para o mesmo trabalho de produção, eles podem formar uma equipe. A equipe pode designar um trabalhador como coordenador. Os trabalhadores restantes se tornarão automaticamente assistentes desse coordenador. Para a equipe resultante, somente o coordenador deve registrar o status do trabalho. Os registros de hora se aplicam a todos os membros da equipe.

Para usar essa funcionalidade, ative o seguinte recurso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Equipes de produção na interface de execução de piso de produção*

### <a name="additional-configuration-in-the-production-floor-execution-interface"></a>Configuração adicional na interface de execução de chão de produção

Esse recurso adiciona configurações para a seguinte funcionalidade na página **Configurar execução de piso de produção**:

- Abrir automaticamente a caixa de diálogo **Iniciar trabalho** quando uma pesquisa é concluída.
- Abrir automaticamente a caixa de diálogo **Progresso do relatório** quando uma pesquisa é concluída.
- Preencher previamente a quantidade restante na caixa de diálogo **Progresso do relatório**.
- Permitir os ajustes de consumo de material a partir da caixa de diálogo **Progresso do relatório**. (Essa funcionalidade também requer o recurso *Registrar consumo de material na interface de execução do piso de produção (não WMS)*.)
- Habilitar pesquisas por ID de projeto.

As informações sobre como usar as configurações são fornecidas mais adiante neste artigo.

Para usar essa funcionalidade, ative o seguinte recurso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Configuração adicional na interface de execução de piso de produção*

### <a name="enable-the-my-jobs-tab"></a>Habilitar a guia Meus trabalhos

A guia **Meus trabalhos** permite que trabalhadores exibam facilmente todos os trabalhos não iniciados e não concluídos que são atribuídos especificamente a eles. Ele é útil em empresas em que os trabalhos são às vezes ou sempre atribuídos a trabalhadores específicos (recursos humanos) em vez de outros tipos de recursos (como máquinas).

Para usar essa funcionalidade, ative o seguinte recurso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Guia Meus trabalhos na interface de execução de piso de produção*

### <a name="enable-use-of-a-numpad-on-the-sign-in-page"></a>Habilitar o uso de um teclado numérico na página de entrada

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until 10.0.31 GA -->

Esse recurso permite que os administradores adicionem um controle de teclado numérico à página de entrada para a interface de execução da área de produção. Os trabalhadores podem então entrar usando o teclado numérico para inserir a ID do crachá ou o número pessoal.

Para usar essa funcionalidade, ative o seguinte recurso em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Habilitar o uso de um teclado numérico na página de entrada*

## <a name="work-with-production-floor-execution-configurations"></a>Trabalhar com configurações de execução de piso de produção

Para criar e manter as configurações de execução de piso de produção, acesse **Controle de produção \> Configuração \> Execução de fabricação \> Configurar execução de piso de produção**. A página **Configurar execução de piso de produção** mostra uma lista das configurações existentes. Nessa página, você pode executar as seguintes ações:

- Selecione qualquer configuração de piso de produção listada na coluna à esquerda para exibi-la e editá-la.
- Selecione **Novo** no Painel de Ações para adicionar uma nova configuração à lista. Em seguida, no campo **Configuração**, insira um nome para identificar a nova configuração. O nome inserido deve ser exclusivo entre todas as configurações e você não poderá editá-lo posteriormente. No campo **Descrição**, você pode inserir uma descrição da configuração.

Em seguida, defina as várias configurações para a configuração selecionada, conforme descrito nas subseções a seguir.

### <a name="the-general-fasttab"></a>Guia rápida Geral

As configurações a seguir estão disponíveis na guia rápida **Geral**:

- **Somente entrada e saída** – defina esta opção como *Sim* para criar uma interface simplificada que forneça somente a funcionalidade de entrada e saída. Essa configuração desabilita a maioria das outras opções desta página. Você deve remover todas as linhas da Guia Rápida **Seleção de guias** para poder habilitar esta opção.
- **Habilitar pesquisa** – defina esta opção como *Sim* para incluir um campo de pesquisa na lista de trabalhos. Os trabalhadores podem encontrar um trabalho específico inserindo a ID do trabalho ou encontrar todos os trabalhos para uma ordem específica inserindo a ID da ordem. Os trabalhadores podem inserir a ID usando um teclado ou digitalizando um código de barras.
- **Habilitar pesquisa por ID de projeto** – defina esta opção como *Sim* para permitir que os trabalhadores pesquisem por ID de projeto (além das IDs do trabalho e da ordem) no campo de pesquisa da interface de execução de piso de produção. Você só poderá definir essa opção como *Sim* se a opção **Habilitar pesquisa** também estiver definida como *Sim*.
- **Abrir automaticamente a caixa de diálogo inicial** – quando essa opção está definida como *Sim*, a caixa de diálogo **Iniciar trabalho** é automaticamente aberta quando os trabalhadores usam a barra de pesquisa para encontrar um trabalho.
- **Abrir automaticamente a caixa de diálogo de progresso do relatório** – quando essa opção está definida como *Sim*, a caixa de diálogo **Progresso do relatório** é automaticamente aberta quando os trabalhadores usam a barra de pesquisa para encontrar um trabalho.
- **Habilitar ajuste de material** – defina essa opção como *Sim* para habilitar o botão **Ajustar material** na caixa de diálogo **Progresso do relatório**. Os trabalhadores podem selecionar esse botão para ajustar o consumo de material para cada trabalho.
- **Quantidade de relatório em registro de saída** - defina essa opção como *Sim* para que os funcionários façam comentários sobre os trabalhos em andamento durante o registro de saída. Quando definido como *Não*, os funcionários não serão solicitados.
- **Bloquear funcionário** – quando essa opção for definida como *Não*, os trabalhadores serão desconectados imediatamente depois que fizerem um registro (como um novo trabalho). A interface retornará à página de entrada. Quando esta opção for definida como *Sim*, os trabalhadores permanecerão conectados à interface de execução de piso de produção. No entanto, um trabalhador pode se desconectar manualmente para que outro trabalhador possa entrar enquanto a interface de execução de piso de produção continua em execução na mesma conta de usuário do sistema. Para obter mais informações sobre esses tipos de contas, consulte [Usuários atribuídos](config-job-card-device.md#assigned-users).
- **Usar o tempo real de registro** - defina essa opção como *Sim* para definir a hora para cada novo registro como a hora exata em que o trabalhador enviou o registro. Quando essa opção for definida como *Não*, a hora de entrada será usada. Em geral, você desejará definir essa opção como *Sim* se tiver definido as opções **Bloquear funcionário** e/ou **Trabalhador único** como *Sim* em casos onde os trabalhadores com frequência permanecem conectados por períodos mais longos.
- **Trabalhador único** – Defina essa opção como *Sim* se apenas um trabalhador usar a interface de execução de piso de produção onde essa configuração está ativa. Quando essa opção estiver definida como *Sim*, a opção **Bloquear funcionário** será automaticamente definida como *Sim*. Além disso, essa configuração remove o requisito (e a capacidade) de o trabalhador entrar usando uma ID de crachá (ou outra ID semelhante). Em vez disso, o trabalhador entra no Microsoft Dynamics 365 Supply Chain Management usando uma conta de usuário do sistema vinculada a um *trabalhador com tempo registrado* (da tabela *Trabalhadores*) e entra na interface de execução de piso de produção como esse trabalhador ao mesmo tempo.
- **Habilitar teclado numérico** – Defina esta opção como *Sim* para adicionar um teclado numérico à tela de entrada, que permite que os funcionários insiram sua ID de crachá ou número pessoal usando um teclado numérico de tela sensível ao toque. Defina esta opção como *Não* para ocultar o teclado numérico.
- **Permitir bloqueio da tela touch** – Defina essa opção como *Sim* para permitir que os trabalhadores bloqueiem a tela touch da interface de execução de piso de produção para que possam corrigi-la. Quando essa opção é definida como *Sim*, um botão **Bloquear tela para correção** é adicionado à página de entrada. Quando um trabalhador seleciona esse botão, a tela touch trava temporariamente para evitar a entrada não intencional. Também é mostrado um temporizador de contagem regressiva. Então, o trabalhador pode limpar com segurança o dispositivo e a tela. Quando a contagem regressiva for concluída, a tela touch será automaticamente desbloqueada.
- **Duração do bloqueio de tela** - quando a opção **Permitir bloqueio da tela touch** estiver definida como *Sim*, use essa opção para especificar o número de segundos de bloqueio da tela touch para correção. A duração deve ser entre 5 e 120 segundos.
- **Gerar placa de licença** – Defina essa opção como *Sim* para gerar uma nova placa de licença cada vez que um trabalhador usar a interface de execução de piso de produção para relatar como concluído. O número da placa de licença é gerado de uma sequência numérica configurada na página **Parâmetros de gerenciamento de depósito**. Quando essa opção estiver definida como *Não*, os trabalhadores deverão especificar uma placa de licença existente ao relatarem como concluído.
- **Imprimir etiqueta** – Defina essa opção como *Sim* para imprimir uma etiqueta da placa de licença quando um trabalhador usar a interface de execução de piso de produção para relatar como concluído. A configuração da etiqueta é configurada no roteamento de documentos, conforme descrito nos [Layouts de etiquetas de roteamento de documentos](../warehousing/document-routing-layout-for-license-plates.md).

### <a name="the-tab-selection-fasttab"></a>Guia rápida de seleção de guia

Use as configurações na guia rápida **Seleção de guia** para escolher quais guias devem ser exibidas pela interface de execução de piso de produção quando a configuração atual estiver ativa. Você pode criar quantas guias forem necessárias e, em seguida, adicioná-las e organizá-las conforme apropriado usando os botões da barra de ferramentas de Guia rápida. Para obter informações sobre como criar guias e trabalhar com as configurações aqui, consulte [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md).

### <a name="the-report-progress-fasttab"></a>Guia rápida Progresso do relatório

As configurações a seguir estão disponíveis na guia rápida **Progresso do relatório**:

- **Habilitar ajuste de material** – defina essa opção como *Sim* para incluir o botão **Ajustar material** na caixa de diálogo **Progresso do relatório**. Os trabalhadores podem selecionar esse botão para ajustar o consumo de material para cada trabalho.
- **Quantidade restante padrão** – defina essa opção como *Sim* para preencher previamente a quantidade restante esperada para um trabalho de produção na caixa de diálogo **Progresso do relatório**.

## <a name="clean-up-job-configurations"></a>Limpar configurações de trabalho

Quando o supervisor de chão de fábrica configura a interface de execução de produção, ele seleciona uma configuração e um filtro de trabalho. Essas seleções são armazenadas em uma tabela de referência no Supply Chain Management, e o navegador usa uma ID armazenada em um cookie local para encontrar a linha correta nessa tabela. A tabela também registra a data e a hora em que um trabalhador entrou pela última vez em cada dispositivo.

Um trabalho em lotes limpa periodicamente entradas na tabela de referências para dispositivos que não registraram nenhuma atividade nos últimos 60 dias. Você também pode limpar manualmente as entradas a qualquer momento seguindo essas etapas.

1. Acesse **Controle de produção \> Configuração \> Execução de fabricação \> Configurar execução de piso de produção**.
1. No Painel de Ação, selecione **Limpar configurações de cliente**.
1. Na caixa de diálogo **Limpar configuração do cliente**, defina o campo **Número de dias** como o número de dias de inatividade (antes de hoje) a ser considerado. Você removerá todas as configurações e os registros de entrada dos dispositivos que não estavam ativos durante esse tempo.
1. Selecione **OK** para limpar as configurações relevantes, com base na configuração de **Número de dias**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
