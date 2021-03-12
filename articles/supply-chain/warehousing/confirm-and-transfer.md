---
title: Confirmar e transferir
description: Este tópico explica como usar o recurso Confirmar e transferir, que permite aos usuários enviar cargas do depósito antes de concluir todo o trabalho associado a elas.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate,WHSWorkTemplateTable,WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6ccfbe30e9d4a0fc4580c7036d222bfca9203a21
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996317"
---
# <a name="confirm-and-transfer"></a>Confirmar e transferir

[!include [banner](../includes/banner.md)]

O recurso *Confirmar e transferir* permite aos usuários enviar cargas do depósito antes de concluir todo o trabalho associado a elas. Quando é recebida uma remessa que inclui linhas de carga que não foram totalmente separadas, o usuário que faz a confirmação é solicitado a dividir as quantidades restantes em uma nova carga ou cancelar as quantidades incompletas.

Os sistemas que estão configurados para permitir a divisão de carga dão suporte a cenários em que cargas planejadas e parcialmente carregadas devem ser adaptadas devido a circunstâncias novas ou variáveis.

O cliente inclui a lógica que permite que uma carga parcialmente carregada seja fechada e confirmada como remetida. Todas as remessas e linhas de carga restantes (inclusive quantidades de linha inteira ou parcial) são convertidas em uma carga e em uma remessa recém-criadas, se essa substituição for necessária e a configuração permitir. Novas remessas e cargas são criadas automaticamente com base nos critérios iniciais para criação de remessa e carga, e os principais atributos permanecem inalterados. Também há uma opção para cancelar automaticamente as quantidades restantes se uma ordem de trabalho ainda não tiver sido criada e o usuário considerar esse cancelamento necessário.

Essa funcionalidade oferece suporte a cenários em que a carga total não cabe em um único caminhão ou quando parte da carga deve sair do depósito antes que o restante da carga esteja pronta para remessa. Nesses cenários, os produtos restantes podem ser transferidos para uma nova carga e, portanto, para um novo caminhão. Como este recurso pode ser usado com cargas que, de outra forma, devem exigir remessa de carga completa, ele oferece flexibilidade extra para os gerenciadores de transporte resolverem cenários imprevistos ou diferentes do padrão.

Quando uma carga é dividida, o recurso *Confirmar e transferir* executa as seguintes ações:

- Novas cargas e remessas são criadas conforme a necessidade. Cada carga ou remessa terá a maioria dos mesmos atributos que a carga ou a remessa original. A exceção é o status da carga, que será recalculado com base no status do trabalho.
- O usuário é informado de que uma nova carga foi criada. O usuário também é notificado sobre a ID da nova carga.
- As linhas de carga, os cabeçalhos de trabalho e as linhas de trabalho que foram divididos são atualizados com as novas informações de carga e remessa.
- Se uma remessa inteira for dividida, ela será mantida e somente as referências de carga serão atualizadas. Se for necessário dividir a remessa, uma nova remessa será criada.

Quando as quantidades restantes são canceladas, todas as quantidades de linha de carga que não foram separadas e que não têm trabalho não cancelado associado a elas são removidas da carga. Se houver algum trabalho em andamento, o usuário só poderá dividir a carga. Não é possível cancelar as quantidades restantes.

Você só pode dividir cargas que atendam a todos os seguintes critérios:

- Uma ou mais linhas de carga têm quantidades separadas.
- O status da carga é menor do que o carregado.
- Não há dados de linha de carga. (Esses dados são criados por meio da consolidação da placa de licença no local de preparo, e o recurso *Confirmar e transferir* não oferece suporte à consolidação de placas de licença.)
- No momento, não há estoque aguardando para ser embalado em um local de embalagem. (O recurso *Confirmar e transferir* não oferece suporte para estoque que foi separado para a estação de embalagem, mas que ainda não foi embalado.)

