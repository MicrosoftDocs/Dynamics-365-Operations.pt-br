---
title: Cenários de exemplo de contagem cíclica
description: Este artigo fornece uma coleção de cenários que exploram os recursos de contagem cíclica do Microsoft Dynamics 365 Supply Chain Management.
author: GalynaFedorova
ms.date: 06/08/2021
ms.topic: article
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 90a3f132a96081b56ab60f5b0ba5cc328b820879
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899314"
---
# <a name="cycle-counting-example-scenarios"></a>Cenários de exemplo de contagem cíclica

[!include [banner](../includes/banner.md)]

Este artigo fornece uma coleção de cenários que exploram os recursos de contagem cíclica do Microsoft Dynamics 365 Supply Chain Management. Primeiro, ele descreve os requisitos para o ambiente existente do Supply Chain Management. Em seguida, explica como configurar a contagem cíclica e descreve todas as etapas da contagem cíclica. Quando terminar, você terá uma boa compreensão da contagem cíclica, incluindo contagem cíclica guiada, contagem cíclica cega, contagem cíclica pontual, restrições de contagem cíclica e planos de contagem cíclica.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Cada cenário neste artigo faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Supply Chain Management. Se você deseja usar os valores fornecidos aqui conforme soluciona os cenários, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal (empresa) como **USMF** antes de começar.

### <a name="turn-on-support-for-the-warehouse-management-mobile-app"></a>Ative o suporte do aplicativo móvel Warehouse Management

Para usar o aplicativo móvel Warehouse Management, o recurso *Configurações de usuário, ícones e títulos de etapas do novo aplicativo de depósito* deve estar ativado no sistema. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Configurações de usuário, ícones e títulos de etapas do novo aplicativo de depósito* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="prepare-demo-data-for-the-scenarios"></a><a name= "prepare-demo-data"></a>Preparar dados de demonstração para os cenários

Siga estas etapas para confirmar que todos os dados de demonstração necessários para os cenários estão disponíveis na empresa USMF em seu sistema. Crie todos os registros ou valores que estão faltando.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalhador**.
1. No painel da lista, selecione **Julia Funderburk**.
1. Na Guia Rápida **Usuários**, selecione a linha que tem os valores a seguir. Se nenhuma linha existente tiver esses valores, crie-a.

    - **Identificação de usuário:** *61*
    - **Nome de usuário:** *WH61*
    - **Depósito padrão:** *61*
    - **Nome do menu:** *Principal*

1. Na Guia Rápida **Trabalho**, defina os seguintes valores para o usuário *61* se eles ainda não estiverem definidos:

    - **É um supervisor de contagem cíclica:** *Não*
    - **Limite máximo da porcentagem:** *0*
    - **Limite máximo da quantidade:** *0*
    - **Limite máximo do valor:** *0*

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Pools de trabalho**.
1. Os pools de trabalho são usados para separar o trabalho de depósito com base no tipo de trabalho (nesse caso, trabalho de contagem cíclica). Verifique se existe um registro que tenha as seguintes configurações:

    - **ID do pool de trabalho:** *CycleCount*
    - **Descrição:** *Contagem cíclica*

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No painel da lista, selecione o registro chamado *Contagem Cíclica*. Se nenhum registro existente tiver esse nome, crie-o. Confirme ou defina os seguintes valores para o registro:

    - **Nome do item do menu:** *Contagem Cíclica*
    - **Título:** *Contagem Cíclica Guiada*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Sim*
    - **Direcionado por** *Sistema dirigido* (Este valor indica que o Supply Chain Management atribuirá um ID de trabalho de contagem cíclica ao trabalhador.)
    - **Exibir status do estoque:** *Sim*

1. No Painel de Ação, selecione **Contagem cíclica**.
1. Na caixa de diálogo **Contagem cíclica do dispositivo móvel**, confirme ou defina os seguintes valores:

    - **Exibir número do item:** *Sim*
    - **Exibir placa de licença:** *Sim*
    - **Número de tentativas:** *1*

