---
title: Processamento de cargas de entrada das ordens de compra no depósito
description: Este tópico descreve o processamento de cargas de entrada das ordens de compra no depósito.
author: omulvad
manager: tfehr
ms.date: 03/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-21
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 991da4a1056bec933698d043fe45fe4e280f555a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004818"
---
# <a name="warehouse-handling-of-inbound-loads-for-purchase-orders"></a>Processamento de cargas de entrada das ordens de compra no depósito

Este tópico descreve o processamento de cargas de entrada das ordens de compra no depósito.

Para cada carga de entrada, seu sistema já deve incluir uma ordem de venda relacionada e talvez também contenha uma especificação de carga e/ou plano de transporte relacionados. Para obter mais informações sobre como criar e gerenciar cargas de entrada, consulte [Processo comercial: Planejando o transporte para cargas de entrada](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/business-process-planning-transportation-for-inbound-loads).

## <a name="overview-how-inbound-loads-are-created-registered-and-received"></a>Visão geral: Como as cargas de entrada são criadas, registradas e recebidas

A ilustração a seguir mostra o fluxo típico de processamento de cargas de entrada que possuem quantidades de ordens de compra quando chegam ao seu depósito.

![O processamento de cargas de entrada](media/inbound-process.png "O processamento de cargas de entrada")

1. **O fornecedor confirma a ordem de compra.**

    O processo começa quando uma ordem de compra é inserida no sistema e depois entregue a um fornecedor, que confirma a ordem. A ordem de compra deve existir antes que você possa criar um registro de carga de entrada. Entretanto, você pode criar a carga de entrada, mesmo que a ordem não tenha sido confirmada. Para obter mais informações, consulte [Aprovar e confirmar ordens de compra](../procurement/purchase-order-approval-confirmation.md).

1. **Um registro de carregamento de entrada é criado para planejar a entrada e seu conteúdo.**

    O registro de carga de entrada representa uma remessa do fornecedor de uma ou mais ordens de compra. Espera-se que a carga chegue ao depósito como uma unidade de transporte físico (como uma carga de caminhão). O registro de carga de entrada é usado para fins de planejamento e permite ao coordenador de logística acompanhar o progresso da carga do fornecedor. Ele também é usado para registrar quantidades de linhas de ordens e gerenciar o progresso nas operações do depósito, como trabalho de entrada e armazenamento. As cargas podem ser criadas automática ou manualmente e podem ser baseadas em uma ordem de compra ou em um aviso de remessa avançada (ASN) do fornecedor. Para obter mais informações, consulte [Criar ou modificar uma carga de entrada](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/create-or-modify-an-inbound-load).

1. **O fornecedor confirma a expedição da carga.**

    Quando o fornecedor expede a carga, o coordenador de logística no depósito de recebimento confirma a remessa da carga. Se a empresa que recebe estiver usando o módulo **Gerenciamento de transporte**, a confirmação da remessa de entrada acionará outros processos de gerenciamento de carga associados às cargas de entrada. Para obter mais informações, consulte [Confirmar uma carga para envio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/confirm-a-load-for-shipping).

