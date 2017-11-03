---
title: "RFQs (solicitações de cotação)"
description: "Este tópico oferece uma visão geral das RFQs (solicitações de cotação), que as organizações emitem quando precisam adquirir itens ou serviços e desejam receber ofertas competitivas de vários fornecedores."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchRFQCaseTable, PurchRFQCaseTableListPage, PurchRFQCompare, PurchRFQReplyTable, PurchRFQVendReplyTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2154
ms.assetid: 3936996e-d943-46ca-8385-84c042990f1d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8b817ffd905f1d3e99befc149416006e1a51f5e2
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="request-for-quotations-rfqs"></a>RFQs (solicitações de cotação)

[!include[banner](../includes/banner.md)]


Este tópico oferece uma visão geral das RFQs (solicitações de cotação), que as organizações emitem quando precisam adquirir itens ou serviços e desejam receber ofertas competitivas de vários fornecedores. Em uma RFQ, você solicita que os fornecedores forneçam preços e prazos de entrega das quantidades do item que você especificar. Você também pode solicitar que os fornecedores especifiquem caso haja encargos incidentais, como custos de remessa, ou quaisquer descontos para grandes pedidos ou pagamento antecipado da fatura do fornecedor.

O processo de RFQ (solicitação de cotação) cobre as seguintes tarefas:

-   Criar e enviar uma RFQ a um ou mais fornecedores.
-   Receber e registrar respostas à RFQ (cotações).
-   Transferir os lances aceitos para uma ordem de compra, um contrato de compra ou uma requisição de compra.

A ilustração a seguir fornece uma visão geral do processo de RFQ.  

[![Processo de solicitação de cotação](./media/rfq-process-458x1024.jpg)](./media/rfq-process.jpg)  

Você pode criar uma solicitação de cotação a partir das ordens planejadas, de uma requisição de compra ou uma entrada manual. A RFQ que você cria é chamada de exemplo de RFQ e esse é o documento base que você usa para emitir uma RFQ a cada fornecedor. Depois de preparar o caso de RFQ e adicionar fornecedores, clique em **Enviar** no caso RFQ, e um diário RFQ é gerado para cada fornecedor que você enviou a RFQ. Você pode configurar as configurações de gerenciamento de impressão para a ação Enviar para imprimir um relatório para cada fornecedor em um arquivo ou enviar um relatório para o endereço de e-mail de cada fornecedor. Além disso, o diário de RFQ de cada fornecedor pode ser usado para gerar um relatório que você pode enviar ou reenviar a um fornecedor posteriormente. Você também pode configurar a ação Enviar para gerar uma folha de respostas que o fornecedor possa preencher.  

Se você precisar alterar uma RFQ depois que a enviar, poderá reenviar a RFQ aos fornecedores quando terminar.  

Ao receber ofertas, você deverá incorporá-las na página **Respostas da solicitação de cotação**. Se você selecionar a opção **Copiar dados para resposta**, os dados como a quantidade e as datas dos exemplos da RFQ serão copiados na resposta. É possível alterar esses dados para refletir a oferta do fornecedor.  

Se uma segunda iteração de uma resposta for necessária para um fornecedor específico, clique em **Retornar** na página **Resposta à solicitação de cotação**. A ação Retornar gera um novo diário e um relatório que serão impressos, arquivados e enviados de acordo com as configurações de gerenciamento de impressão.  

Se você adicionou critérios de pontuação para seu exemplo de RFQ, a resposta de RFQ terá um painel de pontuação no qual você poderá inserir as contagens. As pontuações totais aparecerão quando você comparar as respostas na página **Comparar respostas**, na qual você também pode comparar outros dados de resposta, como preço da linha, data de entrega e preço total.  

