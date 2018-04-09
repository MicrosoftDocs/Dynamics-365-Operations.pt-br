---
title: "Solicitações de cotação (RFQs)"
description: "Este tópico fornece uma visão geral das solicitações de cotação (RFQs). As organizações emitem RFQs quando desejam receber ofertas competitivas de vários fornecedores para os itens ou serviços que eles compram."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: b86363004b8702d1a654f2a1da49bba82fc8ff2a
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="requests-for-quotation-rfqs"></a>Solicitações de cotação (RFQs)

[!include[banner](../includes/banner.md)]

Este tópico fornece uma visão geral das solicitações de cotação (RFQs). As organizações emitem RFQs quando desejam receber ofertas competitivas de vários fornecedores para os itens ou serviços que eles compram. Em uma RFQ, você solicita que os fornecedores forneçam preços e prazos de entrega das quantidades do item que você especificar. Você também pode solicitar que os fornecedores especifiquem caso haja encargos incidentais, como custos de remessa, ou quaisquer descontos para grandes pedidos ou pagamento antecipado da fatura do fornecedor.

O processo de RFQ consiste nas seguintes tarefas:

1. Criar e enviar uma RFQ a um ou mais fornecedores.
2. Receber e registrar respostas à RFQ (lances)
3. Transferir os lances aceitos para uma ordem de compra, um contrato de compra ou uma requisição de compra.

A ilustração a seguir mostra uma visão geral do processo de RFQ.

