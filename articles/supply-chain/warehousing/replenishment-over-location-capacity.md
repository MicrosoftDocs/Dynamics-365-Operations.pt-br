---
title: Reabastecimento sobre a capacidade do local
description: Este tópico fornece informações sobre o recurso Reabastecimento sobre a capacidade do local. Este recurso habilita a criação de todo o trabalho de reabastecimento que será necessário para o dia e gerencia a disponibilidade desse trabalho de reabastecimento para garantir que o local de separação não fique sem estoque nem acima da capacidade.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 8e9ae16fea892d1d6b6a6b5d06137576623e7f5b
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016599"
---
# <a name="replenishment-over-location-capacity"></a>Reabastecimento sobre a capacidade do local

[!include [banner](../includes/banner.md)]

Alguns depósitos de alto volume ou de espaço restrito devem enviar mais quantidade de um item em um dia do que caiba no local de separação. O recurso *Reabastecimento sobre a capacidade do local* habilita a criação de todo o trabalho de reabastecimento que será necessário para o dia e gerencia a disponibilidade desse trabalho de reabastecimento para garantir que o local de separação não fique sem estoque nem acima da capacidade.

O recurso permite que mais trabalho de reabastecimento seja criado do que caberá em um local e bloqueia a conclusão do trabalho de reabastecimento quando o local está cheio. À medida que o estoque no local de separação fica abaixo de um limite configurável, mais trabalho de reabastecimento é disponibilizado.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>Ativar o recurso Reabastecimento sobre a capacidade do local

Para disponibilizar este recurso, ative os seguintes recursos no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (nesta ordem):

1. Bloqueio de trabalho em toda a organização
1. Reabastecimento sobre a capacidade do local

## <a name="set-up-the-feature-for-the-example-scenario"></a>Configurar o recurso para o cenário de exemplo

Esta seção fornece diretrizes e um exemplo que mostra como configurar este recurso e preparar dados de exemplo para o cenário de exemplo fornecido mais adiante neste tópico.

### <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para trabalhar com o [cenário de exemplo](#example-scenario) usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

### <a name="location-profile"></a>Perfil de localização

Habilite a funcionalidade de reabastecimento sobre capacidade no perfil de localização.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localizações**.
1. No painel esquerdo, selecione **PICK-06**.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Reabastecimento** , defina os seguintes valores:

    - **Exceder Capacidade de Localização:** *Sim*

        Quando esta opção estiver habilitada, a capacidade máxima do local será permitida a ser excedida por trabalhos de reabastecimento. Isso também habilita outros campos na FastTab **Reabastecimento**.

    - **Tipo de limite de disponibilidade de trabalho:** *Quantidade*

        Este campo define o método usado para determinar quando mais trabalho deve ser liberado. Você pode liberar por quantidade ou uma porcentagem:

        - *Porcentagem* – selecione esta opção para usar a capacidade de porcentagem baseada em limites de estoque ou de volumetria. A seleção desta opção habilita o campo **Porcentagem de excesso** e desabilita os dois campos relacionados à quantidade, **Quantidade de excesso** e **Unidade de excesso**.

            Você poderá usar esta opção se os locais de separação usarem volumetria.

            Se esta opção estiver selecionada, defina o campo **Porcentagem de excesso** com a porcentagem na qual mais trabalho de reabastecimento será disponibilizado.

        - *Quantidade* – selecione esta opção para usar um valor de quantidade específico. A seleção desta opção desabilita o campo **Porcentagem de excesso** e habilita os campos **Quantidade de excesso** e **Unidade de excesso**.

            Use esta opção quando não estiver usando volumetria para os locais reabastecidos ou quando houver quantidades consistentes em que você deseja que mais estoque seja trazido para o local.

           Se esta opção estiver selecionada, defina os campos **Quantidade de excesso** e **Unidade de excesso** para a quantidade e a unidade em que mais trabalho de reabastecimento será disponibilizado.

    - **Quantidade de excesso:** *0,65*

        Este campo define a quantidade em que ocorre o excesso de localização.

        O trabalho será disponibilizado sempre que a soma da quantidade disponível no local e da quantidade de trabalho estiver abaixo desse valor. Qualquer trabalho de reabastecimento acima desse valor será bloqueado e deverá ser desbloqueado manualmente.

        Os limites do estoque de localização são considerados quando a quantidade do trabalho é calculada.

    - **Unidade de excesso:** *PL*

        Este campo define a unidade associada à quantidade de excesso.

        Nesse caso, mais trabalho de reabastecimento será disponibilizado quando o local for reduzido a 0,65 palete (PL).

    - **Porcentagem de excesso**

        Este campo define a porcentagem em que ocorre o excesso de localização.

        O trabalho será disponibilizado sempre que a soma da quantidade disponível no local e da quantidade de trabalho estiver abaixo dessa porcentagem. Qualquer porcentagem de quantidade de trabalho de reabastecimento acima desse valor será bloqueada e deverá ser desbloqueada manualmente.

        Os limites do estoque de localização são considerados quando a porcentagem da quantidade de trabalho é calculada. Se nenhum limite de estoque de localização for definido, a porcentagem da quantidade de trabalho será calculada por volume se as restrições de volume forem definidas para o perfil do local.

