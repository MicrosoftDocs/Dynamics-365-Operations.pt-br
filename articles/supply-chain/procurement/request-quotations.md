---
title: Visão geral de solicitações de cotação (RFQs)
description: Este tópico fornece uma visão geral das solicitações de cotação (RFQs). As organizações emitem RFQs quando desejam receber ofertas competitivas de vários fornecedores para os itens ou serviços que eles compram.
author: mkirknel
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: daa21e547a1d38b898032e3cdbeee40de23bd64e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207870"
---
# <a name="requests-for-quotation-rfqs-overview"></a>Visão geral de solicitações de cotação (RFQs)

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral das solicitações de cotação (RFQs). As organizações emitem RFQs quando desejam receber ofertas competitivas de vários fornecedores para os itens ou serviços que eles compram. Em uma RFQ, você solicita que os fornecedores forneçam preços e prazos de entrega das quantidades do item que você especificar.
Você também pode solicitar que os fornecedores especifiquem caso haja encargos incidentais, como custos de remessa, ou quaisquer descontos para grandes pedidos ou pagamento antecipado da fatura do fornecedor.

O processo de RFQ consiste nas seguintes tarefas:

1.  Criar e enviar uma RFQ a um ou mais fornecedores.

2.  Receber e registrar lances (respostas da RFQ)

3.  Transferir os lances aceitos para uma ordem de compra, um contrato de compra ou uma requisição de compra.

A ilustração a seguir mostra uma visão geral do processo de RFQ.