[![Processo RFQ](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)

Você pode criar uma RFQ de ordens planejadas, de uma requisição de compra ou de uma entrada manual. A RFQ criada é chamada de caso RFQ. O caso de RFQ é o documento base que você usa para emitir uma RFQ a cada fornecedor.

Após preparar o caso de RFQ e adicionar os fornecedores, selecione **Enviar** no caso de RFQ. Um diário de RFQ é gerado para cada fornecedor para o qual você enviou a RFQ. Você pode definir as configurações de gerenciamento de impressão para a ação Enviar, de forma que seja impresso um relatório para cada fornecedor em um arquivo ou enviado um relatório para o endereço de e-mail de cada fornecedor. Além disso, você pode usar o diário de RFQ de cada fornecedor para gerar um relatório que você pode enviar ou reenviar a um fornecedor posteriormente. Você também pode configurar a ação Enviar, de forma que ela gere uma planilha de respostas que o fornecedor pode preencher.

Este tópico abrange o processo para tratar RFQ quando a colaboração do fornecedor não for usada. Se o sistema estiver configurado para a colaboração do fornecedor, os fornecedores poderão inserir lances diretamente no Microsoft Dynamics 365 for Finance and Operations. Para obter mais informações, consulte [Colaboração de fornecedores com clientes](vendor-collaboration-work-customers-dynamics-365-operations.md).
 
Se tiver que alterar uma RFQ após enviá-la, você pode reenviar a RFQ aos fornecedores quando tiver terminado, usando as duas ações de alteração: Criar e finalizar.

Ao receber lances por email, você deverá inseri-los na página **Respostas da solicitação de cotação**. Se você selecionar a opção **Copiar dados para resposta**, os dados como a quantidade e as datas dos exemplos da RFQ serão copiados na resposta. É possível alterar esses dados para refletir a oferta do fornecedor.

Se uma segunda iteração de uma resposta for necessária para um fornecedor, selecione **Retornar** na página **Resposta à solicitação de cotação**. A ação Retornar gera um novo diário e um relatório que serão impressos, arquivados e enviados, de acordo com as configurações de gerenciamento de impressão.

Se você adicionou critérios de pontuação para seu exemplo de RFQ, a resposta de RFQ terá um painel de pontuação no qual você poderá inserir as contagens. As pontuações totais serão exibidas quando você comparar as respostas na página **Comparar respostas**. Nessa página, também é possível comparar outros dados da resposta, como linha preço, data de entrega e o preço total.

Após escolher um lance ou lances parciais, você poderá aceitá-los e rejeitar o restante. Diários de aceitação, diários de rejeição e relatórios correspondentes são gerados e serão impressos, arquivados e enviados de acordo com suas definições de gerenciamento de impressão. Quando você aceita um lance ou linhas específicas de um lance, um contrato de compra ou uma ordem de compra é gerada, ou uma requisição de compra é atualizada, dependendo do tipo de compra da RFQ. Você pode criar um contrato comercial que pode ser usado posteriormente para qualquer uma das respostas, independentemente de você ter aceitado ou rejeitado as respostas.

O status de uma RFQ é exibido no cabeçalho da RFQ e depende do status das linhas da RFQ. O status indica o quanto você processou da RFQ. Cada RFQ tem dois valores para o status: um status mais baixo e um mais alto. O status mais baixo é a fase menos avançada de qualquer linha na RFQ, e o status mais alto é a fase mais avançada de qualquer linha na RFQ. Por exemplo, se o estágio menos avançado de uma RFQ for para uma linha que foi criada, o status mais baixo da RFQ será **Criado**. Se o estágio mais avançado da RFQ for para uma linha que foi enviada para fornecedores, o status mais alto da RFQ será **Enviado**. O status é atualizado automaticamente ao processar uma RFQ.

É possível exibir os status mais alto e o mais baixo de um cabeçalho de RFQ na página **Todas as solicitações de cotação**. É possível exibir os status mais alto e o mais baixo de uma linha de RFQ na guia **Linhas** na página **Solicitação de cotação**.

Aqui está a sequência de status para processamento de RFQ:

1. **Criado**
2. **Enviada**
3. **Recebido**
4. **Aceita**, **Cancelada** ou **Rejeitada**

Esses status serão descritos em mais detalhes posteriormente neste tópico.

## <a name="setting-up-rfq-functionality"></a>Configurando a funcionalidade de RFQ

Antes de criar um exemplo de RFQ, é necessário configurar as informações de RFQ na página **Parâmetros de compras**. Quando você cria um exemplo de RFQ, você pode especificar os valores padrão que são copiados para a RFQ. É possível especificar os seguintes valores padrão:

- O tipo de compra de novas RFQs: **Ordem de compra** ou **Contrato de compra**
- A data e a hora de vencimento
- Informações de entrega e condições de pagamento
- Os campos que devem ser incluídos na resposta à RFQ

Você pode substituir esses valores para um exemplo específico de RFQ.

Você também deve configurar o processo de aditamento. Como parte desta configuração, você poderá ativar o bloqueio do campo. Quando o bloqueio do campo é ativado, um profissional de compras que deseja modificar uma RFQ deve clicar primeiro em **Criar** na seção **Alteração** da guia **Cotação**. Em seguida, depois que a RFQ for atualizada com a alteração, o profissional de compras deverá concluir o processo clicando em **Finalizar**. A ação Finalizar gera uma mensagem de email que notifica os fornecedores sobre a RFQ corrigida.

Na página **Parâmetros de compra**, você seleciona o modelo a ser usado para a notificação de email que foi enviada aos fornecedores. Quando um modelo for criado, ele poderá conter os seguintes tokens de substituição:

- %Caso de RFQ%
- %Motivo do retorno do lance%
- %Motivo do aditamento%
- %Aditamento preparado por%
- %Empresa%
- %Nome do caso de RFQ%
- %ExpiryDateTime%
- %Data%

Os tokens %Motivo do retorno do lance% e %Motivo do aditamento% são substituídos pelo texto que o profissional de aquisição pode inserir quando ele concluir o aditamento no assistente **Aditamento**. Os valores dos tokens %Aditamento preparado por% e %Empresa% são automaticamente efetuados da RFQ. O token de %Date% é substituído na data atual.

Um modelo de email também é necessário se você cancelar uma RFQ depois de enviada. Esse modelo de email é usado para enviar notificação de cancelamento às pessoas de contato do fornecedor. O modelo deve ser selecionado na página **Parâmetros de compras**. Quando o modelo for criado, ele poderá conter os seguintes tokens de substituição:

- %Motivo do cancelamento%
- %Caso de RFQ% 
- %RFQ cancelada por%
- %Empresa%
- %Nome do caso de RFQ%
- %Data%

O token %Motivo do cancelamento% foi substituído pelo texto que o profissional de compras pode inserir no assistente de **Cancelamento**. O token de %Date% é substituído na data atual.

Se quiser usar os códigos de motivo em uma resposta de RFQ para indicar o motivo pelo qual a oferta foi rejeitada ou aceita, você deverá configurar os códigos de motivo na página **Motivos do fornecedor**.

Na página **Configuração de formulário** em Compras, você pode configurar a aparência de seus documentos de RFQ impressos e armazenados.

> [!NOTE]
> Para configuração do setor público, você deve usar o processo de alteração para alterar uma RFQ que já foi enviada. Quando uma RFQ é enviada, os campos são bloqueados. Portanto, para fazer alterações na RFQ, você deve selecionar **Criar** para iniciar o processo de alteração, como descrito anteriormente. O comportamento de bloqueio é controlado pela opção **Bloquear RFQs quando forem enviadas** na página **Parâmetros de compras**. Por padrão, este parâmetro é definido como **Sim** e para uma configuração do setor público, a definição padrão não pode ser alterada. Portanto, embora o processo de alteração possa ser tratado manualmente em uma configuração do setor não público, ele deve ser usado para uma configuração do setor público.

Ao criar uma RFQ para uma ordem de compra e adicionar um item de estoque à RFQ, uma transação de estoque será gerada com um status de recebimento **Recebimento de cotação**. Somente as linhas de RFQ que têm este status serão consideradas quando você usar um plano mestre para calcular os suprimentos. Se quiser que o planejamento mestre inclua linhas de RFQ como um recebimento previsto, você deve configurar esse comportamento na configuração do planejamento mestre.

Um gerente ou agente de compras pode criar e manter tipos de solicitações para ajustar aos requisitos de compras da organização. Cada tipo do possível pode ser associado a um método de pontuação. Os métodos de pontuação consistem em um conjunto de critérios que podem ser usados quando você pontua ofertas. Você deve configurar os tipos da solicitação, métodos de pontuação e critérios de pontuação nas páginas **Tipo de solicitação** e **Método de pontuação**.

## <a name="creating-and-sending-an-rfq"></a>Criando e enviando uma RFQ

Você cria uma RFQ, seleciona os fornecedores que deseja cotar na RFQ e envia a RFQ aos fornecedores. Você pode usar o gerenciamento de impressão para encaminhar o relatório de RFQ e os relatórios da folha de resposta ao seu destino preferido.

Você pode criar uma RFQ para o tipo de compra **Ordem de compra** ou **Contrato de compra**.

Se a RFQ for do tipo **Ordem de compra**, o seguinte comportamento ocorre:

- Quando as linhas da RFQ forem criadas, as transações de estoque serão geradas com o status de recebimento **Recebimento de cotação**.
- Quando você aceita uma oferta, uma ordem de compra é gerada.

Se a RFQ for do tipo **Contrato de compra**, o seguinte comportamento ocorre:

- A RFQ é usada para um contrato para comprar uma quantidade ou um valor específico de produtos durante um período. Você deve selecionar o intervalo de datas que se aplica ao contrato de compra e o nome da pessoa que gerencia o contrato de compra.
- Quando você aceita uma oferta, um contrato de compra é gerado.

Se a RFQ for gerada a partir de uma requisição de compra, o tipo de **Requisição de compra** é atribuído automaticamente. Você não pode criar manualmente uma RFQ do tipo **Requisição de compra**.

Você pode criar uma RFQ a partir de uma requisição de compra, somente se o status da requisição de compra for **Em revisão** e estiver atribuído para executar a próxima tarefa de fluxo de trabalho. As linhas da requisição de compra são atualizadas automaticamente, conforme você aceita linhas de respostas de RFQ (lances) que você recebeu dos fornecedores. Você não pode concluir, rejeitar, aprovar ou executar nenhuma outra ação na requisição de compra, enquanto a RFQ estiver em andamento.

Quando você cria uma RFQ, é possível selecionar um tipo de solicitação. O tipo de solicitação determina o conjunto de critérios de pontuação que é usado para pontuar as respostas à RFQ.

Você pode adicionar um questionário a um exemplo de RFQ. Este questionário é exibido em todas as respostas depois que você envia a RFQ.

Há três maneiras de selecionar os fornecedores para adicionar um exemplo de RFQ:

- Adicionar os fornecedores um a um.
- Procurar todos os fornecedores que atendem aos critérios específicos.
- Adicionar automaticamente todos os fornecedores que foram aprovados para as categorias de compra que são usadas em linhas da RFQ.

Quando o caso de RFQ estiver pronto, selecione **Enviar**. A ação Enviar gera diários e relatórios que serão impressos, arquivados e enviados de acordo com as configurações de gerenciamento de impressão.

Se você definir **Usar fornecedor para recalcular preços** e **Usar informações de item específicos do fornecedor** como **Sim** na página **Enviando uma solicitação de cotação** quando você enviar a RFQ aos fornecedores, algumas informações específicas do fornecedor serão inseridas automaticamente. Você pode alterar essas informações na página **Resposta à solicitação de cotação**.

A tabela a seguir mostra como o status de RFQ é alterado quando você cria uma RFQ e a envia aos fornecedores.

| Ação                             | Status mais baixo de cabeçalho de RFQ | Status mais alto de cabeçalho de RFQ                        | Status mais baixo de linha de RFQ | Status mais alto de linha de RFQ |
|------------------------------------|--------------------------|--------------------------------------------------|------------------------|-------------------------|
| Crie o cabeçalho da RFQ e alinhe-o.    | Criada em                  | Criada em                                          | Criada em                | Criada em |
| Envie a RFQ para um fornecedor específico. | Enviada                     | Enviada                                             | Enviada                   | Enviada |
| Adicione outro fornecedor.                | Criada em                  | Enviada (a RFQ foi enviada a apenas um fornecedor). | Criada em                | Enviada |
| Enviar a RFQ para o segundo fornecedor. | Enviada                     | Enviada                                             | Enviada                   | Enviada |

> [!NOTE]
> É possível adicionar mais fornecedores a uma RFQ a qualquer momento, e os status mais alto e mais baixo serão atualizados para refletir novos fornecedores. Por exemplo, se você tiver recebido ofertas de todos os fornecedores e aceitado pelo menos uma linha de uma oferta, o status mais baixo do cabeçalho de RFQ será **Rejeitado** e o status mais alto será **Aceito**. Se você adicionar um novo fornecedor, o status mais baixo em qualquer linha agora será **Criado**. Dessa forma, o status mais baixo do cabeçalho de RFQ será atualizado para **Criado** mas o status mais alto permanecerá **Aceito**.

## <a name="amending-an-rfq"></a>Alterando um RFQ

Ocasionalmente, você deve alterar uma RFQ após enviá-la. Você pode alterar uma RFQ se, por exemplo, as datas de entrega foram alteradas, ou se você quiser produtos adicionais ou quantidades diferentes de produtos. Você pode configurar o processo de alteração, de modo que ele seja mais ou menos restritivo.

Se você configurar o processo de alteração de modo que mais restritivo, antes de alterar os campos de um caso da RFQ que já foi enviado, selecione **Criar** no caso de RFQ para iniciar uma alteração. Depois que concluir suas alterações, selecione **Finalizar**. Você será orientado pelo processo de adicionar informações pelo email enviado para notificar os fornecedores sobre o aditamento. O relatório de RFQ atualizado, que inclui uma nota de aditamento, é automaticamente anexado ao email.

Se você configurar o processo de alteração para que seja menos restritivo, não precisará selecionar **Criar** antes de modificar os campos em um caso de RFQ que já foi enviado. Entretanto, você deve adicionar manualmente uma nota de alteração na RFQ e enviar o caso novamente. Lembre-se que esta abordagem pode ser usada somente se nenhuma de respostas (lances) forem editadas. Se você inseriu uma resposta e ela estiver em um estado **Recebido**, o botão **Enviar** não estará disponível. Nesse caso, será necessário selecionar **Criar** e **Finalizar**, como você deve fazer no processo mais restritivo. A resposta é redefinida depois para refletir as alterações no caso de RFQ. 

Se os fornecedores usam a interface de colaboração de fornecedor para inserir ofertas, você sempre usar o processo de alteração para notificar fornecedores sobre alterações no caso de RFQ. Esse requisito ajuda a evitar a situação na qual os fornecedores oferecem um lance em um caso de RFQ desatualizado, enquanto a oferta está em andamento. Para obter mais informações sobre colaboração do fornecedor, consulte [Colaboração do fornecedor com fornecedores externos](vendor-collaboration-work-external-vendors.md). 

Se quiser convidar fornecedores adicionais para fazer o lance, e nenhuma alteração foi feita no caso de RFQ, você poderá usar o botão **Enviar**. Os fornecedores que você adicionou aparecerão na página **Enviar** e receberão o convite por email.

## <a name="receiving-and-registering-rfq-replies"></a>Receber e registrar respostas da RFQ

Quando você envia uma RFQ, uma folha de respostas é automaticamente gerada. Ao receber respostas (ofertas) a uma RFQ, é necessário inserir as informações de cada fornecedor em uma planilha de resposta de RFQ específica do fornecedor. Se adicionou critérios de pontuação, você poderá pontuar as respostas. Em seguida, você compara as ofertas dos fornecedores e as classifica, de acordo com critérios de pontuação, como o melhor preço total ou melhor prazo de entrega total.

Se um questionário estiver anexado ao caso de RFQ, você deverá inserir manualmente as respostas das perguntas na folha de respostas.

Você também pode inserir linhas alternativas, se o caso de RFQ permitir linhas alternativas. Na Guia Rápida **Linhas de cotação de compras**, selecione **Adicionar linha**. Em seguida, insira informações sobre o produto, como o número do item ou a categoria de compras, quantidade, preço e desconto.

Se você inseriu uma resposta mas requer uma nova oferta de fornecedor, você pode reenviar a cotação. Serão gerados um novo diário e um relatório e você poderá usá-los para solicitar alterações do fornecedor.

Você pode ver uma visão geral de todas as RFQs e seus status de resposta na página **Acompanhamento da solicitação de cotação**.

A tabela a seguir mostra como o status da RFQ é alterado, conforme você recebe ofertas e registra as informações na folha de respostas da RFQ.

| Ação                                         | Status mais baixo da oferta | Status mais alto da oferta | Status mais baixo de cabeçalho de RFQ | Status mais alto de cabeçalho de RFQ | Status mais baixo de linha de RFQ | Status mais alto de linha de RFQ |
|------------------------------------------------|-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Registre um lance de um fornecedor e salve-o.        | Enviada              | Recebido           | Enviada                     | Recebido                  | Enviada                   | Recebido |
| Registre o segundo lance do fornecedor e salve-o. | Recebido          | Recebido           | Recebido                 | Recebido                  | Recebido               | Recebido |

> [!NOTE]
> Se você devolver um lance de um fornecedor para negociação adicional, os status mais baixo e o mais alto permanecerão **Recebidos**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Aceitando e rejeitando ofertas e transferindo ofertas aceitas para os documentos downstream

Depois de identificar a melhor oferta, por exemplo, a que oferece o melhor preço total, aceite a oferta. Você pode aceitar algumas linhas em uma oferta e rejeitar outras. Você também pode aceitar linhas de fornecedores. Esteja ciente de que se você aceitar algumas linhas, será solicitado a rejeitar todas as outras. Consequentemente, se quiser aceitar outras linhas, você deverá selecionar **Cancelar** quando solicitado. O status da resposta da RFQ para cada fornecedor que você aceitar lances ou linhas é atualizado como **Aceito**. 

Quando você aceita um lance ou linhas específicas em um lance, uma ordem de compra ou um contrato de compra será gerado automaticamente. Você poderá então rejeitar os lances de todos os outros fornecedores.

Na resposta, você pode adicionar um código de motivo para explicar por que aceitou ou rejeitou uma oferta.

Quando você aceita uma resposta RFQ que tem um tipo de **Requisição de compra**, as linhas da resposta de RFQ atualizam as linhas de requisição de compra com as seguintes informações:

- Preço unitário
- Percentual de desconto
- Valor do desconto
- Encargos de compra
- Encargos da linha
- Fornecedor
- Número externo
- Descrição externa

A tabela a seguir mostra como o status de RFQ é alterado, à medida que você aceita ou rejeita ofertas de fornecedores.

| Ação                      | Status mais baixo da oferta | Status mais alto da oferta | Status mais baixo de cabeçalho de RFQ | Status mais alto de cabeçalho de RFQ | Status mais baixo de linha de RFQ | Status mais alto de linha de RFQ |
|-------------------------    |-------------------|--------------------|--------------------------|---------------------------|------------------------|-------------------------|
| Aceite uma das ofertas.     | Recebido          | Aceita           | Recebido                 | Aceita                  | Recebido               | Aceita |
| Rejeite todos os outros lances.  | Rejeitada          | Aceita           | Rejeitada                 | Aceita                  | Rejeitada               | Aceito |