> [!NOTE]
> Essa funcionalidade é diferente da funcionalidade de carga de transporte, que deve ser usada em depósitos que nunca podem planejar e criar cargas antes da separação, mas que, em vez disso, carregam o espaço de transporte disponível depois que a separação é finalizada.
>
> Use o recurso *Confirmar e transferir* em situações nas quais as cargas normalmente são planejadas e criadas com antecedência, mas em que, às vezes, ocorrem exceções quando a carga não cabe no transporte disponível (em um caminhão, por exemplo).

## <a name="turn-on-confirm-and-transfer"></a>Habilitar confirmar e transferir

Para que você possa usar o recurso *Confirmar e transferir*, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Confirmar e transferir*

## <a name="set-up-confirm-and-transfer"></a>Configurar confirmar e transferir

Para usar o recurso *Confirmar e transferir*, você deve ativá-lo em cada modelo de carga relevante. Além disso, dependendo de suas necessidades, convém preparar seus modelos de trabalho para oferecer suporte ao recurso. Se você quiser trabalhar no cenário de exemplo apresentado mais adiante neste tópico, configure o sistema conforme descrito nesta seção. (Esse cenário baseia-se em dados de demonstração da **USMF**.)

### <a name="prepare-your-load-templates"></a>Preparar os modelos de carga