[![Processo RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Você pode criar um caso de RFQ de ordens planejadas, de uma requisição de compra ou por entrada manual. O caso de RFQ é o documento base que você usa para emitir uma RFQ a cada fornecedor.+

Após preparar o caso de RFQ e adicionar fornecedores, selecione **Enviar** (**Enviar e publicar** para o setor público) no caso de RFQ. Um diário de RFQ é gerado para cada fornecedor para o qual você enviou a RFQ. Você pode definir as configurações de impressão para a ação de envio de forma que seja impresso um relatório para cada fornecedor em um arquivo ou que seja enviado um relatório para o endereço de e-mail de cada fornecedor. Além disso, você pode usar o diário de RFQ de cada fornecedor para gerar um relatório que você pode enviar ou reenviar a um fornecedor posteriormente. Você também pode configurar a ação Enviar, de forma que ela gere uma planilha de respostas que o fornecedor pode preencher.

Este tópico abrange o processo para tratar RFQ quando a colaboração do fornecedor não for usada. Se o sistema estiver configurado para a colaboração do fornecedor, os fornecedores poderão inserir lances diretamente no Supply Chain Management. Para obter mais informações, consulte [Colaboração de fornecedores com clientes](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations) e [Colaboração de fornecedores com fornecedores externos](vendor-collaboration-work-external-vendors.md).

Se tiver que alterar uma RFQ após enviá-la, você poderá enviá-la novamente para os fornecedores quando tiver terminado usando as duas ações de alteração: criar e finalizar.+

Ao receber lances por email, você deverá gerenciá-los lances na página **Solicitação de cotação**.

Se é necessária uma segunda iteração de uma resposta de um fornecedor, selecione **Retornar** na página **Solicitação de cotação**. A ação de retornar gera um novo diário e um relatório que serão impressos, arquivados e enviados de acordo com as configurações de impressão.

Se você adicionou critérios de pontuação ao seu caso de RFQ, a RFQ terá um painel de pontuação em que você poderá inserir as pontuações. As pontuações totais serão exibidas na RFQ e no momento em que você comparar as respostas na página **Comparar respostas**. Na página **Comparar respostas**, também é possível comparar outros dados de respostas, como preço da linha, data de entrega e o preço total.

Após escolher um lance ou número de linhas em um lance, você poderá aceitar todas ou algumas linhas e rejeitar o restante. Diários de aceitação, diários de rejeição e relatórios correspondentes são gerados e serão impressos, arquivados e enviados de acordo com as configurações de impressão. Quando você aceita um lance ou linhas específicas de um lance, um contrato de compra ou uma ordem de compra é gerada, ou uma requisição de compra é atualizada, dependendo do tipo de compra da RFQ. Você pode criar um contrato comercial que pode ser usado posteriormente para qualquer uma das respostas, independentemente de você ter aceitado ou rejeitado as respostas.

Um caso de RFQ tem dois status: o mais alto e o mais baixo. Você pode visualizar o status na página de listagem para **Todas as solicitações de cotação**. O status mais baixo é a fase menos avançada de qualquer linha no caso de RFQ, e o status mais alto é a fase mais avançada de qualquer linha no caso de RFQ. Por exemplo, se um caso de RFQ com três linhas é enviado para dois fornecedores, há duas RFQs com três linhas cada. Todas as linhas são **Enviado**. Agora, um lance é inserido de um dos fornecedores, e as linhas de RFQ obtêm o status **Recebido**. Isso significa que, das três linhas no caso de RFQ, todas elas são **Enviado** para uma RFQ e **Recebido** para outra RFQ. O status mais baixo será **Enviado,** e o mais alto é **Recebido**.

Esses status serão descritos em mais detalhes posteriormente neste tópico.

## <a name="setting-up-rfq-functionality"></a>Configurando a funcionalidade de RFQ

Antes de criar um exemplo de RFQ, é necessário configurar as informações de RFQ na página **Parâmetros de compras**. Quando você cria um exemplo de RFQ, você pode especificar os valores padrão que são copiados para a RFQ. É possível especificar os seguintes valores padrão:

-   O tipo de compra de novas RFQs: **Ordem de compra** ou **Contrato de compra**

-   A data de vencimento e a diferença de horário do dia em que o caso de RFQ foi criado

-   Tipo de solicitação, que pode ser usado como padrão a um método específico de pontuação no caso de RFQ

-   Informações de entrega e condições de pagamento

-   Campos que devem ser incluídos no lance

Você pode substituir esses valores para um exemplo específico de RFQ.

Você também deve configurar o processo de aditamento. Como parte desta configuração, você poderá ativar o bloqueio do campo. Quando o bloqueio do campo está ativado, um profissional de compras que deseja alterar uma RFQ deve selecionar primeiro **Criar** na seção **Aditamento** da guia **Cotação** no caso de RFQ. Em seguida, depois que o caso de RFQ for atualizado com o aditamento, o profissional de compras deverá concluir o processo selecionando **Finalizar**. A ação Finalizar gera uma mensagem de email que notifica os fornecedores sobre a RFQ corrigida.

Na página **Parâmetros de compra**, você seleciona o modelo a ser usado para a notificação de email que foi enviada aos fornecedores. Quando um modelo é criado em **Modelos de email**, ele poderá conter os seguintes tokens de substituição:

-   %Caso de RFQ%

-   %Motivo do retorno do lance%

-   %Motivo do aditamento%

-   %Aditamento preparado por%

-   %Empresa%

-   %Nome do caso de RFQ%

-   %Data/hora de vencimento%

-   %Data%

Os tokens %Motivo do retorno do lance% e %Motivo do aditamento% são substituídos pelo texto que o profissional de aquisição pode inserir quando ele concluir o aditamento no assistente **Aditamento**. Os valores dos tokens %Aditamento preparado por% e %Empresa% são automaticamente efetuados da RFQ. O token de %Date% é substituído na data atual.

Para cancelar uma RFQ após seu envio, é possível fazer isso no caso de RFQ. Para cancelar, um modelo de email deve enviar a notificação de cancelamento às pessoas de contato do fornecedor. O modelo deve ser selecionado na página **Parâmetros de compras**. Quando o modelo for criado, ele poderá conter os seguintes tokens de substituição:

-   %Motivo do cancelamento%

-   %Caso de RFQ%

-   %RFQ cancelada por%

-   %Empresa%

-   %Nome do caso de RFQ%

-   %Data%

O token %Motivo do cancelamento% foi substituído pelo texto que o profissional de compras pode inserir no assistente de **Cancelamento**. O token de %Date% é substituído na data atual.

Se você quiser usar os códigos de motivos em um lance para indicar o motivo de sua rejeição ou aceitação, deverá configurar os códigos de motivos na página **Motivos do fornecedor**.

Na página **Configuração de formulário** em Compras, você pode configurar a aparência de seus documentos de RFQ impressos e armazenados.

> [!NOTE]
> Para configuração do setor público, você deve usar o processo de alteração para alterar uma RFQ que já foi enviada. Quando uma RFQ é enviada, os campos são bloqueados.
Portanto, para fazer alterações na RFQ, você deve selecionar **Criar** para iniciar o processo de alteração, como descrito anteriormente. O comportamento de bloqueio é controlado pela opção **Bloquear RFQs quando forem enviadas** na página **Parâmetros de compras**. Por padrão, este parâmetro é definido como **Sim** e para uma configuração do setor público, a definição padrão não pode ser alterada. Portanto, embora o processo de alteração possa ser tratado manualmente em uma configuração do setor não público, ele deve ser usado para uma configuração do setor público.

Ao criar um caso de RFQ do tipo ordem de compra e adicionar um item de estoque à RFQ, uma transação de estoque é gerada com um status de recebimento **Recebimento de cotação**. Somente as linhas de caso de RFQ que têm esse status serão consideradas quando você usar um plano mestre para calcular os suprimentos. Se você deseja que o plano mestre inclua linhas de caso de RFQ como um recebimento esperado, configure esse comportamento na configuração do planejamento mestre.

Um gerente ou agente de compras pode criar e manter tipos de solicitações para ajustar aos requisitos de compras da organização. Cada tipo do possível pode ser associado a um método de pontuação. Os métodos de pontuação consistem em um conjunto de critérios que podem ser usados quando você pontua ofertas. Você deve configurar os tipos da solicitação, métodos de pontuação e critérios de pontuação nas páginas **Tipo de solicitação** e **Método de pontuação**.

## <a name="creating-and-sending-an-rfq"></a>Criando e enviando uma RFQ

Crie um caso de RFQ, selecione os fornecedores aos quais deseja dar lances no caso de RFQ e envie as RFQs para eles. Você pode usar as configurações de impressão para encaminhar o relatório de RFQ e os relatórios de folha de resposta ao seu destino de preferência.

Você pode criar manualmente um caso de RFQ para os tipos de compra **Ordem de compra** ou **Contrato de compra**.

Se o caso de RFQ é do tipo **Ordem de compra**, o seguinte comportamento que ocorre se diferencia dos outros tipos de casos de RFQ:

-   Quando as linhas de caso de RFQ forem criadas, as transações de estoque serão geradas com o status de recebimento **Recebimento de cotação**.

-   Quando você aceita uma oferta, uma ordem de compra é gerada.

Se o caso de RFQ é do tipo **Contrato de compra**, o seguinte comportamento que ocorre se diferencia dos outros casos de RFQ:

-   O caso de RFQ é usado para um contrato de comprar de uma quantidade ou um valor específico de produtos durante um certo período. Você deve selecionar o intervalo de datas que se aplica ao contrato de compra e o nome da pessoa que gerencia o contrato de compra.

-   Quando você aceita uma oferta, um contrato de compra é gerado.

Se um caso de RFQ for gerado a partir de uma requisição de compra, o tipo **Requisição de compra** é atribuído automaticamente. Você não pode criar manualmente um caso de RFQ do tipo **Requisição de compra**.

Você pode criar um caso de RFQ a partir de uma requisição de compra somente se o status da requisição de compra é **Em revisão**, e se você foi atribuído para executar a próxima tarefa do fluxo de trabalho. As linhas da requisição de compra são atualizadas automaticamente conforme você aceita linhas de lances (respostas de RFQ) recebidas de fornecedores. Você não pode concluir, aprovar, rejeitar nem executar outras as ações da requisição de compra até que a linha de requisição seja atualizada com uma linha de RFQ aceita ou até que o caso de RFQ seja cancelado.

Ao criar um caso de RFQ, é possível selecionar um tipo de solicitação. O tipo de solicitação determina o conjunto de critérios de pontuação que é usado para pontuar as respostas de RFQ para o caso de RFQ.

Você pode adicionar um questionário a um exemplo de RFQ. Este questionário é exibido em todas as respostas de RFQ depois que você envia a RFQ. A conclusão do questionário é uma tarefa obrigatória antes do lance ser enviado.


Há três maneiras de selecionar os fornecedores para adicionar um exemplo de RFQ:

- Adicionar os fornecedores um a um.
- Procurar todos os fornecedores que atendem aos critérios específicos.
- Adicione automaticamente todos os fornecedores que foram aprovados para as categorias de compra que são usadas nas linhas de caso de RFQ.

Quando o caso de RFQ estiver pronto, selecione **Enviar**. A ação de envio gera diários e relatórios que serão impressos, arquivados e enviados de acordo com as configurações de impressão.

Se você definir **Usar fornecedor para recalcular preços** e **Usar informações de itens específicas do fornecedor** como **Sim** na página **Enviando uma solicitação de cotação** ao enviar a RFQ para o fornecedor, algumas informações específicas do fornecedor serão inseridas automaticamente na RFQ para ele.


## <a name="amending-an-rfq-case"></a>Alterando um caso de RFQ

Às vezes, você deve alterar um caso de RFQ após enviá-lo. Você pode ter que alterar um caso de RFQ se, por exemplo, as datas de entrega forem alteradas ou se você quiser produtos adicionais ou quantidades diferentes de produtos. Você pode configurar o processo de alteração, de modo que ele seja mais ou menos restritivo.

Se você configurar o processo de alteração de modo que mais restritivo, antes de alterar os campos de um caso da RFQ que já foi enviado, selecione **Criar** no caso de RFQ para iniciar uma alteração. Depois que concluir suas alterações, selecione **Finalizar**. Você será orientado pelo processo de adicionar informações pelo email enviado para notificar os fornecedores sobre o aditamento. O relatório de RFQ atualizado, que inclui uma nota de aditamento, é automaticamente anexado ao email.

Se você configurar o processo de alteração para que seja menos restritivo, não precisará selecionar **Criar** antes de modificar os campos em um caso de RFQ que já foi enviado. Entretanto, você deve adicionar manualmente uma nota de alteração na RFQ e enviar o caso novamente. Lembre-se que esta abordagem pode ser usada somente se nenhuma de respostas (lances) forem editadas. Se você inseriu uma resposta e ela estiver em um estado **Recebido**, o botão **Enviar** não estará disponível. Nesse caso, será necessário selecionar **Criar** e **Finalizar**, como você deve fazer no processo mais restritivo. A resposta é redefinida depois para refletir as alterações no caso de RFQ.

Se os fornecedores usam a interface de colaboração de fornecedor para inserir ofertas, você sempre usar o processo de alteração para notificar fornecedores sobre alterações no caso de RFQ. Esse processo ajuda a evitar a situação em que os fornecedores dão um lance em um caso de RFQ desatualizado, enquanto o lance está em andamento. Para obter mais informações sobre colaboração do fornecedor, consulte [Colaboração do fornecedor com fornecedores externos](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors).

Se quiser convidar fornecedores adicionais para fazer o lance, e nenhuma alteração foi feita no caso de RFQ, você poderá usar o botão **Enviar**. Os fornecedores que você adicionou aparecerão na página **Enviar** e receberão o convite por email.


## <a name="receiving-and-registering-rfq-replies"></a>Receber e registrar respostas da RFQ

Quando você envia uma RFQ, uma folha de respostas é automaticamente gerada. Ao receber lances em uma RFQ, você deve inseri-los na página **Solicitação de cotação** clicando na ação **Editar resposta de RFQ.** Isso permitirá que você insira as informações do lance em um formulário dedicado à lances. Inicialmente, o **Andamento da resposta** será **Não iniciado**. Ao clicar em **Editar resposta de RFQ**, o status de andamento é **Comprador está atualizando** até que o lance seja enviado. Clique em **Enviar** depois de inserir as informações do lance. O status de progresso da resposta será alterado para **Enviado pelo comprador**. De forma semelhante, com a colaboração do fornecedor habilitada, o **Andamento da resposta** será atualizado conforme o fornecedor interagir com o lance. Em seguida, o status é alterado de **Fornecedor está atualizando** para **Enviado pelo fornecedor**. Quando o lance é enviado, um diário é criado como **Recebido**. A resposta (lance) tem que ser enviada para estar registrada quando recebida e só então ela pode ser processada como aceita ou rejeitada.

Se você precisa atualizar o lance, é necessário passar pelo mesmo processo acima e enviá-lo novamente.

Observe que é permitido editar o formulário **Solicitação de cotação** somente para as informações relacionadas ao processamento do lance, não para inserir o lance. Para inserir ou modificar o lance, clique em **Editar resposta de RFQ**.

Ao inserir as informações do lance, se o caso de RFQ permite linhas alternativas, você pode adicionar linhas alternativas para as linhas que têm somente uma categoria de compras e não têm nenhum item de catálogo especificado. Clique em **Adicionar alternativa** para adicionar linhas alternativas.

Se você inseriu uma resposta, mas requer uma nova oferta do fornecedor, você pode devolver a RFQ. Um novo diário e um relatório são gerados, que podem ser enviados ao fornecedor.

Você pode ter uma visão geral de todas as RFQs e seus status: **enviado, recebido, aceito, rejeitado, cancelado, recusado** na página **Acompanhamento da solicitação de cotação**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Aceitando e rejeitando ofertas e transferindo ofertas aceitas para os documentos downstream

Depois de identificar a melhor oferta, por exemplo, a que oferece o melhor preço total, aceite a oferta. Você pode aceitar algumas linhas em uma oferta e rejeitar outras.
Você também pode aceitar linhas de fornecedores. Esteja ciente de que se você aceitar algumas linhas, será solicitado a rejeitar todas as outras. Consequentemente, se quiser aceitar outras linhas, você deverá selecionar **Cancelar** quando solicitado. O status da resposta da RFQ para cada fornecedor que você aceitar lances ou linhas é atualizado como **Aceito**.

Se, ao preparar a ordem de compra ou o contrato de compra, você precisa adicionar uma linha ao RFQ, clique em **Adicionar linha** na grade de linha da página **Solicitação de cotação**. Você só pode visualizar e editar essa linha na página **Solicitação de cotação**. Ela estará visível na página do lance quando ele for aceito.

Quando você aceita um lance ou uma ou mais linhas em um lance, uma ordem de compra ou um contrato de compra serão gerados automaticamente. Você poderá então rejeitar os lances de todos os outros fornecedores.

Na resposta, você pode adicionar um código de motivo para explicar por que aceitou ou rejeitou uma oferta.

Ao aceitar um lance do tipo **Requisição de compra**, as linhas da requisição de compra serão atualizadas com as seguintes informações que refletem as informações do lance aceito:

-   Preço unitário

-   Percentual de desconto

-   Valor do desconto

-   Encargos de compra

-   Encargos da linha

-   Fornecedor

-  Número externo

-   Descrição externa


A tabela a seguir mostra como o status de RFQ é alterado, à medida que você aceita ou rejeita ofertas de fornecedores.

<a name="statuses--highest-and-lowest"></a>Status – o mais baixo e o mais alto
-----------------------------

Na guia Fornecedor do caso de RFQ, você pode ver as linhas com o status mais baixo e o mais alto para um determinado fornecedor. Quando o fornecedor é adicionado, e nenhuma linha foi enviada, o status mais baixo e o mais alto é <strong>Criado</strong>. Quando a RFQ é enviada ao fornecedor com todas linhas, o status das duas linhas será <strong>Enviado</strong>. Se algumas linhas em um lance de um fornecedor são aceitas e outras são rejeitadas, as linhas rejeitadas receberão o status mais baixo, que é <strong>Rejeitado</strong>, e as linhas aceitas receberão o status mais alto, que é <strong>Aceito</strong>.

Nas linhas do caso de RFQ, você pode ver o status mais alto e o mais baixo por linha em todos os fornecedores. Se você enviou uma linha para todos os fornecedores do caso de RFQ, e ninguém tenha respondido ainda, o status mais baixo e o mais alto é **Enviado**. Quando pelo menos um fornecedor responder, o estado mais alto será alterado para **Recebido**. Se você adicionar um novo fornecedor ao caso, o status mais baixo será alterado para **Criado**

O status mais alto e o mais baixo do caso de RFQ é uma agregação dos status na guia \<Fornecedor e na guia Linhas.

Os status são classificados da seguinte maneira, do mais baixo ao mais alto: criado, enviado, recebido, rejeitado, aceito, recusado, cancelado.

A tabela a seguir mostra como o status do caso de RFQ é alterado quando você cria um caso de RFQ com linhas e o envia para os fornecedores.

| **Ação**                                | **Status mais baixo do caso de RFQ** | **Status mais alto do caso de RFQ** | **Status mais baixo da linha do caso de RFQ** | **Status mais alto da linha do caso de RFQ** |
|-------------------------------------------|----------------------------|-----------------------------|---------------------------------|----------------------------------|
| Crie o cabeçalho e a linha do caso de RFQ.      | Criação em                    | Criação em                     | Criação em                         | Criação em                          |
| Envie as RFQs para todos os fornecedores do caso de RFQ. | Enviada                       | Enviada                        | Enviada                            | Enviada                             |
| Adicione outro fornecedor.                       | Criação em                    | Enviada                        | Criação em                         | Enviada                             |
| Enviar a RFQ para o segundo fornecedor.        | Enviada                       | Enviada                        | Enviada                            | Enviada                             |

Todas as linhas da RFQ relacionadas ao caso de RFQ estarão no estado **Enviado**.

A tabela a seguir mostra como o status da RFQ é alterado, conforme você recebe ofertas e registra as informações na folha de respostas da RFQ.

| **Ação**                                               | **Status mais baixo em todas as linhas de todas as RFQs** | **Status mais alto em todas as linhas de todas as RFQs** | **Status mais baixo do cabeçalho do caso de RFQ** | **Status mais alto do cabeçalho do caso de RFQ** | **Status mais baixo da linha do caso de RFQ** | **Status mais alto da linha do caso de RFQ** |
|----------------------------------------------------------|------------------------------------------------|-------------------------------------------------|-----------------------------------|------------------------------------|---------------------------------|----------------------------------|
| Registre um lance de um fornecedor a uma RFQ e a salve.        | Enviada                                           | Recebido                                        | Enviada                              | Recebido                           | Enviada                            | Recebido                         |
| Registre o segundo lance do fornecedor em uma RFQ e a salve. | Recebido                                       | Recebido                                        | Recebido                          | Recebido                           | Recebido                        | Recebido                         |


No exemplo abaixo, você pode ver o status mais alto e o mais baixo do caso de RFQ em que um lance foi recebido e o outro lance foi aceito. Quando um lance recebido for rejeitado, o status mais baixo será alterado de recebido para rejeitado no cabeçalho e na linha do caso de RFQ.


|            <strong>Ação</strong>             | <strong>Status mais baixo em todas as linhas de todas as RFQs</strong> | <strong>Status mais alto em todas as linhas de todas as RFQs</strong> | <strong>Status mais baixo do cabeçalho do caso de RFQ</strong> | <strong>Status mais alto do cabeçalho do caso de RFQ</strong> | <strong>Status mais baixo da linha do caso de RFQ</strong> | <strong>Status mais alto da linha do caso de RFQ</strong> |
|------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|------------------------------------------------|-------------------------------------------------|----------------------------------------------|-----------------------------------------------|
| Aceite uma das ofertas. (ou pelo menos uma linha) |                          Recebido                           |                           Aceita                           |                    Recebido                    |                    Aceita                     |                   Recebido                   |                   Aceita                    |
|           Rejeite todos os outros lances.           |                          Rejeitada                           |                           Aceita                           |                    Rejeitada                    |                    Aceita                     |                   Rejeitada                   |                   Aceito                    |