Após decidir sobre uma oferta ou ofertas parciais, você poderá aceitá-las e rejeitar o restante. Os diários de aceitação, os diários de rejeição e os relatórios correspondentes são gerados. Eles serão impressos, enviados arquivados, e de acordo com as configurações de gerenciamento de impressão. Quando você aceita uma oferta ou linhas específicas de uma oferta, um contrato de compra ou ordem de compra é gerado, ou uma requisição de compra é atualizada, dependendo do tipo de compra da RFQ. Você pode criar um contrato comercial que pode ser usado posteriormente para qualquer uma das respostas, independentemente de você ter aceitado ou rejeitado as respostas.  

O status de uma RFQ é exibido no cabeçalho da RFQ e depende do status das linhas da RFQ. O status indica o quanto você processou a RFQ. Cada RFQ tem dois valores para o status: o mais baixo e o mais alto. O status mais baixo é a fase menos avançada de qualquer linha na RFQ, e o status mais alto é a fase mais avançada de qualquer linha na RFQ. Por exemplo, se o estágio menos avançado de uma RFQ for para uma linha que foi criada, o status mais baixo da RFQ será **Criado**. Se o estágio mais avançado da RFQ for para uma linha que foi enviada para fornecedores, o status mais alto da RFQ será **Enviado**. O status é atualizado automaticamente ao processar uma RFQ.  

É possível exibir os status mais alto e o mais baixo de um cabeçalho de RFQ na página **Todas as solicitações de cotação**. É possível exibir os status mais alto e o mais baixo de uma linha de RFQ na guia **Linhas** na página **Solicitação de cotação**.  

A sequência de status para processar RFQs é a seguinte:

1.  **Criado**
2.  **Enviado**
3.  **Recebido**
4.  **Aceito**/**Cancelado**/**Rejeitado**

Os status serão descritos em mais detalhes nas seções posteriores deste tópico.

## <a name="setting-up-rfq-functionality"></a>Configurando a funcionalidade de RFQ
Antes de criar um exemplo de RFQ, é necessário configurar as informações de RFQ na página **Parâmetros de compras**. Quando você cria um exemplo de RFQ, você pode especificar os valores padrão que são copiados para a RFQ. É possível especificar os seguintes valores padrão:

-   O tipo de compra de novas RFQs: **Ordem de compra** ou **Contrato de compra**.
-   Definições para data e hora de vencimento.
-   Informações de entrega e condições de pagamento
-   Campos que devem ser incluídos na resposta à RFQ.

Você pode substituir esses valores para um exemplo específico de RFQ. Você também deve configurar o processo de aditamento. Como parte desta configuração, você poderá ativar o bloqueio do campo. Quando o bloqueio do campo é ativado, um profissional de compras que deseja modificar um RFQ deve clicar primeiro em **Criar** na seção **Alteração** da guia **Cotação** . Depois que a cotação foi atualizada com a alteração, o profissional de compras deverá concluir o processo clicando em **Finalizar**. A ação **Finalizar** gera uma mensagem de email que notifica os fornecedores sobre a RFQ corrigida. Você seleciona o modelo para a notificação de email enviada aos fornecedores na página **Parâmetros de compras**. Quando um modelo for criado, ele poderá conter os seguintes tokens de substituição:

-   %Motivo do retorno do lance%
-   %Motivo do aditamento%
-   %Aditamento preparado por%
-   %Empresa%

Os tokens %Motivo do retorno do lance% e %Motivo do aditamento% são substituídos pelo texto que o profissional de aquisição pode inserir quando ele concluir o aditamento no assistente **Aditamento**. Os valores dos tokens %Aditamento preparado por% e %Empresa% são automaticamente efetuados da RFQ.  

Se quiser usar os códigos de motivo em uma resposta de RFQ para indicar o motivo pelo qual a oferta foi rejeitada ou aceita, você deverá configurar os códigos de motivo na página **Motivos do fornecedor**.  

Você pode configurar a aparência dos documentos da RFQ impressos ou armazenados na página **Configuração de formulário** em Compras. 