1. Selecione **OK** para fechar a caixa de diálogo.
1. No painel da lista, selecione o registro chamado *Contagem Cíclica Cega*. Se nenhum registro existente tiver esse nome, crie-o. Confirme ou defina os seguintes valores para o registro:

    - **Nome do item do menu:** *Contagem Cíclica Cega*
    - **Título:** *Contagem Cíclica Cega*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Sim*
    - **Direcionado por:** *Agrupamento de contagem cíclica* (Este valor indica que o trabalhador pode agrupar as IDs de trabalho de contagem cíclica que são específicas de uma localização, uma zona, ou um pool de trabalho.)

1. No Painel de Ação, selecione **Contagem cíclica**.
1. Na caixa de diálogo **Contagem cíclica do dispositivo móvel**, confirme ou defina os seguintes valores:

    - **Exibir número do item:** *Não*
    - **Exibir placa de licença:** *Não*
    - **Número de tentativas:** *0*

1. Selecione **OK** para fechar a caixa de diálogo.
1. No painel da lista, selecione o registro chamado *Contagem Pontual*. Se nenhum registro existente tiver esse nome, crie-o. Confirme ou defina os seguintes valores para o registro:

    - **Nome do item do menu:** *Contagem Pontual*
    - **Título:** *Contagem Pontual*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Não*
    - **Processo de criação de trabalho:** *Contagem cíclica pontual* (Este valor indica que o trabalhador pode contar itens em um local de depósito a qualquer momento, sem criar o trabalho de contagem cíclica. Para fazer a contagem cíclica pontual em um local, o trabalhador insere a ID do local.)

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. No painel da lista, selecione o registro chamado *Estoque*. Se nenhum registro existente tiver esse nome, crie-o. Confirme se os itens do menu de contagem cíclica a seguir aparecem na coluna **Estrutura de menu**:

    - Contagem Cíclica
    - Contagem Cíclica Cega
    - Contagem pontual

1. Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Contagem cíclica**, defina os seguintes valores:

    - **Tipo de ajuste de contagem cíclica padrão:** *Contagem cíclica* (Este campo especifica o tipo de diário que é postado quando a contagem cíclica é feita.)
    - **ID da classe de trabalho de contagem cíclica padrão:** *CCount* (Este campo especifica a classe de trabalho que é usada para contagem cíclica.)
    - **Prioridade de trabalho de contagem cíclica padrão:** *50* (Este campo define a prioridade que o trabalho de contagem cíclica tem em relação a outros tipos de trabalho no depósito. Ao inserir um número menor que o número inserido para outros tipos de trabalho, você aumenta a prioridade do trabalho de contagem cíclica.)

1. Acesse **Gerenciamento de depósito \> Configuração \> Estoque \> Tipos de ajuste**.
1. A página **Tipos de ajuste** permite criar códigos para os diferentes ajustes de entrada e saída que podem ocorrer. Confirme se existe um registro que tenha as seguintes configurações:

    - **Tipo de ajuste de estoque:** *Contagem Cíclica*
    - **Descrição:** *Contagem cíclica*
    - **Nome:** *ICnt*

1. Acesse **Gerenciamento de depósito \> Configuração \> Configuração do depósito \> Depósitos**.
1. No painel da lista, selecione o depósito *61*. Se nenhum registro existente tiver esse nome, crie-o.
1. Na Guia Rápida **Depósito**, defina os seguintes valores:

    - **Usar o processo de gerenciamento de depósito:** *Sim* (Esse valor habilita o depósito para processos de gerenciamento de depósito.)
    - **Permitir movimentações de placa de licença durante a contagem cíclica:** *Sim* (Este valor permite que os trabalhadores movam placas de licença durante uma contagem cíclica.)

## <a name="scenario-1-guided-cycle-counting"></a>Cenário 1: Contagem cíclica guiada

Antes que a contagem cíclica guiada possa ocorrer, será necessário criar algum trabalho. Este trabalho guiará a pessoa atribuída no depósito, de um local para outro, para completar as contagens que estão configuradas no trabalho.

### <a name="create-cycle-counting-work-for-scenario-1"></a>Criar trabalho de contagem cíclica para o cenário 1

Siga estas etapas para criar trabalhos de contagem cíclica para a localização do item *01A02R2S2B* (BULK-06) no depósito *61*.