1. **A carga chega ao depósito e os funcionários registram as quantidades.**

    Quando um caminhão chega à doca de recebimento do depósito, os funcionários do depósito registram as quantidades de carga. Quando o módulo **Gerenciamento de depósito** é usado, os funcionários fazem o registro usando dispositivos móveis. Para obter mais informações, consulte as seções [Recebimento de produtos contra ordens de compra - registro](../procurement/product-receipt-against-purchase-orders.md#registration) e [Registrar quantidades de itens que chegam em uma carga de entrada](#register-item-quantities-arriving).

1. **As quantidades de carga registradas são lançadas nas ordens de compra.**

    Após as quantidades de carga terem sido registradas na entrada, elas devem ser lançadas como produto recebido no razão do estoque da empresa para registrar o aumento do estoque físico. Para obter mais informações, consulte [Recebimento de produtos contra ordens de compra - recebimento de produtos](../procurement/product-receipt-against-purchase-orders.md#product-receipt) e [Lançar quantidades de produtos registrados nas ordens de compra](#post-registered-quantities).

## <a name="register-item-quantities-that-arrive-on-an-inbound-load"></a><a name="register-item-quantities-arriving"></a>Registrar quantidades de itens que chegam em uma carga de entrada

O Microsoft Dynamics 365 Supply Chain Management oferece suporte a várias abordagens operacionais para registrar a entrada de produtos solicitados. Portanto, você pode configurar o sistema para corresponder aos seus requisitos comerciais específicos. Esta seção descreve como registrar quantidades de itens recebidos usando um dispositivo móvel quando o gerenciamento de depósito avançado está ativado no sistema. No entanto, há um fluxo alternativo baseado no uso do diário de entrada de itens em vez de em um dispositivo móvel. Para obter mais informações sobre esse fluxo, consulte [Registrar itens para um item habilitado de depósito avançado usando um diário de entrada de item](tasks/register-items-advanced-warehousing.md).

Quando uma carga de entrada chega primeiro ao depósito, os funcionários do depósito devem registrar as quantidades de itens incluídas na remessa. Em geral, eles usam scanners portáteis. Esse fluxo de trabalho está disponível apenas se os seguintes itens estiverem presentes no sistema:

- **Um registro de carga de entrada que descreve as quantidades de itens que são esperadas na remessa**

    Geralmente, o fornecedor confirma o registro de carga de entrada antes que a remessa chegue ao depósito. Portanto, a carga tem um status de _Remetida_. No entanto, os funcionários do depósito também podem registrar quantidades de itens para cargas com status de _Em aberto_ ou _Recebida_.

- **Um menu de dispositivo móvel configurado para permitir o recebimento de carga**

    O [aplicativo de depósito](install-configure-warehousing-app.md) para dispositivos móveis é compatível com os seguintes processos de criação de trabalho:

    - Recebimento do item de carga
    - Recebimento e armazenamento do item de carga
    - Recebimento de placa de licença mista, em que o campo **Método de identificação da linha do documento de origem** para o item de menu do dispositivo móvel está definido como _Recebimento do item de carga_. Para obter mais informações, consulte [Recebimento de placa de licença mista](mixed-license-plate-receiving.md).
    - Recebimento e armazenamento de placa de licença mista, em que o campo **Método de identificação da linha do documento de origem** para o item de menu do dispositivo móvel está definido como _Recebimento do item de carga_. Para obter mais informações, consulte [Recebimento de placa de licença mista](mixed-license-plate-receiving.md).

    > [!NOTE]
    > Independentemente do processo, o sistema gerará trabalho para selecionar as quantidades registradas no local de recebimento e mantê-las no local de armazenamento regular. Quando o processo _Recebimento e armazenamento do item de carga_ ou _Recebimento e armazenamento de placa de licença mista_ é usado, o funcionário que registrou a quantidade de carga também será instruído pelo dispositivo a realizar o trabalho de armazenamento como parte da tarefa de registro. Por outro lado, para os processos _Recebimento do item de carga_ e _Recebimento de placa de licença mista_, a suposição é que o trabalho de armazenamento será realizado separadamente da tarefa de registro.

- **Um modelo de trabalho que define o trabalho de separação e armazenamento para cargas recebidas**

    Esse item está relacionado aos itens anteriores. Você deve ter pelo menos um modelo de trabalho para o tipo de ordem de serviço _Ordem de serviço_, o qual deve conter um conjunto de tipos de trabalho de seleção/armazenamento.

O dispositivo móvel orienta o auxiliar de recebimento de depósito através do fluxo para o registro da quantidade de carga. No mínimo, esse fluxo inclui as seguintes etapas para cada ID de carga:

1. Insira a ID da carga.
2. Digite o número do item para um item recebido.
3. Digite a quantidade desse número de item que é recebido.
4. Digite o número da placa de licença do local inicial do item, se o sistema não estiver configurado para gerar esse número automaticamente.
5. Toque em **OK**.

Depois que o funcionário conclui essas etapas, o sistema faz as atualizações a seguir nas entidades apropriadas, desde que a quantidade da linha da ordem de compra que chegou em uma carga e todas as quantidades de carga tenham sido registradas:

| Entidade | Atualizações | Observação |
|---|---|---|
| Carregar | O campo **Quantidade de trabalho criado** na linha de carga é atualizado para mostrar a quantidade registrada. | O valor **Status da carga** permanece _Remetida_ ou _Em aberto_ se nenhuma confirmação de remessa foi executada para a carga. Se pelo menos uma linha de trabalho de armazenamento tiver sido iniciada, ela será alterada para _Em processamento_. |
| Transação de estoque de uma ordem de compra em relação à qual quantidades de carga associadas foram registradas |<p>Os campos a seguir serão atualizados:</p><ul><li>O campo <b>Recebimento</b> está definido como <i>Registrado</i>.</li><li>O campo <b>Local</b> é atualizado com o código de local da doca de recebimento. (Esse código é especificado no campo <b>Local de recebimento padrão</b> para cada depósito.)</li><li>O campo <b>Placa de licença</b> é atualizado com o número da placa de licença que foi inserida ou gerada durante o registro.</li><li>O campo <b>ID de carga</b> é atualizado com o número da carga em que a quantidade foi registrada. (Consulte a nota.)</li></ul> | A capacidade de vincular a transação de estoque da ordem de compra às quantidades registradas na carga foi introduzida na versão 10.0.9 como um recurso opcional chamado _Associar transações de estoque da ordem de compra à carga_. Esse recurso é especialmente benéfico para fluxos operacionais em que uma única ordem de mercadorias compradas é entregue como várias cargas ou quando uma carga contém quantidades para várias ordens. |
| Armazenamento no depósito | O trabalho é criado com base em um modelo de trabalho, para instruir o funcionário a mover as quantidades registradas do local de recebimento para um local de armazenamento regular. | A escolha do local de armazenamento é controlada pela diretiva Local de armazenamento. Se nenhuma diretiva de local foi definida, o local de armazenamento no trabalho está vazio. |

Observe que os funcionários do depósito podem registrar o recebimento de uma ordem de compra com uma ou mais cargas associadas sem usar o processo _Recebimento do item de carga_. Os seguintes métodos estão disponíveis:

- **No dispositivo móvel:** use os processos _Recebimento da linha da ordem de compra_ e _Recebimento da linha da ordem de compra e armazenamento_. (Se houver mais de uma carga para a quantidade de linha da ordem de compra, o funcionário não poderá usar o processo _Recebimento da linha da ordem de compra_. Em vez disso, o funcionário será instruído a usar a ação do dispositivo que está associada ao processo _Recebimento do item de carga_.)
- **No cliente:** use o diário de entrada do item.
- **No cliente:** use a ação **Registro** que pode ser acessada na linha de ordem de compra.

> [!NOTE]
> Se o recebimento da ordem de compra for registrado usando qualquer um dos métodos anteriores, nenhum link será criado entre a transação de estoque da ordem de compra e a carga, mesmo quando o recurso _Associar transações de estoque da ordem de compra à carga_ estiver ativado. Uma exceção a essa regra é quando você usa a opção **Recebimento da linha da ordem de compra** e apenas uma carga possui um status diferente de _Recebida_ para a linha de ordem de compra.

### <a name="handle-discrepancies-during-registration-of-inbound-load-quantities"></a>Controlar discrepâncias durante o registro de quantidades de carga de entrada

Os funcionários do depósito podem fazer um registro de recebimento de quantidade de carga parcial. Cada recebimento de quantidade de carga parcial cria uma transação de estoque separada que possui um status de recebimento de _Recebida_ para a quantidade registrada e a ID do lote se refere à linha de ordem de compra original.

#### <a name="load-under-receiving"></a>Sub-recebimento de carga

Na entrada de uma carga, se as quantidades do item forem menores que aquelas informadas no registro de carga, a equipe de recebimento no depósito pode trabalhar diretamente no cliente para confirmar essa discrepância, reduzindo a quantidade da linha de carga para que ela corresponda à quantidade real que chegou e foi registrada.

#### <a name="load-over-receiving"></a><a name="load-over-receiving"></a>Recebimento de carga em excesso

O recebimento em excesso ocorre quando uma carga chega e as quantidades do item excedem a quantidade de linha de carga esperada. Você pode controlar se e em que grau o recebimento em excesso é permitido durante o registro de carga.

Use o campo **Excesso no recebimento de carga** para os itens de menu relevantes do dispositivo móvel para controlar o que ocorre quando um funcionário do depósito tenta registrar uma entrega excedente. Esse campo está disponível para itens de menu do dispositivo móvel que usam os seguintes tipos de processos de criação de trabalho:

- Recebimento do item de carga
- Recebimento e armazenamento do item de carga
- Recebimento de placa de licença mista (em que o campo **Método de identificação da linha do documento de origem** está definido como _Recebimento do item de carga_)
- Recebimento e armazenamento de placa de licença mista (em que o campo **Método de identificação da linha do documento de origem** está definido como _Recebimento do item de carga_)

A tabela a seguir explica as opções disponíveis para o campo **Excesso no recebimento de carga**.

| Alíquota | descrição |
|---|---|
| Permitir | Os funcionários podem registrar o recebimento de quantidades que excedam a quantidade não registrada restante para uma carga selecionada, mas apenas se a quantidade total registrada não exceder a quantidade da linha da ordem de compra associada à carga (após o ajuste da porcentagem de entrega excedente). |
| Bloquear | <p>Os funcionários não conseguem registrar o recebimento de quantidades que excedam a quantidade não registrada restante para uma carga selecionada (após o ajuste da porcentagem de entrega excedente). Um funcionário que tentar registrar os recebimentos receberá um erro e não poderá continuar até que registre uma quantidade igual ou menor que a quantidade restante de carga não registrada.</p><p>Por padrão, o valor da porcentagem de entrega excedente em uma linha de carga é copiado da linha de ordem de compra associada. Quando o campo <b>Excesso no recebimento de carga</b> está definido como <i>Bloquear</i>, o sistema usa o valor percentual de entrega excedente para calcular a quantidade total que pode ser registrada para uma linha de carga. Entretanto, esse valor pode ser substituído para cargas individuais, conforme necessário. Esse comportamento se torna relevante durante o recebimento de fluxos em que parte ou toda a quantidade excedente que representa a porcentagem de entrega excedente da linha da ordem é distribuída desproporcionalmente em várias cargas. Veja um exemplo de cenário:</p><ul><li>Existem várias cargas para uma linha de ordem de compra.</li><li>A linha da ordem tem uma porcentagem de entrega excedente superior a 0 (zero).</li><li>As quantidades já foram registradas em uma ou mais cargas sem levar em consideração a porcentagem de entrega excedente.</li><li>A quantidade de entrega excedente chega na última carga.</li></ul><p>Nesse cenário, um dispositivo móvel pode ser usado para registrar a quantidade excedente para a última carga somente se o supervisor do depósito aumentar a porcentagem de entrega excedente para a linha de carga relevante do valor padrão para um valor que seja grande o suficiente para que a entrega excedente completa possa ser registrada com a carga final.</p> |
| Bloquear somente para cargas fechadas | Os funcionários podem receber quantidades excessivas de linhas de carga para cargas em aberto, mas não para cargas com o status de _Recebida_. |

> [!NOTE]
> O valor padrão do campo **Excesso no recebimento de carga** é _Permitir_. Quando esse valor é usado, o comportamento corresponde ao comportamento padrão que estava disponível antes da introdução do recurso _Excesso no recebimento de quantidades de carga_ na versão 10.0.11.

### <a name="put-away-the-registered-quantities"></a>Armazenar as quantidades registradas

Quando o registro é concluído no dispositivo móvel, a ação _Registro de recebimento de quantidade_ atualiza os registros de estoque e depósito para indicar que as quantidades estão agora no local da doca de recebimento e disponíveis para reserva. No entanto, as operações de depósito de uma empresa costumam exigir que as quantidades sejam movidas da doca de recebimento para o armazenamento regular no depósito, para que os processos de seleção subsequentes possam ocorrer. As instruções para armazenamento são capturadas no trabalho de armazenamento que é gerado automaticamente quando a carga de entrada é registrada como recebida.

Quando o funcionário do depósito concluir o trabalho de armazenamento, o sistema registra e rastreia o resultado atualizando várias entidades, conforme resumido na tabela a seguir.

| Entidade | Atualizações | Observação |
|---|---|---|
| Carregar | <p>Os campos a seguir serão atualizados:</p><ul><li>O valor <b>Status da carga</b> é alterado para <i>Em processamento</i>.</li><li>O valor <b>Status de trabalho</b> é alterado para <i>100,00% de trabalho concluído</i>.</li></ul> | O valor **Status da carga** é alterado para _Em processamento_ quando o funcionário inicia a tarefa de armazenamento para pelo menos uma linha de trabalho de armazenamento. |
| Transações de estoque de trabalho em relação às quais quantidades associadas foram armazenadas | Os campos **Recebimento** e **Local** e outros campos relevantes são atualizados para refletir o movimento do local de recebimento para o local de armazenamento. | O valor **Estado de recebimento** da transação de estoque da ordem de compra permanece _Registrado_. |
| Armazenamento no depósito | O valor **Status de trabalho** é alterado para _Fechado_. | |

## <a name="post-registered-product-quantities-against-purchase-orders"></a><a name="post-registered-quantities"></a>Lançar quantidades de produtos registrados nas ordens de compra

Depois que as quantidades de produtos de entrada são registradas no sistema, elas ficam disponíveis para reserva em conexão com vendas e outras operações internas e de saída. No entanto, o sistema ainda não atualiza as contas de estoque (provisórias). Essa atualização pode ocorrer apenas quando a equipe de operações lança os recebimentos de produtos registrados.

Para abrir uma página na qual possam lançar um recibo do produto, os membros da equipe de operações podem seguir qualquer _uma_ das etapas abaixo:

- Abra o registro da carga relevante e selecione a ação **Recebimento de produtos**.
- Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Atualizar recebimentos de produtos** e, no campo **ID de carga**, especifique a carga que será lançada.
- Abra a ordem de compra relevante e selecione a ação **Recebimento de produtos**.
- Acesse **Compras e fornecimento \> Ordens de compra \> Recebendo produtos \> Trabalho Lançamento de recebimento de produtos**.

A ação **Recebimento de produtos** disponível na página **Carga** (e na página equivalente do trabalho de atualização, a página **Atualizar recebimentos de produtos**) pode atualizar as quantidades de recebimento de produtos somente em quantidades de ordens de compra com status de _Registrada_. No entanto, a ação **Recebimento de produtos** disponível na página **Ordem de compra** pode incluir quantidades nos dois status de processamento (_Encomendado_ e _Registrado_). Ela também pode controlar o escopo do lançamento de recebimento de produtos por meio de parâmetros adicionais, como _Quantidade de recebimento atual_ e _Quantidade e serviços registrados_.

Somente ordens com o status _Confirmada_ podem ser lançados como produto recebido. Para ordens de compra não confirmadas, a ação **Recebimento de produtos** aparecerá como indisponível.

### <a name="post-registered-quantities-from-the-load-page"></a>Lançar quantidades registradas na página Carga

Para lançar quantidades registradas como produto recebido na página **Carga**, os seguintes pré-requisitos devem estar em vigor:

- A carga deve ter pelo menos uma unidade de quantidade com o status _Registrada_.
- O status da carga deve ser _Remetida_.
- A ordem de compra associada à carga deve ter o status de _Confirmada_.

> [!NOTE]
> Se o status da carga não tiver sido definido como _Remetida_, o sistema confirmará automaticamente a carga antes de executar a atualização de recebimento do produto. (O status da carga é definido como _Remetida_ quando um usuário registra a remessa de entrada da carga.)

Para lançar como produto recebido os registros de entrada associados a uma carga selecionada, o funcionário seleciona a ação **Recebimento de produtos** na página **Carga**. A página que é aberta possui os seguintes detalhes principais:

- O campo **Quantidade** na seção **Parâmetros** na guia **Configurações** mostra a _quantidade registrada_. Nenhuma outra opção está disponível aqui.
- A grade da FastTab **Visão geral** lista todas as ordens de compra incluídas na carga selecionada.
- A grade da FastTab **Linhas** lista todas as linhas da ordem que possuem uma quantidade registrada.

> [!NOTE]
> As quantidades das linhas da ordem que aparecem na guia **Linha** são calculadas de maneira diferente, dependendo se o recurso _Permitir vários recebimentos de produtos por carga_ está disponível e ativado na sua versão do Supply Chain Management.
>
> | Versão | Cálculo |
> |---|---|
> | Versões anteriores à versão 10.0.10 e versões mais recentes, em que o recurso _Permitir vários recebimentos de produtos por carga_ não está ativado | A quantidade de linha é o total de todas as quantidades registradas _dessa linha de ordem de compra_, independentemente de o registro ter sido feito em várias cargas, independentemente da carga, em um dispositivo móvel ou no cliente. |
> | Versão 10.0.10 e posterior, onde o recurso _Permitir vários recebimentos de produtos por carga_ está ativado | A quantidade de linha é o total de todas as quantidades registradas _do registro de carga_ no qual a ação **Lançamento do recebimento de produtos** foi iniciada. |

Quando o usuário seleciona **OK** para confirmar o lançamento de recebimento de produtos, o sistema faz as atualizações a seguir importantes nas entidades apropriadas.

| Entidade | Atualizações |
|---|---|
| Transação de estoque da ordem de compra em relação à qual as quantidades de linha foram incluídas no escopo de lançamento | <p>Os seguintes campos são atualizados (mas observe que também existem várias outras atualizações):</p><ul><li>O campo <b>Recebimento</b> está definido como <i>Recebida</i>.</li><li>O campo <b>Data física</b> é atualizado com a data da lançamento.</li></ul> |
| Carga da qual o usuário lançou o recebimento de produtos | As atualizações das cargas dependerão da versão usada e da configuração do campo **Permitir vários recebimentos de produtos por carga**. As regras são descritas na tabela que aparece mais adiante nesta seção. |

O campo **Permitir vários recebimentos de produtos por carga** permite que as empresas escolham uma política de recebimento de carga de entrada. Dependendo de seus fluxos operacionais, as empresas podem optar por permitir ou não vários lançamentos de recebimento de produtos para a mesma carga. Recomendamos que o gerente de logística defina o campo **Permitir vários recebimentos de produtos por carga** com um dos seguintes valores:

- **Não** – Selecione este valor se os auxiliares de recebimento de depósito sempre registram todas as quantidades de ordens que chegam com cada carga dentro de um período designado. Se alguma quantidade de carga não for registrada, o sistema assumirá que ela não chegou ou não estava na carga e, portanto, não deve ser considerada parte da carga. O lançamento de recebimento de produtos executado por meio de uma carga usa a mesma suposição. Além de recebimento de produto, atualizando todas as quantidades registradas (sua principal função), ele informa a carga completa e fechada para processamento adicional. Nesse caso, todas as quantidades de linhas de carga são atualizadas automaticamente para as quantidades registradas, as linhas de carga que não possuem quantidades registradas são excluídas e o status da carga é alterado para _Recebida_.
- **Sim** – Selecione este valor se os auxiliares de recebimento de depósito precisarem de mais tempo para registrar todas as quantidades da carga que chegou, mas, nesse ínterim, é necessário lançar como produto recebido as quantidades que já foram registradas. Nesse caso, o gerente de logística desejará manter uma carga aberta, mesmo após a execução do trabalho de lançamento de recebimento de produtos, para que as quantidades de carga restantes possam ser registradas e atualizadas como produto recebido no razão de forma contínua.
- **Aviso** – Selecione este valor se suas práticas de recebimento de carga forem combinadas e for necessária uma decisão toda vez que o lançamento de recebimento de produtos for executado.

A tabela a seguir resume os efeitos da configuração **Permitir vários recebimentos de produtos por carga**.

| Permitir vários recebimentos de produtos por carga | Quantidade de carga | Status da carga | Observação |
|---|---|---|---|
| Quando esse campo não está disponível (versões anteriores à 10.0.10) | <p>A quantidade de carga é definida para que seja igual à quantidade registrada.</p><p>Se a quantidade de carga for atualizada para 0 (zero), o que significa que nenhum registro foi feito, a linha de carga será excluída.</p><p>Se não houver linhas de carga na carga, a carga será excluída.</p> | _Recebida_ | Se houver várias cargas para a quantidade registrada da linha do pedido, somente o status da carga da qual o recebimento foi lançado será atualizado para _Recebida_. |
| Não | <p>A quantidade de carga é definida para que seja igual à quantidade registrada associada à ID de carga.</p><p>Se nenhuma ID de carga for registrada para a transação de estoque, o comportamento corresponderá ao das versões anteriores à 10.0.10.</p> | _Recebida_ | |
| Sim | Nenhuma atualização | _Recebida_, se a quantidade total de carga registrada for igual ou superior à quantidade de carga | |
| Sim | Nenhuma atualização | _Remetida_ ou _Em processamento_, se a quantidade total de carga registrada for inferior à quantidade de carga | |

Depois que o campo **Status da carga** é definido como _Recebida_, não é possível fazer mais lançamentos de recebimento de produtos para essa carga. Entretanto, o funcionário pode registrar a quantidade restante da ordem na carga recebida nas condições a seguir. (Para obter mais informações, consulte a seção [Recebimento de carga em excesso](#load-over-receiving) anterior nesse tópico.)

- A versão do Supply Chain Management é anterior à versão 10.0.11.
- O recurso _Excesso no recebimento de quantidades de carga_ está ativado e o campo **Excesso no recebimento de quantidade da linha de carga** no item de menu do dispositivo móvel em relação à ação de recebimento de itens de carga está definido como _Permitir_.

Para lançar como produto recebido quantidades de carga registradas adicionais em relação a uma carga com o status de _Recebida_, o usuário deve executar a ação de lançamento na ordem de compra associada.

### <a name="post-registered-quantities-from-the-purchase-order-page"></a>Lançar quantidades registradas na página Ordem de compra

Para lançar como produto recebido quantidades registradas na página **Ordem de compra**, o usuário conclui as seguintes tarefas antes de selecionar a ação **Recebimento de produtos**:

- Defina o campo **Quantidade** na seção **Parâmetros** na guia **Configurações** como _Quantidade registrada_.
- No campo **Recebimento de produtos**, insira os números das ordens de compra incluídos no lançamento.

> [!NOTE]
> A quantidade de linha que será incluída no escopo de lançamento é o total de todas as quantidades registradas para a linha da ordem, independentemente de o registro de quantidade ter sido feito em várias cargas, independentemente da carga, em um dispositivo móvel ou no cliente. A mesma regra se aplica quando o lançamento de recebimento de produtos é executado em uma carga, se feito onde o campo **Permitir vários recebimentos de produtos por carga** não estiver disponível ou não estiver ativado.

Quando o usuário seleciona **OK** para confirmar o lançamento de recebimento de produtos, o sistema faz as atualizações a seguir importantes nas entidades apropriadas.

| Entidade | Atualizações |
|---|---|
| Transação de estoque da ordem de compra em relação à qual as quantidades de linha foram incluídas no escopo de lançamento | <p>Os seguintes campos são atualizados (mas observe que também existem várias outras atualizações):</p><ul><li>O campo <b>Recebimento</b> está definido como <i>Recebida</i>.</li><li>O campo <b>Data física</b> é atualizado com a data da ação de lançamento do recebimento de produtos.</li></ul> |
| Carregar | As atualizações nas cargas dependem se o campo **Permitir vários recebimentos de produtos por carga** está disponível e ativado. As regras são descritas na tabela a seguir. |

A tabela a seguir resume os efeitos da configuração **Permitir vários recebimentos de produtos por carga**.

| Permitir vários recebimentos de produtos por carga | Quantidade de carga | Status da carga | Observação |
|---|---|---|---|
| Quando esse campo está desativado ou indisponível (nas versões anteriores à 10.0.10) | Nenhuma atualização | Nenhuma atualização é feita. (O status permanece _Em aberto_, _Remetida_ ou _Em processamento_.) | Como o registro de recebimento de produtos é iniciado na ordem de compra, a lógica de atualização não possui informações sobre a associação entre as quantidades registradas dentro de seu escopo e as cargas nas quais o registro foi registrado. Portanto, ele não pode selecionar a carga para a atualização de status. |
| Habilitada | Nenhuma atualização | <p>Ocorre uma das seguintes ações:</p><ul><li>O status será alterado para <i>Recebida</i> se as quantidades totais recebidas e compradas das transações de estoque de ordem de compra forem maiores ou iguais à quantidade da carga à qual estão associados.</li><li>O status permanece <i>Em aberto</i>, <i>Remetida</i> ou <i>Em processamento</i> se a condição anterior não for atendida para todas as linhas na carga.</li></ul> | |

### <a name="select-the-appropriate-product-receipt-posting-option-for-your-logistics-operations"></a>Selecione a opção apropriada de lançamento de recebimento de produtos para suas operações logísticas

Como foi descrito anteriormente, o sistema oferece duas opções de lançamento de recebimento de produtos. As opções podem ser acessadas nos seguintes locais:

- Na página **Carga** ou no menu **Gerenciamento de depósito \> Tarefas periódicas** como um trabalho de atualização
- Na página **Purchase order** ou no menu **Compras e fornecimento \> Ordens de compra \> Recebendo produtos** como um trabalho de atualização

As empresas que usam cargas para planejar e gerenciar transporte e depósito de suas ordens de entrada são aconselhadas a utilizar as funções a seguir que foram desenvolvidas para trabalhar com cargas:

- Ações **Recebimento do item de carga** em seus dispositivos móveis de depósito, para registrar a entrada da quantidade do produto na carga
- Ações **Lançamento do recebimento de produtos** iniciadas em uma carga, para atualizar o razão do estoque

> [!NOTE]
> Outras funções de registro de quantidade e lançamento de recebimento de produtos podem ser usadas para oferecer suporte aos processos operacionais de entrada correspondentes. No entanto, se você usá-las de maneira intercambiável com ou em vez das funções exclusivas com foco na carga, talvez comprometa a precisão dos dados dos registros de carga e, portanto, a uniformidade dos fluxos de gerenciamento de carga.

## <a name="example-scenarios"></a>Cenários de exemplo

### <a name="prepare-your-system-to-run-the-sample-scenarios"></a>Prepare seu sistema para executar os cenários de exemplo

Para trabalhar com os cenários de exemplo descritos nesta seção, você deve primeiro se certificar de que todos os recursos necessários estejam ativados no seu sistema. Os dados de demonstração necessários também devem estar disponíveis no sistema.

#### <a name="turn-on-the-required-features"></a>Ativar os recursos necessários

Esses cenários exigem o recurso _Vários lançamentos de recebimento de produtos por carga_ e seu recurso de pré-requisito. Os administradores podem ativar esses recursos as etapas a seguir.

1. Abra o espaço de trabalho **Gerenciamento de recursos**. (Para obter detalhes completos sobre como encontrar e usar esse espaço de trabalho, consulte [Visão geral do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)

1. Ative o recurso _Associar transações de estoque da ordem de compra à carga_, listado da seguinte maneira:

    - **Módulo:** _Gerenciamento de Depósito_
    - **Nome do recurso:** _Associar transações de estoque da ordem de compra à carga_

1. Ative o recurso _Vários lançamentos de recebimento de produtos por carga_, listado da seguinte maneira:

    - **Módulo:** _Gerenciamento de Depósito_
    - **Nome do recurso:** _Vários lançamentos de recebimento de produtos por carga_

#### <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para trabalhar com esses cenários usando os registros e valores de exemplo especificados, você deve usar um sistema em que os dados de demonstração padrão estão instalados. Você também deve selecionar a entidade legal **USMF** antes de começar.

#### <a name="add-a-menu-item-for-receiving-load-items-when-a-mobile-device-is-used"></a>Adicione um item de menu para receber itens de carga quando um dispositivo móvel for usado

Antes de os auxiliares de recebimento de depósito poderem usar um dispositivo móvel para registrar o estoque de entrada que está vinculado a uma carga, você deve criar um item de menu do dispositivo móvel para esse fim.

Nesta seção, você criará um item de menu do dispositivo móvel e o adicionará a um menu existente. Um funcionário do depósito pode selecionar o item de menu no aplicativo de depósito.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel** e verifique se o menu do seu dispositivo móvel inclui um item de menu com as seguintes configurações:

    - **Modo:** _Trabalho_
    - **Processo de criação de trabalho:** _Recebimento do item de carga_
    - **Gerar placa de licença:** _Sim_

    Você pode deixar todas as outras configurações com seus valores padrão.

    ![Configurações do item de menu do dispositivo móvel](media/inbound-mobile-menu-items.png "Configurações do item de menu do dispositivo móvel")

    Para obter mais informações sobre como configurar itens de menu do dispositivo móvel, consulte [Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md).

2. Depois de concluir a configuração do item de menu, acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu de dispositivos móveis** e adicione-o à estrutura do menu de seus dispositivos móveis.

### <a name="example-scenario-1-register-a-load-where-some-items-are-missing"></a>Cenário de exemplo 1: registrar uma carga em que alguns itens estão ausentes

Esse cenário mostra como registrar quantidades para uma carga de entrada em que nem todas as quantidades esperadas estão presentes. Em seguida, mostra como lançar o recebimento de produtos para a ordem de compra.

#### <a name="create-a-load-to-plan-receipt-of-a-purchase-order"></a>Criar uma carga para planejar o recebimento de uma ordem de compra

Neste procedimento, você criará manualmente uma ordem de compra e uma carga associada. Você atualizará a carga para simular que ela foi remetida pelo fornecedor (que atualiza o status da carga). Os planejadores do depósito podem filtrar as cargas por **Status da carga** para encontrar as cargas de entrada esperadas.

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de compra**, defina o campo **Conta de fornecedor** como _1001_.
1. Selecione **OK** para fechar a caixa de diálogo e criar a ordem de compra.
1. A nova ordem de compra já inclui uma linha em **Linhas de ordem de compra**. Defina os seguintes valores para essa linha:

    - **Número de item:** _A0001_
    - **Depósito:** _24_
    - **Quantidade:** _10_

1. No Painel de ações, na guia **Compra**, selecione **Ações \> Confirmar**. O status da ordem agora é _Confirmada_.
1. No Painel de ações, na guia **Depósito**, selecione **Ações \> Bancada do planejamento de carga**.
1. Na página **Bancada de planejamento de carga**, no Painel de ações, na guia **Oferta e demanda**, selecione **Adicionar \> Para nova carga**.
1. Na caixa de diálogo **Atribuição de modelo de carga**, defina o campo **ID do modelo de carga** como _Contêiner 20'_.
1. Selecione **OK** para fechar a caixa de diálogo e retornar ao ambiente de trabalho.
1. Na seção **Cargas**, selecione **ID de carga** para abrir a carga recém-criada.
1. Revise o cabeçalho de carga e os detalhes da linha e observe os seguintes pontos:

    - Na FastTab **Carga**, o campo **Status da carga** é definido _Em aberto_.
    - Na seção **Linhas de carga**, existe uma única linha em que o campo **Quantidade** é definido como _10_ e o campo **Quantidade de trabalho criado** é definido como _0_ (zero).

    ![Detalhes da carga](media/inbound-load-details.png "Detalhes da carga")

1. No Painel de ações, na guia **Enviar e receber**, no grupo **Confirmar \> Remessa de entrada**. Observe que o **Status da carga** foi alterado para _Remetida_.
1. Anote o valor **ID de carga**, para que você possa usá-lo no próximo procedimento.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-load"></a>Registrar o recebimento das quantidades que chegaram na carga

Quando a carga chega à doca de recebimento do depósito, um auxiliar de recebimento registra as quantidades de carga de um dispositivo móvel.

1. Use seu dispositivo móvel para entrar no depósito 24. (Nos dados de demonstração padrão, entre usando _24_ como a ID do usuário e _1_ como a senha.)
1. Selecione o item de menu _Recebimento do item de carga_ que você criou para o cenário.
1. Siga as instruções de entrada de dados na tela para inserir os valores a seguir. (A ordem pode variar, dependendo do dispositivo móvel ou emulador que você está usando.)

    - **Carga** – Insira a ID de carga que você criou no procedimento anterior.
    - **Item** – Insira _A0001_, que é o item esperado para essa carga.
    - **Qtd.** – Insira _9_ como a quantidade real presente na carga. Observe que essa quantidade é menor que a quantidade esperada.

1. Continue passando pelo fluxo de trabalho, deixando todos os outros campos em branco ou com os valores padrão até o dispositivo informar que o trabalho foi concluído.

A tarefa de recebimento de carga agora está concluída, e o auxiliar de recebimento pode passar para a próxima tarefa. No entanto, a equipe de recebimento de depósito revisará o registro de carga e poderá ver que a quantidade recebida foi menor que a quantidade esperada. Eles concluirão o procedimento a seguir usando o cliente Web.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Na lista, encontre a carga que você acabou de receber. (Pode ser necessário marcar a caixa de seleção **Mostrar fechada** para incluir as cargas de entrada com um status de carga de _Remetida_.) Em seguida, selecione o link na coluna **ID de carga** para abrir a carga.
1. No registro de carga, observe que o valor **Status da carga** permanece _Remetida_, mas o valor **Quantidade de trabalho criado** na linha de carga foi alterado para _9_.
1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Na lista, localize a compra que você acabou de receber e selecione o link na coluna **Ordem de compra** para abrir a ordem.
\
1. Na FastTab **Linhas de ordem de compra**, selecione **Estoque \> Exibir \> Transações**.
1. Revise os detalhes das duas transações de ordem de compra. (Talvez você precise personalizar a página **Transações de estoque** para ver o campo **ID de carga** na grade.) Você deve ver duas transações:

    - A transação que possui um recebimento no status _Registrada_ representa a quantidade de registro de _9_ que foi executada em uma carga específica usando o dispositivo móvel. A **ID de carga** está associada à transação em questão.
    - A transação que possui um recebimento no status _Encomendada_ representa a quantidade restante de linhas de ordens não registradas de _1_.

#### <a name="product-receiptpost-the-registered-load-quantities-against-purchase-orders"></a>Lançar como produto recebido as quantidades de carga registradas nas ordens de compra

Neste procedimento, você lançará como produto recebido o estoque que você registrou para uma carga. Como resultado, o estoque recebido e seus custos relacionados serão adicionados à contabilidade da empresa.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Na lista, encontre a carga recebida. (Pode ser necessário marcar a caixa de seleção **Mostrar fechada** para incluir as cargas de entrada com um status de carga de _Remetida_.) Em seguida, selecione o link na coluna **ID de carga** para abrir a carga.
1. No Painel de ações, na guia **Enviar e receber**, no grupo **Receber \> Recebimento de produtos**. Se você for solicitado a confirmar a ação, selecione **Sim**.
1. Na caixa de diálogo **Lançamento de recebimento de produtos**, na FastTab **Lines**, inspecione a grade. Você deve ver a linha de ordem de compra para a qual a quantidade foi registrada na carga selecionada.

    > [!NOTE]
    > Nas versões em que o recurso _Vários lançamentos de recebimento de produtos por carga_ não está disponível ou não está ativado, a quantidade padrão mostrada na grade **Linhas de carga** será a quantidade total registrada em todas as cargas que estão associadas à linha de ordem de compra.

1. Na FastTab **Visão geral**, inspecione o campo **Recebimento de produtos** na grade. Observe que ele é definido como um número que inclui a ID de carga selecionada.
1. Selecione **OK** para lançar o recebimento do produto e feche a caixa de diálogo **Lançamento de recebimento de produtos**.
1. Você retornou aos detalhes da carga. Observe os seguintes pontos:

    - O campo **Status da carga** agora é definido como _Recebida_.
    - Na linha de carga, o valor **Quantidade** da carga foi alterado de _10_ a _9_ pcs para corresponder à quantidade registrada, mas o valor de **Quantidade de trabalho criado** permanece _9_.

Caso a equipe de compras não espere que o fornecedor entregue a quantidade restante da ordem de 1, poderá fechá-la atualizando o restante da entrega da linha para _0_. Contudo, caso se descubra logo que a peça que faltava chegou na carga original, a equipe do depósito pode executar uma das seguintes ações:

- Registre a quantidade na mesma carga. Nesse caso, o campo **Status da carga** será redefinido para _Remetida_ e o valor **Quantidade de trabalho criado** será atualizado para _10_. Esta opção está disponível apenas nas seguintes situações:

    - O recurso _Excesso no recebimento de quantidades de carga_ não está disponível ou não está ativado.
    - O recurso _Excesso no recebimento de quantidades de carga_ está disponível e ativado, e o campo **Excesso no recebimento de quantidade da linha de carga** está definido como _Permitir_.

- Adicione a quantidade a uma carga nova ou existente e processe-a da maneira usual.
- Registre e/ou receba a quantidade de uma forma que não envolva processamento de carga.

### <a name="example-scenario-2-register-quantities-that-arrive-on-multiple-inbound-loads-where-some-items-are-missing"></a>Cenário de exemplo 2: registrar quantidades que chegam em várias cargas de entrada nas quais alguns itens estão ausentes

Nesse cenário, uma remessa de entrada relacionada a uma única linha de ordem de compra será dividida em duas cargas. Por exemplo, uma linha de ordem de compra pode ser dividida em várias cargas em razão restrições de carga física em peso e/ou volume.

Esse cenário também mostra como processar vários lançamentos de recebimento de produtos para a mesma carga. Você registrará as quantidades que chegam em várias cargas de entrada, mas as quantidades não corresponderão às quantidades esperadas. As atualizações de custo que ocorrem por meio do lançamento do recebimento de produtos serão feitas várias vezes para a mesma carga.

#### <a name="set-up-load-receiving-policies"></a>Configurar políticas de recebimento de carga

Neste procedimento, você habilitará vários lançamentos de recebimento de produtos da mesma carga.

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Cargas**, defina o campo **Permitir vários recebimentos de produtos por carga** como _Sim_.

#### <a name="create-two-loads-to-plan-receipt-of-a-purchase-order"></a>Criar duas cargas para planejar o recebimento de uma ordem de compra

Neste procedimento, você criará uma ordem de compra e duas cargas. Você atualizará manualmente cada carga para simular que ela foi remetida pelo fornecedor (que atualiza o status da carga). Os planejadores do depósito podem filtrar as cargas por **Status da carga** para encontrar as cargas de entrada esperadas.

Você também aprenderá como definir a linha da ordem de compra para poder receber uma quantidade 20% maior que a quantidade especificada da linha.

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Selecione **Novo**.
1. Na FastTab **Fornecedor**, defina o campo **Conta de fornecedor** como _1001_ e selecione **OK**.
1. Sua ordem de compra é aberta e inclui uma linha em branco na grade **Linhas de ordem de compra**. Defina os seguintes valores para essa linha de ordem:

    - **Número de item:** _A0001_
    - **Depósito:** _24_
    - **Quantidade:** _10_

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Entrega excedente** como _20_.
1. No Painel de ações, na guia **Compra**, selecione **Ações \> Confirmar**. O status da ordem agora é _Confirmada_.
1. No Painel de ações, na guia **Depósito**, selecione **Ações \> Bancada do planejamento de carga**.
1. Na página **Bancada de planejamento de carga**, no Painel de ações, na guia **Oferta e demanda**, selecione **Adicionar \> Para nova carga**.
1. Na caixa de diálogo **Atribuição de modelo de carga**, defina o campo **ID do modelo de carga** como _Contêiner 20'_. Na guia **Detalhes**, altere o valor **Quantidade** de _10_ para _5_ para adicionar parcialmente a quantidade da linha da ordem de compra.
1. Selecione **OK** para aplicar suas configurações e fechar a caixa de diálogo.
1. Repita as etapas 8 a 10 para criar uma segunda carga. Dessa vez, o campo **Quantidade** já deve estar definido como _5_.
1. Na página **Bancada do planejamento de carga**, na grade **Cargas**, selecione o valor **ID de carga** da primeira carga que você criou. A página **Detalhes da carga** é exibida e mostra a carga selecionada. Execute estas etapas:

    1. No Painel de ações, na guia **Enviar e receber**, no grupo **Confirmar \> Remessa de entrada**.
    1. Observe que o valor **Status da carga** foi alterado para _Remetida_.
    1. Selecione o botão Fechar para retornar à página **Bancada de planejamento de carga**.

1. Repita a etapa anterior para a segunda carga que você criou.
1. Anote os dois valores **ID de carga** que aparecem na grade **Cargas**.

#### <a name="register-partial-receipt-of-the-quantities-that-arrived-on-the-first-load-and-post-the-registered-load-quantities"></a>Registrar o recebimento parcial das quantidades que chegaram na primeira carga e lançar as quantidades de carga registradas

Quando as cargas chegam à doca de recebimento do depósito, um auxiliar de recebimento registra as quantidades de carga de um dispositivo móvel. O estoque registrado vinculado a uma carga é então atualizado na contabilidade da empresa lançando o recebimento do produto da ordem de compra, com base na carga.

Esse procedimento mostra como um auxiliar de recebimento registrará quantidades de carga de um dispositivo móvel.

1. Use seu dispositivo móvel para entrar no depósito 24. (Nos dados de demonstração padrão, entre usando _24_ como a ID do usuário e _1_ como a senha.)
1. Selecione o item de menu _Recebimento do item de carga_ que você criou para o cenário.
1. Siga as instruções de entrada de dados na tela para inserir os valores a seguir. (A ordem pode variar, dependendo do dispositivo móvel ou emulador que você está usando.)

    - **Carga** – Insira a primeira ID de carga que você criou no procedimento anterior.
    - **Item** – Insira _A0001_, que é o item esperado para essa carga.
    - **Qtd.** – Digite _3_. Observe que essa quantidade é menor que a quantidade esperada. Nesse cenário, imagine que você, como auxiliar de recebimento, não tenha tempo para registrar todas as quantidades dessa carga. Posteriormente neste procedimento, você registrará as peças restantes repetindo essa etapa e configurando o campo **Qtd.** como _2_.

1. Continue passando pelo fluxo de trabalho, deixando todos os outros campos em branco ou com os valores padrão até o dispositivo informar que o trabalho foi concluído.
1. No cliente Web, acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Na lista, encontre a carga que você acabou de receber e selecione o valor **ID de carga** para abrir a carga. Observe que o valor **Status da carga** permanece _Remetida_, mas o valor **Quantidade de trabalho criado** na linha de carga foi alterado para _3_.
1. No Painel de ações, na guia **Enviar e receber**, no grupo **Receber \> Recebimento de produtos**. Se você for solicitado a confirmar a ação, selecione **Sim**.
1. Na caixa de diálogo **Lançamento de recebimento de produtos**, revise, mas não altere os valores mostrados e selecione **OK**.
1. Você retornou à página **Detalhes da carga** da carga selecionada. Observe os seguintes pontos:

    - O campo **Status da carga** permanece definido como _Remetida_.
    - Na linha de carga, o valor **Quantidade** da carga permanece _5_ pcs, que é a quantidade original de carga, e o valor **Quantidade de trabalho criado** permanece _3_.

1. Conclua o registro da quantidade restante dessa carga, repetindo esse procedimento. No entanto, na etapa 3, defina o campo **Qtd.** como _2_.

A tarefa de recebimento da primeira carga agora está concluída. Foram criados dois diários de recebimento de produtos, um para cada uma das duas atualizações de recebimento de produtos que você executou.

#### <a name="register-receipt-of-the-quantities-that-arrived-on-the-second-load-and-account-for-the-overdelivered-quantity"></a>Registrar o recebimento das quantidades que chegaram na segunda carga e contabilizar a quantidade entregue em excesso

Nesse cenário, o auxiliar de recebimento registrará na entrada uma quantidade que excede a quantidade existente na carga. O recebimento em excesso será permitido porque o sistema está configurado para permitir a entrega excedente.

1. Use seu dispositivo móvel para entrar no depósito 24. (Nos dados de demonstração padrão, entre usando _24_ como a ID do usuário e _1_ como a senha.)
1. Selecione o item de menu _Recebimento do item de carga_ que você criou para o cenário.
1. Siga as instruções de entrada de dados na tela para inserir os valores a seguir. (A ordem pode variar, dependendo do dispositivo móvel ou emulador que você está usando.)

    - **Carga** – Insira a segunda ID de carga que você criou anteriormente.
    - **Item** – Insira _A0001_, que é o item esperado para essa carga.
    - **Qtd.** – Insira _7_, que é a quantidade restante que o fornecedor está autorizado a entregar como parte da quantidade total da ordem de compra de 12 (onde 10 é a quantidade original da ordem e 2 é a quantidade permitida de entrega excedente de 20%). Lembre-se de que 5 pcs já foram registradas na primeira carga.

A segunda carga agora foi atualizada com a quantidade de 7 e pode ser atualizada como produto recebido com base nessa quantidade.