**Observação:** em uma configuração para o setor público, para fazer alterações em uma RFQ que já foi enviada, será necessário usar o processo de aditamento. Quando a RFQ é enviada, os campos são bloqueados, por isso, clicar em **Criar** para usar o processo de aditamento conforme descrito acima é uma etapa obrigatória para fazer alterações na RFQ.
Isso é controlado pelo parâmetro de bloqueio de campo **Bloquear RFQs quando forem enviadas** em **Parâmetros de compras e fornecimento**. Esse parâmetro está definido como **Sim** e, em uma configuração para o setor público, esse é um padrão que não pode ser alterado. Isso significa que, enquanto o processo de aditamento pode ser feito manualmente em uma configuração para outros setores, o controle de aditamentos por meio do bloqueio de campos depois do envio da RFQ é obrigatório para o setor público.

Ao criar uma RFQ para uma ordem de compra e adicionar um item de estoque à RFQ, uma transação de estoque será gerada com um status de recebimento **Recebimento de cotação**. Somente as linhas de RFQ que têm este status serão consideradas quando você usar um plano mestre para calcular os suprimentos. Se quiser que o planejamento mestre inclua linhas de RFQ como um recebimento previsto, você deve configurar esse comportamento na configuração do planejamento mestre.  

Como um gerente ou agente de compras, você pode criar e manter tipos de solicitação para corresponder aos requisitos de compras para sua organização. Cada tipo de solicitação pode levar a métodos de pontuação. Os métodos de pontuação consistem em um conjunto de critérios que podem ser usados quando você pontua ofertas. Você deve configurar os tipos da solicitação, métodos de pontuação e critérios de pontuação nas páginas **Tipo de solicitação** e **Método de pontuação**.

## <a name="creating-and-sending-an-rfq"></a>Criando e enviando uma RFQ
Você cria uma RFQ, seleciona os fornecedores que deseja cotar na RFQ e envia a RFQ aos fornecedores. Você pode usar o gerenciamento de impressão para encaminhar o relatório de RFQ e os relatórios da folha de resposta ao seu destino preferido.  

Você pode criar uma RFQ para o tipo de compra **Ordem de compra** ou **Contrato de compra**.  

Se a RFQ for gerada a partir de uma requisição de compra, o tipo de **Requisição de compra** é atribuído automaticamente. Você não pode criar manualmente uma RFQ do tipo **Requisição de compra**. Se o tipo da RFQ for **Ordem de compra**:

-   Quando as linhas da RFQ forem criadas, as transações de estoque serão geradas com o status de recebimento **Recebimento de cotação**.
-   Quando você aceita uma oferta, uma ordem de compra é gerada.

Se o tipo da RFQ for **Contrato de compra**:

-   A RFQ é usada para um contrato para comprar uma quantidade ou um valor específico de produtos durante um período. Você deve selecionar o intervalo de datas que se aplica ao contrato de compra e o nome da pessoa que gerencia o contrato de compra.
-   Quando você aceita uma oferta, um contrato de compra é gerado.

Você pode criar uma RFQ a partir de uma requisição de compra somente se o status da requisição de compra for **Em revisão** e estiver atribuído para executar a próxima tarefa de fluxo de trabalho. As linhas da requisição de compra são atualizadas automaticamente conforme você aceita linhas de resposta de RFQ (ofertas) que você recebeu dos fornecedores. Você não pode concluir, rejeitar, aprovar ou executar nenhuma outra ação na requisição de compra, enquanto a RFQ estiver em andamento.  

Quando você cria uma RFQ, é possível selecionar um tipo específico da solicitação. O tipo de solicitação determina o conjunto de critérios de pontuação que é usado para pontuar as respostas à RFQ.  

Você pode adicionar um questionário a um exemplo de RFQ. Este questionário é exibido em todas as respostas depois que você envia a RFQ.  

Há três maneiras de selecionar os fornecedores para adicionar um exemplo de RFQ:

-   Adicionar os fornecedores um a um.
-   Procurar todos os fornecedores que atendem aos critérios específicos.
-   Adicionar automaticamente todos os fornecedores que foram aprovados para as categorias de compra que são usadas em linhas da RFQ.