1. Vá para **Gerenciamento de depósito \> Configuração \> Carga \> Modelos de carga**.
1. No Painel de Ação, selecione **Editar** para colocar a página no modo de edição.
1. Marque a caixa de seleção **Permitir divisão de carga durante confirmação de remessa** para cada modelo existente no qual você deseja ativar o recurso. Se preferir, selecione **Novo** para criar um novo modelo e configurá-lo conforme necessário. Todas as cargas criadas com esse modelo herdarão esta funcionalidade. (Se estiver trabalhando com os dados de demonstração da **USMF**, ative o recurso para o modelo de carga **Contêiner 20'**.)

### <a name="prepare-your-work-templates"></a>Preparar os modelos de trabalho

Esta configuração não é necessária em todas as situações. O exemplo mostrado aqui garante que o trabalho possa ser dividido por remessa para dar suporte ao cenário de exemplo apresentado mais adiante neste tópico. Também há outras maneiras de conseguir esse resultado.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Na grade na parte superior da página, selecione um modelo de trabalho existente no qual você deseja configurar o recurso *Confirmar e transferir*. (Se você estiver trabalhando com os dados de demonstração da **USMF**, selecione o modelo de trabalho **51 Estágio de separação**). Outra opção é criar um novo modelo de trabalho.
1. No Painel de Ação, selecione **Editar consulta** para abrir a caixa de diálogo **Vendas**.
1. Na caixa de diálogo **Vendas**, na guia **Classificação**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tabela:** *Transações de trabalho temporário*
    - **Tabela derivada:** *Transações de trabalho temporário*
    - **Campo:** *ID da Remessa*
    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para salvar suas configurações e fechar a caixa de diálogo **Vendas**.
1. Se você receber uma mensagem informando que o agrupamento será redefinido, selecione **Sim** para continuar.
1. Na grade na parte superior da página **Modelos de trabalho**, selecione o modelo que você acabou de editar e, no Painel de Ação, selecione **Quebras de Cabeçalho de Trabalho**.
1. No Painel de Ação, selecione **Editar** para colocar a página no modo de edição.
1. Na grade, defina os seguintes valores:

    - **Nome da tabela:** *Transações de trabalho temporário*
    - **Nome do campo:** *ID da Remessa*
    - **Agrupar por este campo:** Marque esta caixa de seleção.

1. No Painel de ações, selecione **Salvar**.
1. Feche a página.

## <a name="scenario"></a>Cenário

Este cenário mostra um exemplo no qual o processo de separação ainda não foi concluído, mas os itens separados até agora devem ser carregados em um caminhão e remetidos mesmo assim. Portanto, o usuário pode dividir as linhas de carga não separadas em uma nova carga. Todos os relacionamentos de dados serão atualizados automaticamente.

> [!NOTE]
> Os valores específicos descritos neste cenário são baseados nos dados de demonstração da **USMF**. É recomendável usar esses dados de demonstração enquanto você estiver demonstrando ou aprendendo como usar o recurso. Se você não estiver usando os dados de demonstração da **USMF**, substitua seus valores conforme necessário.

### <a name="step-1-create-a-load-that-has-multiple-load-lines"></a>Etapa 1: Criar uma carga contendo várias linhas de carga

Para poder usar esta funcionalidade, você deve ter uma carga que contenha várias linhas de carga. Você também deve se certificar de que os locais de separação têm estoque suficiente para todos os itens nas ordens de venda que criará. Examine a configuração da diretiva de localização (**Gerenciamento de depósito \> Configuração \> Diretivas de localização**) e anote os locais de separação usados para separação de ordens de venda. Se tiver de ajustar o estoque, crie movimentações manuais, use o reabastecimento ou utilize qualquer outro fluxo.

Para criar uma carga de qualificação, primeiro crie três ordens de venda seguindo essas etapas.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ação, selecione **Novo** para abrir a caixa de diálogo **Criar ordem de venda**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores (no mínimo):

    - Na FastTab **Cliente**, defina o campo **Conta do cliente** como *US-004* (*Cave Wholesales*).
    - Na FastTab **Geral**, defina o campo **Depósito**, como *51*.

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo **Criar ordem de venda**.
1. A nova ordem de venda é aberta. Na grade **Linhas de ordem de venda**, adicione uma linha que tenha os seguintes valores:

    - **Número de item:** *M9200*
    - **Quantidade:** *40*
    - **Unidade:** *ea*

1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. No Painel de Ação, selecione **Reservar lote** para abrir a página **Reserva**.
1. Reserve o estoque na linha de venda e, depois, feche a página **Reserva**.
1. Repita as etapas de 1 a 4 para adicionar uma segunda ordem de venda para os mesmos cliente e depósito.
1. Adicione duas linhas de venda com os valores a seguir. Depois de adicionar cada linha, reserve estoque para elas, conforme descrito nas etapas de 6 a 8.

    - **Linha 1:** defina o campo **Número do item** como *M9200*, o campo **Quantidade** como *30* e o campo **Unidade** como *unidade*.
    - **Linha 2:** defina o campo **Número do item** como *M9201*, o campo **Quantidade** como *20* e o campo **Unidade** como *unidade*.

1. Repita as etapas de 1 a 4 para adicionar uma terceira ordem de venda para os mesmos cliente e depósito.
1. Adicione duas linhas de venda com os valores a seguir. Depois de adicionar cada linha, reserve estoque para elas, conforme descrito nas etapas de 6 a 8.

    - **Linha 1:** defina o campo **Número do item** como *M9201*, o campo **Quantidade** como *20* e o campo **Unidade** como *unidade*.
    - **Linha 2:** defina o campo **Número do item** como *M9202*, o campo **Quantidade** como *60* e o campo **Unidade** como *unidade*.

#### <a name="load-planning-workbench"></a>Bancada do planejamento de carga

A bancada de planejamento de carga usará a ID do modelo de carga para criar as remessas e liberar as linhas de ordem de venda para o depósito.

1. Vá para **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.
1. No campo **Depósito**, selecione *51*.

    Agora você irá montar a carga para as ordens de venda que acabou de criar.

1. Na guia **Linhas de venda**, na grade, selecione as linhas de venda para as novas ordens de venda.
1. No Painel de Ação, na guia **Oferta e demanda** , no grupo **Adicionar** , selecione **Para nova carga**.
1. Na caixa de diálogo **Atribuição de modelo de carga**, no campo **ID do modelo de carga**, selecione *Contêiner 20'*.
1. Selecione **OK**.
1. Na seção **Cargas** da página **Bancada de planejamento de carga**, na grade, encontre a ID da carga recém-criada para o depósito *51*. Role para a direita até ver a coluna **Permitir divisão de carga durante confirmação de remessa**. A caixa de seleção da sua carga deve ser marcada.
1. Selecione a carga.
1. No menu **Liberar** acima da grade, selecione **Liberar para o depósito** para criar o trabalho.
1. Na caixa de diálogo **Liberar carga para depósito**, verifique se a FastTab **Registros a serem incluídos** mostra a ID da carga.
1. Selecione **OK**.

    Você pode receber uma mensagem "Processando operação" enquanto o sistema cria as remessas e o trabalho.

1. Na seção **Cargas** da página **Bancada de planejamento de carga**, agora sua carga deve ter o status de carga *Na Onda*. Selecione a carga e, no menu **Informações relacionadas** acima da grade, selecione **Detalhes da onda** para ver as IDs de remessa que foram criadas. Quando terminar, feche a página **Ondas**.
1. Na seção **Cargas** da página **Bancada de planejamento de carga**, selecione a carga e, no menu **Informações relacionadas** acima da grade, selecione **Detalhes do trabalho** para exibir o trabalho que foi criado para as ordens de venda.
1. Tome nota das IDs de trabalho que foram criadas. Pode ser necessário rolar para a direita para ver o número da ordem de venda e a ID da remessa associados à ID do trabalho.

### <a name="step-2-set-up-the-execution-flow-for-mobile-devices"></a>Etapa 2: Configurar o fluxo de execução para dispositivos móveis

Para as tarefas em dispositivo móvel, o usuário deverá inserir informações, como a ID do trabalho ou a ID da placa de licença. Nos campos, essas informações normalmente são fornecidas para os usuários do depósito na forma de códigos de barras que são encontrados na documentação, na embalagem ou no rack. Para concluir as etapas do dispositivo móvel para cenários, você deve ter identificado as IDs de trabalho relativas às transações e as IDs de placa de licença para o item e a local nas transações.

1. Entre no dispositivo móvel usando uma ID de usuário e uma senha para o depósito *51*.
1. Selecione **Saída**.
1. Selecione **Separação de Venda**.
1. Você tem a opção de inserir a ID do trabalho ou a ID da placa de licença. Insira a ID do trabalho da primeira ordem de venda e, depois, selecione **Enter**.
1. No campo **Loc**, insira o local mostrado para confirmar o local de separação. Depois, selecione **Enter**.
1. No campo **LP**, insira a ID da placa de licença. A ID da placa de licença deve corresponder ao item, ao depósito e ao local do item que está sendo separado no local selecionado. Quando terminar, selecione **Enter**.
1. No campo **Item**, insira o número do item para confirmar o item que está sendo separado e, depois, selecione **Enter**.
1. No campo **Qtd.**, insira a quantidade do item que está sendo separado e, depois, selecione **Enter**.
1. No campo **LP de destino**, insira a ID da placa de licença de destino. As placas de licença de destino são definidas pelo usuário. Insira uma ID de placa de licença que você lembrará. É recomendável usar a data atual mais uma sequência de dois dígitos (AAMMDD\#\#) como formato, por exemplo, *19112301*. Quando terminar, selecione **Enter**.
1. Verifique as informações mostradas. Essas são as informações de *Separar* que agora se tornarão os dados de *Colocar* da transação put. Quando terminar, selecione **Enter**.

    - Você recebe uma mensagem **Trabalho Concluído**.

1. Repita as etapas de 4 a 10 para a ID de trabalho da segunda ordem de venda.

A próxima etapa é carregar as duas placas de licença separadas para o caminhão.

1. Entre no dispositivo móvel usando uma ID de usuário e uma senha para o depósito *51*.
1. Selecione **Saída**.
1. Selecione **Carregamento de Venda**.
1. Insira a ID da placa de licença de destino definida pelo usuário que você criou para a primeira ID de trabalho no procedimento anterior. Em seguida, selecione **Enter** para colocar a placa de licença de destino no local **ESTÁGIO**.
1. Insira a ID da placa de licença de destino novamente e selecione **Enter** para colocar a placa da licença no local **PORTA DA BAÍA**.
1. Repita as etapas 4 e 5 para a ID da placa de licença de destino que você criou para a segunda ID de trabalho.

Agora as duas IDs de trabalho serão fechadas (carregadas).

### <a name="step-3-confirm-the-outbound-shipment"></a>Etapa 3: Confirmar a remessa de saída

Nesta etapa, você confirmará as duas ordens de venda e o trabalho que foram concluídos para a carga a fim de enviar os itens separados da carga e criar uma nova carga para os itens não separados. A confirmação da remessa de saída deve ser feita na página **Detalhes da carga**.

1. Vá para **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.
1. Na seção **Cargas**, na grade, selecione a linha da ID da carga que você criou.
1. Selecione o link da ID da carga para abrir a página **Detalhes da carga**.
1. Na página **Detalhes da carga**, no Painel de Ação, na guia **Enviar e receber**, no grupo **Confirmar**, selecione **Remessa de saída** para iniciar a confirmação.
1. Na caixa de diálogo **Confirmação de remessa**, no campo **Método de divisão de carga durante confirmação de remessa**, selecione *Dividir quantidade para nova carga*.
1. Selecione **OK**.

    Você pode receber uma mensagem "Processando operação".

    Você recebe mensagens informativas que indicam que a remessa da carga foi confirmada e que uma nova carga foi criada com a quantidade dividida.

Atualize a página **Bancada de planejamento de carga** para ver a carga recém-criada.

Também é possível confirmar que as relações de transação foram atualizadas das seguintes maneiras:

- As linhas de remessa e remessa restante (não processada) são atualizadas com a ID da nova carga.
- A ordem de venda está vinculada à ID da nova carga.
- A carga original não inclui as linhas de carga restantes.
- O trabalho restante foi atualizado com a ID da nova carga.
- A onda permanece igual.
- O status da nova carga é atualizado corretamente. (Se o status do trabalho for _Em andamento_, o status da carga também deverá ser _Em andamento_.)

## <a name="notes-and-tips"></a>Observações e dicas

- Você também pode ativar o parâmetro **Permitir divisão de carga durante confirmação de remessa** depois que a carga for criada com o parâmetro **Modelo de carga** desativado, mas antes do início do processo de carregamento. Vá até a carga desejada e, na exibição de cabeçalho, ative o parâmetro.
- A opção **Dividir quantidade para nova carga** também funciona quando alguns dos cabeçalhos de trabalho restantes têm o status *Em andamento*. Portanto, você ainda poderá usar a funcionalidade mesmo se os trabalhadores já estiverem executando as ordens de separação.
- Se você selecionar **Cancelar quantidade não atendida** enquanto houver trabalho restante com o status *Aberto* ou *Em andamento*, a seguinte mensagem de erro será exibida: "Não é possível cancelar quantidade pendente para carga. Existe trabalho para a carga."
- Se você selecionar **Cancelar quantidade não atendida** quando não houver trabalho restante, mas houver linhas de carga não liberadas na carga, receberá a seguinte mensagem de erro: "Não foi possível confirmar a remessa da carga porque a quantidade do item excede a porcentagem definida para entrega insuficiente." Para evitar o erro, você pode definir a porcentagem de **Entrega insuficiente** na linha de carga não liberada como 100%. As linhas não liberadas não serão movidas para uma nova carga, mas a carga atual será confirmada com entrega insuficiente. Nesse caso, não será possível liberar a ordem original novamente. Por isso você terá que processá-la de outra forma.