> [!IMPORTANT]
> Se você estiver usando os dados de demonstração da entidade legal **USMF** e previamente ativou o recurso *Posicionamento da placa de licença de localização* , desative a configuração **Habilitar posicionamento da placa de licença** para o perfil de localização **BULK-06** para concluir as etapas móveis no cenário de exemplo.

### <a name="wave-step-code"></a>Código da etapa da onda

> [!NOTE]
> Para configurar um código de etapa de onda, conforme descrito aqui, você deve primeiro usar o [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar o recurso denominado *Código da etapa da onda em toda a organização*.

1. Vá para **Gerenciamento de Depósito \> Configuração \> Ondas \> Códigos da etapa da onda**.
1. Selecione **Novo** e defina os seguintes valores:

    - **Código da etapa da onda:** *Reabastecimento*
    - **Descrição da etapa da onda:** *Reabastecimento*
    - **Tipo de etapa de onda:** *Reabastecimento*

1. Selecione **Salvar**.

### <a name="replenishment-template"></a>Modelo de reabastecimento

Modelos de reabastecimento são um conjunto de regras que controlam como e quando um local é reabastecido.

1. Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**.
1. No Painel de Ações, selecione **Editar**.
1. Na seção **Visão geral** , selecione a linha em que o campo **Modelo de reabastecimento** está definido como *Reabastecimento de demanda*.
1. Defina os seguintes valores:

    - **Código da etapa da onda:** *Reabastecimento*
    - **Permitir que a demanda de onda use quantidades não reservadas:** *Sim*

1. Selecione **Salvar**.

### <a name="wave-template"></a>Modelo da onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. No painel esquerdo, defina o campo **Tipo de modelo de onda** como *Remessa*.
1. Selecione o modelo **Remessa 61** na lista.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Geral** , defina a opção **Automatizar liberação do trabalho de reabastecimento** como *Sim*.

    Defina esta opção como *Sim* para criar o trabalho de reabastecimento baseado em demanda e liberá-lo automaticamente. Você deve adicionar o método de onda de reabastecimento ao modelo de onda e criar um modelo de reabastecimento do tipo **Demanda da onda**. Configure um modelo de reabastecimento na página **Modelos de reabastecimento**. Para configurar um modelo de reabastecimento, você deve adicionar o método de reabastecimento ao modelo de onda.

1. Na FastTab **Métodos** , na coluna **Métodos selecionados** , localize a seguinte linha:

    - **Nome do método:** *reabastecimento*
    - **Nome:** *Reabastecimento*

1. Defina o campo **Código da etapa da onda** para esta linha como *Reabastecimento*.
1. Selecione **Salvar**.

## <a name="example-scenario"></a>Cenário de exemplo

Após disponibilizar todos os dados de exemplo descritos anteriormente e configurá-los, você poderá trabalhar neste cenário para testar o recurso *Reabastecimento sobre a capacidade do local*. Os valores que são mostrados neste cenário pressupõem que você está trabalhando com os dados de demonstração padrão, que você selecionou a entidade legal **USMF** e preparou os registros de exemplo descritos anteriormente neste tópico. Esse cenário também serve como exemplo para mostrar como o recurso pode ser usado em uma configuração de produção.

### <a name="create-replenishment-work"></a>Criar trabalho de reabastecimento

#### <a name="create-sales-order-1"></a>Criar ordem de venda 1

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo** para abrir uma caixa de diálogo para criar uma nova ordem de venda.
1. Na caixa de diálogo , defina os seguintes valores:

    - **Conta de cliente:** *US-007*
    - **Depósito:** *61*

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ela inclui uma nova linha vazia na FastTab **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *T0100*
    - **Quantidade:** *40*

1. Na FastTab **Linhas da ordem de venda** , selecione **Estoque \> Reserva**.
1. Na página **Reserva** , selecione **Reservar lote**.
1. Feche a página.
1. No Painel de Ações, na guia **Depósito** , selecione **Liberar para o depósito**.

    Você recebe mensagens informativas que mostram IDs da onda e da remessa que foram criadas. Uma onda de reabastecimento também é criada.

    Você também receberá uma mensagem de aviso afirmando "não é possível desbloquear a ID de trabalho XXXX porque existe trabalho de reabastecimento não concluído".

#### <a name="create-sales-order-2"></a>Criar ordem de venda 2

1. Na página **Todas as ordens de venda** , no Painel de Ações, selecione **Novo** para abrir uma caixa de diálogo para criar uma nova ordem de venda.
1. Na caixa de diálogo , defina o seguinte valor:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *61*

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ela inclui uma nova linha vazia na FastTab **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *T0100*
    - **Quantidade:** *60*

1. Na FastTab **Linhas da ordem de venda** , selecione **Estoque \> Reserva**.
1. Na página **Reserva** , selecione **Reservar lote**.
1. Feche a página.
1. No Painel de Ações, na guia **Depósito** , selecione **Liberar para o depósito**.

    Você recebe mensagens informativas que mostram IDs da onda e da remessa que foram criadas. Uma onda de reabastecimento também é criada.

    Você também receberá uma mensagem de aviso afirmando "não é possível desbloquear a ID de trabalho XXXX porque existe trabalho de reabastecimento não concluído".

#### <a name="create-sales-order-3"></a>Criar ordem de venda 3

1. Na página **Todas as ordens de venda** , no Painel de Ações, selecione **Novo** para abrir uma caixa de diálogo para criar uma nova ordem de venda.
1. Na caixa de diálogo , defina os seguintes valores:

    - **Conta de cliente:** *US-004*
    - **Depósito:** *61*

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ela inclui uma nova linha vazia na FastTab **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *T0100*
    - **Quantidade:** *30*

1. Na FastTab **Linhas da ordem de venda** , selecione **Estoque \> Reserva**.
1. Na página **Reserva** , selecione **Reservar lote**.
1. Feche a página.
1. No Painel de Ações, na guia **Depósito** , selecione **Liberar para o depósito**.

    Você recebe mensagens informativas que mostram IDs da onda e da remessa que foram criadas. Uma onda de reabastecimento também é criada.

    Você também receberá uma mensagem de aviso afirmando "não é possível desbloquear a ID de trabalho XXXX porque existe trabalho de reabastecimento não concluído".

#### <a name="view-work-details"></a>Exibir detalhes do trabalho

1. Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Na seção **Visão geral** , filtre a coluna **Depósito** para o depósito *61*.
1. Note que foram criadas sete IDs de trabalho para as três ordens de venda de demanda.

    - Três das sete IDs de trabalho têm um **Tipo de ordem de trabalho** com valor de *Reabastecimento* e quatro têm um **Tipo de ordem de trabalho** com valor de *Ordens de venda*.
    - Todas as três IDs de trabalho com **Tipo de ordem de trabalho** com valor de *Reabastecimento* têm as mesmas localizações de *Separação* e *Colocação* na seção **Linhas** :

        - **Separar:** *02A01R5S1B*
        - **Colocar:** *06A01R2S1B*

    - Duas IDs de trabalho foram criadas para a ordem de venda 1.

1. Anote as IDs de trabalho das ordens de venda.

Dependendo das quantidades disponíveis, as quantidades de trabalho criadas podem variar um pouco. No entanto, em geral, os cabeçalhos de trabalho criados devem corresponder a este exemplo de cenário.

#### <a name="on-hand-inventory-license-plate-id"></a>ID da placa de licença de estoque disponível

Posteriormente neste cenário, você usará o aplicativo de depósito (ou um emulador), no qual deve identificar a placa de licença para preencher os cenários de separação e reabastecimento.

Para localizar as IDs de placa de licença que serão necessárias posteriormente, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível**.
1. Selecione o botão **Mostrar filtros** para abrir o painel de filtros.
1. Insira os critérios de filtragem a seguir para obter as placas de licença do cenário. Use o filtro *começa com*.

    - **Número de item:** *T0100*
    - **Depósito:** *61*

1. Selecione **Aplicar**.
1. No Painel de Ação, selecione **Dimensões**.
1. Na caixa de diálogo **Exibição de dimensões** , na seção **Dimensões de Armazenamento** , selecione todos os valores.
1. Na seção **Transações** , selecione **Número do item** e **Quantidade \<\> 0**.
1. Quando terminar, selecione **OK** para fechar a caixa de diálogo.
1. A grade **Disponível** mostra os números das placas de licença para o item *T0100* em cada local. Anote a placa da licença que está em cada local, pois essas informações serão necessárias posteriormente.
1. Feche a página.

### <a name="process-steps"></a>Etapa do processo

Você executará o reabastecimento de localização de depósito para as duas primeiras IDs de trabalho. O trabalho no terceiro trabalho de reabastecimento será bloqueado até que o nível de estoque no local de separação fique abaixo do limite.

#### <a name="replenishment"></a>Reabastecimento

1. Entre no aplicativo do depósito como um usuário no depósito *61*. (Insira *61* como a ID do usuário e *1* como a senha.)
1. Vá para **Estoque \> Reabastecimento**.

    Você será solicitado a concluir o primeiro trabalho de reabastecimento. O número do item, a quantidade e o local de separação são mostrados.

1. No campo **LP** , insira o número da placa de licença para o item na localização que é mostrada.
1. Selecione o botão **OK** (símbolo de marca de seleção).

    O sistema gera um número de placa de licença de destino para a nova placa de licença para o item separado.

1. Selecione **OK** para confirmar o valor.

    O trabalho de colocação mostrado orienta o usuário a colocar a placa de licença de destino no local de reabastecimento. O local de *colocação* deve ser **06A01R2S1B**.

1. Confirme os detalhes de colocação e selecione **OK**.

    Você recebe uma mensagem "Trabalho Concluído" e os detalhes da próxima tarefa de separação de reabastecimento são mostrados: número do item, quantidade e local de separação. O local de separação será o mesmo que o primeiro local de reabastecimento. Portanto, a placa de licença terá a mesma ID da placa de licença usada para a primeira tarefa de reabastecimento.

1. Repita as etapas anteriores para concluir o trabalho de reabastecimento para a segunda tarefa de trabalho. A quantidade e a placa de licença de destino serão diferentes da quantidade e da placa da licença de destino para a primeira tarefa de trabalho.

Depois que o segundo trabalho de reabastecimento for concluído, você receberá uma mensagem "Trabalho Concluído". O dispositivo móvel também informa que não há trabalho disponível, embora algum trabalho de reabastecimento permaneça. Esse comportamento ocorre porque o trabalho de reabastecimento tem um status de disponibilidade *Retido* e, portanto, é marcado como **Bloqueado**.

O status *Retido* foi disparado porque o perfil de localização do local de separação ao qual o trabalho é atribuído tem um valor **Quantidade de excesso** de *0,65 PL*. As duas tarefas de trabalho de reabastecimento anteriores preencheram o local quase no limite de excesso do item *T0100*. (A conversão de unidades do item é *1 PL = 100 cada*.) Portanto, o trabalho de reabastecimento restante levaria o local a ultrapassar o limite de excesso.

Até que o estoque suficiente seja separado do local para deixá-lo abaixo do limite de liberação de trabalho no item de menu do dispositivo móvel, este trabalho de reabastecimento permanecerá bloqueado.

#### <a name="sales-order-pick"></a>Separação da ordem de venda

Antes da conclusão da tarefa de trabalho de reabastecimento restante, o estoque do local de separação deve ser esgotado até um nível em que o trabalho de reabastecimento restante possa ser desbloqueado. Em outras palavras, a soma da quantidade de estoque disponível no local e a quantidade de reabastecimento não pode exceder o valor **Quantidade de excesso**. Quando essa soma for menor do que a quantidade de excesso, o trabalho de reabastecimento restante será desbloqueado.

1. Entre no aplicativo do depósito como um usuário no depósito *61*. (Insira *61* como a ID do usuário e *1* como a senha.)
1. Vá para **Saída \> Separação de Venda**.
1. Insira a primeira ID de trabalho para a ordem de venda 1.

    Consulte as IDs de trabalho para ordens de venda que você anotou, anteriormente, na página **Detalhes do trabalho**. A ID de trabalho inserida aqui gerará um trabalho de separação para uma quantidade de 10 cada de dois locais separados.

1. Selecione **OK**.

    A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção para a primeira localização.

1. No campo **LP** , insira o número da placa de licença para o item na localização que é mostrada.
1. Selecione o botão **OK** (símbolo de marca de seleção).

    A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção para a próxima localização.

1. No campo **LP** , insira o número da placa de licença para o item na localização que é mostrada.
1. Selecione o botão **OK** (símbolo de marca de seleção).

    A página **Ordens de venda: colocar** orienta a armazenar os trabalhos de separação concluídos no local de preparo de saída.

1. Selecione **OK**.

    Você receberá uma mensagem "Trabalho Concluído".

1. Insira a segunda ID de trabalho para a ordem de venda 1.

    Há apenas uma tarefa de seleção para esta ID de trabalho.

1. Selecione **OK**.

    A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção.

1. No campo **LP** , insira o número da placa de licença para o item na localização que é mostrada.

    A placa de licença especificada será uma das placas de licença geradas pelo sistema das tarefas de trabalho de reabastecimento. Para verificar se você captura a ID da placa de licença correta, verifique o estoque na página **Lista disponível** para o item, o local e a quantidade.

1. Selecione o botão **OK** (símbolo de marca de seleção).
1. Confirme as instruções da tarefa de colocação para o local de preparo de saída.
1. Selecione **OK**.

    Você receberá uma mensagem "Trabalho Concluído".

A ordem de venda 2 é bloqueada para separação porque a tarefa de reabastecimento à qual ela está vinculada não foi concluída. No momento, ainda há uma quantidade de 30 cada no local de separação e a quantidade de reabastecimento para a ordem de venda 2 é de 60 cada. A soma do estoque disponível e do estoque de reabastecimento (90 cada) excede a quantidade de excesso de 0,65 PL (ou 65 cada). Para que o trabalho de reabastecimento possa ser concluído, a ordem de venda 3 deve ser separada.

1. Insira a ID de trabalho da ordem de venda 3.

    Há apenas uma tarefa de seleção para esta ID de trabalho.

1. Selecione **OK**.

    A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção.

1. No campo **LP** , insira o número da placa de licença para o item na localização que é mostrada.

    A placa de licença especificada será uma das placas de licença geradas pelo sistema das tarefas de trabalho de reabastecimento. Para verificar se você captura a ID da placa de licença correta, verifique o estoque na página **Lista disponível** para o item, o local e a quantidade.

1. Selecione o botão **OK** (símbolo de marca de seleção).
1. Confirme as instruções da tarefa de colocação para o local de preparo de saída.
1. Selecione **OK**.

    Você receberá uma mensagem "Trabalho Concluído".

Assim que a soma da quantidade disponível no local de separação e a quantidade de reabastecimento estiver abaixo do limite, você poderá processar o trabalho de reabastecimento restante.

Retorne à página **Detalhes do trabalho** e observe que a disponibilidade do trabalho de reabastecimento para a parte final do reabastecimento (para a ordem de venda 2) está *Aberta* , pois há espaço suficiente no local para aceitar o reabastecimento.

Agora você pode processar este trabalho de reabastecimento por meio do dispositivo móvel.

1. Vá para **Estoque \> Reabastecimento**.

    Você será solicitado a concluir o trabalho restante de reabastecimento. O número do item, a quantidade e o local de separação são mostrados.

1. No campo **LP** , insira o número da placa de licença para o item na localização que é mostrada.
1. Selecione o botão **OK** (símbolo de marca de seleção).

    O sistema gera um número de placa de licença de destino para a nova placa de licença para o item separado.

1. Selecione **OK** para confirmar o valor.

    O trabalho de colocação mostrado orienta o usuário a colocar a placa de licença de destino no local de reabastecimento. O local de *colocação* deve ser **06A01R2S1B**.

1. Confirme os detalhes de colocação e selecione **OK**.

    Você recebe mensagens "Trabalho Concluído" e "Nenhum Trabalho Disponível".

Agora, você pode separar a ordem de venda 2. Ele se tornou desbloqueada quando o trabalho de reabastecimento vinculado à ordem de venda foi concluído.

1. Insira a ID de trabalho da ordem de venda 2.

    Há apenas uma tarefa de seleção para esta ID de trabalho.

1. Selecione **OK**.

    A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção.

1. No campo **LP** , insira o número da placa de licença para o item na localização que é mostrada.

    A placa de licença especificada será a placa de licença gerada pelo sistema da tarefa de trabalho de reabastecimento. Para verificar se você captura a ID da placa de licença correta, verifique o estoque na página **Lista disponível** para o item, o local e a quantidade.

1. Selecione o botão **OK** (símbolo de marca de seleção).
1. Confirme as instruções da tarefa de colocação para o local de preparo de saída.
1. Selecione **OK**.

    Você receberá uma mensagem "Trabalho Concluído".

## <a name="notes-and-tips"></a>Observações e dicas

- Essa funcionalidade funciona com todos os tipos de reabastecimento: demanda de onda, mín./máx., demanda de carga e slots.
- Se desejar, você poderá substituir manualmente a disponibilidade de trabalho de reabastecimento para cada cabeçalho de trabalho da página **Detalhes do trabalho**.
- Quando o sistema define a disponibilidade do trabalho de reabastecimento, ele considera qualquer estoque que já esteja no local antes da conclusão de qualquer trabalho
- Cada item de trabalho da ordem de venda é vinculado a um trabalho de reabastecimento específico. Não há funcionalidade de disponibilidade de trabalho de vendas correspondente.