Quando o exemplo da RFQ estiver pronto, clique em **Enviar**. A ação Enviar gera diários e relatórios que serão impressos, arquivados e enviados de acordo com as configurações de gerenciamento de impressão.  

Se você marcou as caixas de seleção **Usar fornecedor para recalcular preços** e **Usar informações de item específicas do fornecedor** na página **Enviando uma solicitação de cotação** quando você enviar a solicitação para os fornecedores, algumas informações específicas do fornecedor serão inseridas automaticamente. Você pode alterar essas informações na página **Resposta à solicitação de cotação**.  

A tabela a seguir mostra como o status de RFQ é alterado quando você cria uma RFQ e a envia aos fornecedores.

|                                    |                              |                                                 |                            |                             |
|------------------------------------|------------------------------|-------------------------------------------------|----------------------------|-----------------------------|
| **Ação**                         | **Status mais baixo de cabeçalho de RFQ** | **Status mais alto de cabeçalho de RFQ**                   | **Status mais baixo de linha de RFQ** | **Status mais alto de linha de RFQ** |
| Crie o cabeçalho da RFQ e alinhe-o.    | Criada em                      | Criada em                                         | Criada em                    | Criada em                     |
| Envie a RFQ para um fornecedor específico. | Enviada                         | Enviada                                            | Enviada                       | Enviada                        |
| Adicione outro fornecedor.                | Criada em                      | Enviada (a RFQ foi enviada a apenas um fornecedor). | Criado em                    | Enviada                        |
| Enviar a RFQ para o segundo fornecedor. | Enviada                         | Enviada                                            | Enviada                       | Enviada                        |

**Observação:** É possível adicionar mais fornecedores a uma RFQ a qualquer momento, e os status mais alto e mais baixo se alteram para refletir novos fornecedores. Por exemplo, se você tiver recebido ofertas de todos os fornecedores e aceitado pelo menos uma linha de uma oferta, o status mais baixo do cabeçalho de RFQ será **Rejeitado** e o status mais alto será **Aceito**. Se você adicionar um novo fornecedor, o status mais baixo em qualquer linha agora será **Criado**. Dessa forma, o status mais baixo do cabeçalho de RFQ será alterado para **Criado** e o status mais alto permanece **Aceito**.

## <a name="amending-an-rfq"></a>Alterando um RFQ
Ocasionalmente, você deve alterar uma RFQ após enviá-la. Por exemplo, isso pode ocorrer se as datas de entrega foram alteradas, ou se você quiser produtos adicionais ou quantidades diferentes de produtos. Você pode configurar o processo de aditamento, de modo que ele seja mais ou menos restritivo.  

Se usar o processo mais restritivo de aditamento, você deve clicar em **Criar** no exemplo de RFQ para iniciar uma alteração antes que possa alterar os campos no exemplo da RFQ. Depois que terminar de fazer as alterações, clique em **Finalizar**. Você será orientado pelo processo de adicionar informações pela mensagem de email enviada para notificar fornecedores sobre o aditamento. O relatório de RFQ atualizado, que inclui uma nota de aditamento, é automaticamente anexado à mensagem.  

Se você usar o processo menos restritivo de aditamento, você não precisa criar um aditamento antes de alterar os campos em um exemplo da RFQ que já foi enviado. No entanto, você deve adicionar manualmente uma nota de aditamento na RFQ.

## <a name="receiving-and-registering-rfq-replies"></a>Receber e registrar respostas da RFQ
Quando você envia uma RFQ, uma folha de respostas é automaticamente gerada. Ao receber respostas (ofertas) a uma RFQ, é necessário inserir as informações de cada fornecedor em uma planilha de resposta de RFQ específica do fornecedor. Se você adicionou critérios de pontuação, você poderá marcar as respostas. Em seguida, você compara as ofertas dos fornecedores e as classifica, de acordo com critérios de pontuação, como o melhor preço total ou melhor prazo de entrega total.  