1. Acesse **Gerenciamento de depósito \> Contagem cíclica \> Trabalho de contagem cíclica por localização**.
1. Na caixa de diálogo **Criar trabalho de contagem cíclica por localização**, defina o campo **ID do pool de trabalho** como *CycleCount*.
1. Na Guia Rápida **Registros a incluir**, selecione **Filtro**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo**, siga estas etapas:

    - Na linha em que o campo **Campo** está definido como *Depósito*, defina o campo **Critérios** como *61*.
    - Na linha em que o campo **Campo** está definido como *Localização*, defina o campo **Critérios** como *01A02R2S2B*.

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. Selecione **OK** para fechar a caixa de diálogo **Criar trabalho de contagem cíclica por localização**.

    Quando o processo de criação do trabalho é concluído, uma mensagem é exibida no centro de ação.

1. Acesse **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Encontre o trabalho recém-criado definindo um filtro na coluna **ID do pool de trabalho** para encontrar registros que tenham um valor de *CycleCount*.

### <a name="do-cycle-counting-work-for-scenario-1"></a>Fazer o trabalho de contagem cíclica para o cenário 1

Depois de criar o trabalho de contagem cíclica, faça o trabalho contando itens em um local de depósito e, em seguida, usando um dispositivo móvel para inserir os resultados no Supply Chain Management. Siga estas etapas para fazer o trabalho de contagem cíclica no aplicativo móvel Warehouse Management.