Se um questionário estiver anexado ao caso de RFQ, você deverá inserir manualmente as respostas das perguntas na folha de respostas.  

Se você tiver que inserir linhas alternativas, e o exemplo de RFQ permitir isso, na Guia Rápida **Linhas de cotação de compra**, clique em **Adicionar linha**. Em seguida, insira informações sobre o produto, como o número do item ou a categoria de compras, quantidade, preço e desconto.  

Se você inseriu uma resposta mas requer uma nova oferta de fornecedor, você pode reenviar a cotação. Isso irá gerar um novo diário e relatório que você pode usar para solicitar alterações do fornecedor.  

Você pode ver uma visão geral de todas as RFQs e seus status de resposta na página **Acompanhamento da solicitação de cotação**.  

A tabela a seguir mostra como o status da RFQ é alterado, conforme você recebe ofertas e registra as informações na folha de respostas da RFQ.

|                                                |                       |                        |                              |                               |                            |                             |
|------------------------------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Ação**                                     | **Status mais baixo da oferta** | **Status mais alto da oferta** | **Status mais baixo de cabeçalho de RFQ** | **Status mais alto de cabeçalho de RFQ** | **Status mais baixo de linha de RFQ** | **Status mais alto de linha de RFQ** |
| Registre a oferta de um fornecedor e a salve.        | Enviada                  | Recebido               | Enviada                         | Recebido                      | Enviada                       | Recebido                    |
| Registre a segunda oferta de um fornecedor e a salve. | Recebido              | Recebido               | Recebido                     | Recebido                      | Recebido                   | Recebido                    |

**Observação:** Se você devolver uma oferta a um fornecedor para negociação adicional, os status mais baixo e o mais alto permanecerão como **Recebido**.

### <a name="accepting-and-rejecting-bids-and-transferring-accepted-bids-to-downstream-documents"></a>Aceitando e rejeitando ofertas e transferindo ofertas aceitas para os documentos downstream

Depois de identificar a melhor oferta, por exemplo, a que oferece o melhor preço total, aceite a oferta. O status da resposta de RFQ para esse fornecedor é atualizado para **Aceito**. Quando você aceita uma oferta ou linhas específicas em uma oferta, uma ordem de compra ou um contrato de compra são gerados automaticamente, e você pode rejeitar as ofertas de outros fornecedores.  

Quando você aceita uma resposta RFQ que tem um tipo de **Requisição de compra**, as linhas da resposta de RFQ atualizam as linhas de requisição de compra com as seguintes informações:

-   Preço unitário
-   Percentual de desconto
-   Valor do desconto
-   Encargos de compra
-   Encargos da linha
-   Fornecedor
-   Número externo
-   Descrição externa

Na resposta, você pode adicionar um código de motivo para explicar por que aceitou ou rejeitou uma oferta.  

Você pode aceitar algumas linhas em uma oferta e rejeitar outras. Você também pode aceitar linhas de fornecedores. Esteja ciente de que se você aceitar algumas linhas, será solicitado a rejeitar todas as outras. Consequentemente, se quiser aceitar outras linhas, você deverá clicar em **Cancelar** quando você receber o aviso.  

A tabela a seguir mostra como o status de RFQ é alterado, à medida que você aceita ou rejeita ofertas de fornecedores.

|                         |                       |                        |                              |                               |                            |                             |
|-------------------------|-----------------------|------------------------|------------------------------|-------------------------------|----------------------------|-----------------------------|
| **Ação**              | **Status mais baixo da oferta** | **Status mais alto da oferta** | **Status mais baixo de cabeçalho de RFQ** | **Status mais alto de cabeçalho de RFQ** | **Status mais baixo de linha de RFQ** | **Status mais alto de linha de RFQ** |
| Aceite uma das ofertas. | Recebido              | Aceito               | Recebido                     | Aceito                      | Recebido                   | Aceito                    |
| Rejeite as outras ofertas.  | Rejeitada              | Aceito               | Rejeitada                     | Aceito                      | Rejeitada                   | Aceito                    |