1. Entre no aplicativo móvel Warehouse Management como o usuário de trabalho que você configurou na seção [Preparar dados de demonstração para os cenários](#prepare-demo-data) no início deste artigo. Para o exemplo deste artigo, o usuário se chama *Julia Funderburk* e está configurado para o depósito *61*. (Os dados de demonstração da USMF devem permitir que você entre como o usuário de trabalho inserindo *61* como a ID de usuário e *1* como a senha.)
1. No menu principal, selecione **Estoque**.
1. No menu **Estoque**, selecione **Contagem Cíclica Guiada**.
1. Selecione o campo **Qtd**, insira *9* usando o teclado numérico e, em seguida, selecione **OK** (o botão de marca de seleção).
1. O sistema esperava que você inserisse uma contagem de 10 peças para este item, esta localização e esta placa de licença. Portanto, é necessário recontar. Selecione o campo **Qtd**, insira *9* novamente usando o teclado numérico e, em seguida, selecione **OK** (o botão de marca de seleção). Na segunda tentativa, sua contagem será aceita.

    > [!NOTE]
    > Quando o sistema detectou uma diferença entre a quantidade disponível esperada e a quantidade inserida, ele solicitou que você contasse uma segunda vez porque o campo **Número de tentativas** está definido como *1* para o item do menu **Contagem Cíclica Guiada** do dispositivo móvel. Você foi guiado para um número de item específico e um número da placa de licença porque as opções **Exibir número de item** e **Exibir a placa de licença** estão definidas como *Sim* para o item do menu do dispositivo móvel.

1. Selecione o botão **OK** (o botão de marca de seleção).

### <a name="review-the-cycle-counting-differences-for-scenario-1"></a>Revise as diferenças de contagem cíclica para o cenário 1

Siga estas etapas para revisar as diferenças de contagem cíclica.

1. Retorne ao Supply Chain Management.
1. Acesse **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Encontre e selecione o trabalho de contagem cíclica que você analisou anteriormente. (Por exemplo, defina um filtro na coluna **ID do pool de trabalho** para encontrar registros que tenham um valor de *CycleCount*.) Observe que o campo **Status de trabalho** para este trabalho está agora definido como *Revisão pendente*.

    > [!NOTE]
    > Para a conta de usuário de trabalho que você usou para fazer o trabalho de contagem, a opção **Supervisor de contagem cíclica** é definida como *Não*, e os campos **Limite máximo da porcentagem**, **Limite máximo da quantidade** e **Limite de valor máximo** estão todos definidos como *0* (zero). Portanto, todas as diferenças de contagem que este usuário relata devem ser aprovadas manualmente, e o campo **Status de trabalho** do trabalho relacionado está definido como *Revisão pendente*. Se o valor contado estivesse dentro dos limites de desvio (conforme especificado nos campos **Limite percentual máximo** ou **Limite máximo da quantidade** na página **Usuários do trabalho**) ou se a opção **Supervisor de contagem cíclica** fosse definida como *Sim* para o usuário, o trabalho teria sido automaticamente fechado.

1. No Painel de ações, na guia **Trabalho**, selecione **Contagem cíclica**.
1. No Painel de Ação, selecione **Aceitar contagem**.

    A diferença é lançada usando o diário de contagem padrão, e uma nova ordem de serviço é criada.

1. Na página **Transações de contagem cíclica**, no Painel de Ação, selecione **Trabalho derivado** para encontrar o trabalho criado para a diferença aprovada.

## <a name="scenario-2-blind-cycle-counting"></a>Cenário 2: Contagem cíclica cega

Este cenário requer que o cenário 1 já esteja concluído em seu sistema.

### <a name="create-cycle-counting-work-for-scenario-2"></a>Criar trabalho de contagem cíclica para o cenário 2

Antes que a contagem cíclica cega possa ocorrer, será necessário criar algum trabalho. Siga estas etapas para criar trabalhos de contagem cíclica para a localização do item *01A02R2S2B* (BULK-06) no depósito *61*.

1. Acesse **Gerenciamento de depósito \> Contagem cíclica \> Trabalho de contagem cíclica por item**.
1. Na caixa de diálogo **Criar trabalho de contagem cíclica por item**, defina o campo **ID do pool de trabalho** como *CycleCount*.
1. Na Guia Rápida **Registros a incluir**, selecione **Filtro**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione três linhas com as seguintes configurações:

    - Linha 1:

        - **Tabela:** *Itens*
        - **Campo:** *Número do item*
        - **Critérios:** *L0101*

    - Linha 2:

        - **Tabela:** *Dimensões de estoque*
        - **Campo:** *Depósito*
        - **Critérios:** *61*

    - Linha 3:

        - **Tabela:** *Dimensões de estoque*
        - **Campo:** *Localização*
        - **Critérios:** *01A02R2S2B*

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. Selecione **OK** para fechar a caixa de diálogo **Criar trabalho de contagem cíclica por item**.

    Quando o processo de criação do trabalho é concluído, você recebe uma mensagem informacional.

### <a name="do-cycle-counting-work-for-scenario-2"></a>Fazer o trabalho de contagem cíclica para o cenário 2

Depois de criar o trabalho de contagem cíclica, siga estas etapas para fazer o trabalho no aplicativo móvel Warehouse Management.

1. Entre no aplicativo móvel Warehouse Management como o usuário de trabalho que você configurou na seção [Preparar dados de demonstração para os cenários](#prepare-demo-data) no início deste artigo. Para o exemplo deste artigo, o usuário se chama *Julia Funderburk* e está configurado para o depósito *61*. (Os dados de demonstração da USMF devem permitir que você entre como o usuário de trabalho inserindo *61* como a ID de usuário e *1* como a senha.)
1. No menu principal, selecione **Estoque**.
1. No menu **Estoque**, selecione **Contagem Cíclica Cega**.
1. Selecione o campo **ID da zona**, insira *BULK06* e selecione **OK** (o botão de marca de verificação).
1. Selecione o campo **Item**, insira *L0101* e selecione **OK** (o botão de marca de verificação).
1. Selecione o campo **Placa de licença**, insira *LP\_BULK\_06\_01* e selecione **OK** (o botão de marca de verificação).
1. Selecione o campo **Qtd**, insira *10* e selecione **OK** (o botão de marca de verificação).

    > [!NOTE]
    > Mesmo que o sistema tenha detectado uma diferença entre a quantidade disponível esperada e a quantidade verificada, ele não solicitou que você contasse uma segunda vez porque o campo **Número de tentativas** está definido como *0* (zero) para o item do menu **Contagem Cíclica Cega** do dispositivo móvel. Foi solicitado que você verificasse o número do item e a placa de licença porque as opções **Exibir número de item** e **Exibir a placa de licença** estão definidas como *Não* para o item do menu do dispositivo móvel.

1. Selecione o botão **OK** (o botão de marca de seleção).

### <a name="review-the-cycle-counting-differences-for-scenario-2"></a>Revise as diferenças de contagem cíclica para o cenário 2

Siga estas etapas para revisar as diferenças de contagem cíclica.

1. Retorne ao Supply Chain Management.
1. Acesse **Gerenciamento de depósito \> Comum \> Trabalho \> Trabalho de contagem cíclica com revisão pendente**.
1. No Painel de ações, na guia **Trabalho**, selecione **Contagem cíclica**.
1. No Painel de Ação, selecione **Rejeitar contagem**.

    Como a diferença de contagem foi rejeitada, o trabalho é fechado.

## <a name="scenario-3-spot-cycle-counting"></a>Cenário 3: Contagem cíclica pontual

O registro disponível indica que há uma quantidade disponível do item *L0101* no local *01A02R2S2B*. O trabalhador de depósito está no local *01A02R2S1B*. Embora este local deva ficar vazio, ele está cheio. Portanto, o trabalhador de depósito imediatamente faz uma contagem pontual deste local.

### <a name="do-cycle-counting-work-for-scenario-3"></a>Fazer o trabalho de contagem cíclica para o cenário 3

Siga estas etapas para fazer o trabalho de contagem cíclica no aplicativo móvel Warehouse Management.

1. Entre no aplicativo móvel Warehouse Management como o usuário de trabalho que você configurou na seção [Preparar dados de demonstração para os cenários](#prepare-demo-data) no início deste artigo. Para o exemplo deste artigo, o usuário se chama *Julia Funderburk* e está configurado para o depósito *61*. (Os dados de demonstração da USMF devem permitir que você entre como o usuário de trabalho inserindo *61* como a ID de usuário e *1* como a senha.)
1. No menu principal, selecione **Estoque**.
1. No menu **Estoque**, selecione **Contagem pontual**.
1. Selecione o campo **Local**, insira *01A02R2S1B* e selecione **OK** (o botão de marca de verificação).

    O sistema detecta que o local está vazio no Supply Chain Management.

1. Selecione **Adicionar LP ou item**.
1. Selecione o campo **Item**, insira *L0101* e selecione **OK** (o botão de marca de verificação).
1. Selecione o campo **Placa de licença**, insira *LP\_BULK\_06\_01* e selecione **OK** (o botão de marca de verificação).
1. Selecione o campo **Qtd**, insira *9* e selecione **OK** (o botão de marca de verificação).

    Como o sistema detecta que a placa de licença especificada já está disponível em outro local no Supply Chain Management, essa placa de licença será movida para o local atual. Portanto, o sistema solicita que você confirme a movimentação.

1. Selecione o botão **OK** (o botão de marca de seleção).

### <a name="review-the-cycle-counting-differences-for-scenario-3"></a>Revise as diferenças de contagem cíclica para o cenário 3

Siga estas etapas para revisar os resultados de contagem.

1. Retorne ao Supply Chain Management.
1. Acesse **Gerenciamento de depósito \> Comum \> Detalhes do trabalho**.
1. Marque a caixa de seleção **Mostrar fechado** na parte superior da grade.
1. Defina o filtro para a coluna **Tipo de ordem de serviço** como *Movimentação de estoque*.

    O sistema detectou automaticamente essa contagem como uma movimentação de estoque. Essa movimentação é permitida porque a opção **Permitir movimentações da placa de licença durante a contagem cíclica** está definida como *Sim* para o depósito *61* na página **Depósitos**.

## <a name="scenario-4-define-cycle-count-thresholds"></a>Cenário 4: Definir limites de contagem cíclica

Uma forma de criar um trabalho de contagem cíclica é usar limites. Um limite de contagem cíclica indica a quantidade ou o limite da porcentagem de itens de estoque. O trabalho de contagem cíclica é criado automaticamente quando o limite é atingido.

Por exemplo, há 60 itens em um local com um limite de contagem cíclica de 40. Durante uma transação de ordem de venda, 25 itens serão separados no local e colocados no local de preparo. Como a nova contagem de itens de 35 é menor do que a quantidade limite, o trabalho de contagem cíclica é criado automaticamente para o local.

Siga estas etapas para configurar os limites de contagem cíclica.

1. Acesse **Gerenciamento de depósito \> Configuração \> Contagem cíclica \> Limites de contagem cíclica**.
1. No Painel de Ação, selecione **Novo** para criar um limite e defina os seguintes valores:

    - **ID do limite de contagem cíclica:** *L0101*
    - **Descrição:** *Limite L0101*
    - **Quantidade limite:** *2*
    - **Unidade:** *ea*
    - **Limite de capacidade com base na porcentagem:** *0,00*
    - **Tipo de limite de contagem cíclica:** *quantidade*
    - **Processar contagem cíclica imediatamente:** *Sim*
    - **Dias entre a contagem cíclica:** *1*
    - **ID do pool de trabalho:** *CycleCount*

1. No Painel de Ações, selecione **Selecionar itens**.
1. Na caixa de diálogo de editor de consultas, na guia **Intervalo**, localize a linha na qual o campo **Campo** está definido como *Número do item*. Defina o campo **Critérios** dessa linha como *L0101*.
1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.

    Você definiu agora um limite de contagem cíclica para o item *L0101*.

A contagem cíclica agora será criada para o item *L0101* em qualquer local se a quantidade disponível for menor que 2 e se a data da última contagem cíclica para o local não for hoje.

## <a name="scenario-5-define-cycle-count-plans"></a>Cenário 5: Definir planos de contagem cíclica

Os planos de contagem cíclica permitem automatizar a criação do trabalho de contagem cíclica. Você pode configurar cada plano de contagem cíclica com itens específicos e consultas de localização. Quando o trabalho em lotes for executado, ele criará um trabalho de contagem cíclica para todos os locais que corresponderem aos critérios de item e de local (até o número máximo de contagens especificado para o plano). Quando o trabalho de contagem cíclica é criado, a linha de trabalho de contagem inclui informações sobre o local que deve ser contado. O estoque disponível associado a esse local não está bloqueado. Portanto, ele está disponível para reserva e processamento de saída, mesmo que exista um trabalho de contagem aberta.

Siga estas etapas para configurar um plano de contagem cíclica.

1. Acesse **Gerenciamento de depósito \> Configuração \> Contagem cíclica \> Planos de contagem cíclica**.
1. No Painel de Ações, selecione **Novo** para adicionar uma linha à grade e defina os seguintes valores:

    - **ID do plano de contagem cíclica:** *BULK06*
    - **Descrição:** *Contagem da localização para BULK06*
    - **ID do pool de trabalho:** *CycleCount*
    - **Número máximo de contagens cíclicas:** *10*
    - **Dias entre a contagem cíclica:** *10*
    - **Locais vazios:** *Excluir vazios*
    - **Modelo de trabalho:** Deixar este campo em branco.

1. No Painel de Ações, selecione **Selecionar locais**.
1. Uma caixa de diálogo do editor de consultas padrão é exibida. Na guia **Intervalo**, adicione uma linha e defina os seguintes valores:

    - **Tabela:** *Localizações*
    - **Campo:** *ID da zona*
    - **Critérios:** *BULK06*

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. No Painel de Ação, selecione **Processar plano de contagem cíclica**.
1. Na caixa de diálogo **Planos de contagem cíclica**, na Guia Rápida **Executar em segundo plano**, defina a opção **Processamento em lotes** como *Sim*.
1. Selecione **Recorrência**.
1. Na caixa de diálogo **Definir recorrência**, configure o trabalho em lotes para que ele comece imediatamente e seja executado a cada minuto e, portanto, não haja data de término.
1. Selecione **OK** para fechar a caixa de diálogo **Definir recorrência**.
1. Selecione **OK** para fechar a caixa de diálogo **Planos de contagem cíclica**.

    Uma mensagem informa que o trabalho foi adicionado à fila de lotes.

1. Acesse **Gerenciamento de depósito \> Comum \> Agendamento de contagem cíclica**. O plano começa imediatamente e cria um trabalho de contagem. Como o trabalho de contagem não foi concluído, o campo **Status** é definido como *Em andamento*. Após um minuto, o valor na coluna **Total de contagens cíclicas** é alterado para *1*.

    > [!NOTE]
    > O trabalho de contagem cíclica não será criado se o número de dias desde a última contagem cíclica for menor que o valor definido para o campo **Dias entre a contagem cíclica** do plano de contagem cíclica. Por exemplo, se o campo **Dias entre a contagem cíclica** for *5*, o trabalho de contagem cíclica será criado a cada cinco dias. No entanto, se o trabalho de contagem cíclica for processado no dia três, o trabalho seguinte de contagem cíclica será criado cinco dias após a última contagem cíclica tiver sido processada, no dia oito.

1. No Painel de Ação, selecione **Trabalho** para exibir o trabalho de contagem que foi criado.
