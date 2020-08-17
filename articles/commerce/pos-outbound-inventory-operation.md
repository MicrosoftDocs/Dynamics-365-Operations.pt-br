---
title: Operação de estoque de saída no POS
description: Este tópico descreve os recursos da operação de saída do estoque do ponto de venda (POS).
author: hhaines
manager: annbe
ms.date: 07/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 026d25717dec8c5633f19fe63c6d6f64284d322d
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646150"
---
# <a name="outbound-inventory-operation-in-pos"></a>Operação de estoque de saída no POS

[!include [banner](includes/banner.md)]


No Microsoft Dynamics 365 Commerce versão 10.0.10 e posterior, as operações de entrada e saída no ponto de venda (PDV) substituem a operação de separação e recebimento.

> [!NOTE]
> Na versão 10.0.10 e posteriores, todos os novos recursos do aplicativo do POS que estão relacionados ao recebimento do estoque do repositório em relação às ordens de compra e às ordens de transferência serão adicionados à operação de Operações de entrada. Se você estiver usando a operação de separação e recebimento no PDV, recomendamos que você crie uma estratégia para mover-se dessa operação para as novas operações de entrada e saída. Embora a operação de separação e recebimento não seja removida do produto, não haverá mais investimentos nela, de uma perspectiva funcional ou de desempenho, após a versão 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Pré-requisito: configurar uma estrutura de documento assíncrona

A operação de saída inclui melhorias de desempenho para garantir que os usuários com altos volumes de lançamentos de recebimentos em diversas lojas ou empresas e documentos de estoques grandes, possam processar esses documentos para a Sede do Commerce (HQ) sem apresentar tempos limite ou falhas. Esses aperfeiçoamentos exigem o uso de uma estrutura de documento assíncrona.

Ao usar uma estrutura de documentos assíncrona, é possível confirmar alterações de documento de saída do PDV para a Sede do Commerce (HQ) e, em seguida, realizar outras tarefas enquanto o processamento para a Sede do Commerce (HQ) é executado em segundo plano. É possível verificar o status do documento por meio da página da lista de documentos da **Operação de saída** no POS para garantir que o lançamento foi bem-sucedido. No aplicativo do PDV, também é possível usar a lista de documentos ativos da operação de saída para ver todos os documentos que não foram lançados na Sede do Commerce (HQ). Se um documento falhar, os usuários do PDV poderão fazer correções e tentar novamente processá-lo para a sede da Sede do Commerce (HQ).

> [!IMPORTANT]
> A estrutura de documentos assíncrona deve ser configurada antes que uma empresa tente usar a operação de saída no POS.

Para configurar uma estrutura de documento assíncrona, conclua os procedimentos a seguir.

### <a name="create-and-configure-a-number-sequence"></a>Criar e configurar uma sequência numérica

1. Vá para **Administração da organização \> Sequências numéricas \> Sequências numéricas**.
2. Na página **Sequências numéricas**, crie uma sequência numérica.
3. Nos campos **Código de sequência numérica** e **Nome**, insira valores definidos pelo usuário.
4. Na Guia Rápida **Referências**, selecione **Adicionar**.
5. No campo **Área**, selecione uma opção **Parâmetros do Commerce**.
6. No campo **Referência**, selecione **Identificador da operação do documento de varejo**.
7. Na Guia Rápida **Geral**, na seção **Configuração**, defina a opção **Contínuo** como **Não** para garantir que não haja problemas de desempenho.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Criar e agendar dois trabalhos em lote para o processamento de documentos e as tarefas de monitoramento

> [!NOTE]
> No Commerce versão 10.0.13 e posterior, você não precisa configurar os trabalhos em lotes por meio da estrutura do trabalho em lotes. Os processos em lotes podem ser configurados no menu **Retail e Commerce > TI de Varejo e Comércio**. Use as opções de menu **Monitor da operação do documento de varejo** e **Processamento da operação de documento de varejo** para configurar os trabalhos em lotes

Os trabalhos em lotes que você criar serão usados para processar documentos que falharam ou expiram. Eles também serão usados quando o número de documentos de estoque ativos que estão sendo processados no PDV exceder um valor configurado pelo sistema.

1. Vá para **Administração do sistema \> Consultas \> Trabalhos em lotes**.
2. Na página **Trabalho em lotes**, crie dois trabalhos em lote:

    - Configure um trabalho para executar a classe **RetailDocumentOperationMonitorBatch**.
    - Configure o outro trabalho para executar a classe **RetailDocumentOperationProcessingBatch**.

3. Programar os novos trabalhos em lotes a serem executados periodicamente. Por exemplo, defina o plano para que os trabalhos sejam executados a cada cinco minutos.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>Pré-requisito: adicionar a operação de saída ao layout da tela do POS

Antes que a sua organização possa usar a funcionalidade de operação de saída, ela deve configurar a operação do POS da **Operação de saída** em um ou mais [layouts de tela do POS](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Antes de implantar a nova operação em um ambiente de produção, certifique-se de testá-la exaustivamente e treine os usuários para usá-la.

## <a name="overview"></a>Visão geral

A operação de saída permite que os usuários do POS executem as seguintes tarefas:

- Lançar remessas para documentos de ordem de transferência nos casos em que o armazenamento do usuário é o depósito de saída designado.
- Exiba informações sobre remessas históricas da ordem de transferência que foram lançadas pelo armazenamento.
- Crie novas solicitações de ordem de transferência de saída.

Quando a operação de saída for iniciada no aplicativo do POS, uma página de listagem será exibida. Essa exibição mostra documentos da ordem de transferência em aberto contendo linhas de estoque que a loja atual do usuário tem como intenção enviar e preencher. Para localizar um documento específico, os usuários podem rolar a lista ou usar o recurso de pesquisa.

A lista de documentos do estoque de saída tem três guias.

- **Ativo** – Esta guia mostra ordens de transferência cujo status é **Solicitado** ou **Parcialmente enviado**. As ordens contêm linhas ou quantidades nas linhas que devem ser enviadas pelo armazenamento atual do usuário. Essa guia também mostra ordens que têm um status de **Processamento na HQ** (ou seja, estão aguardando a confirmação do lançamento bem-sucedido na sede do Commerce (HQ)) ou **Falha no processamento** (isto é, o lançamento para a sede do Commerce (HQ) não foi bem-sucedido e o usuário deve corrigir os dados e tentar enviar as ordens novamente).
- **Rascunho** – esta guia mostra novas solicitações de ordem de transferência de saída criadas pela loja do usuário. No entanto, os documentos foram salvos somente localmente. Eles ainda não foram enviados para a sede da Sede do Commerce (HQ) para processamento.
- **Concluído** – esta guia mostra uma lista de documentos de ordens de transferência que o repositório enviou totalmente nos últimos sete dias. Esta guia é meramente informativa. Todas as informações sobre os documentos são dados somente leitura da loja.

Quando você exibe documentos em qualquer uma das guias, o campo **Status** pode ajudá-lo a compreender o estágio em que o documento está.

- **Rascunho** – o documento da ordem de transferência foi salvo apenas localmente no banco de dados de canal do armazenamento. Nenhuma informação sobre a solicitação de ordem de transferência foi enviada para a sede da Sede do Commerce (HQ).
- **Solicitado** – a ordem de compra ou de transferência foi criada na Sede do Commerce (HQ) e está totalmente em aberto. O armazenamento atual do usuário ainda foi processado em remessas do documento.
- **Enviado parcialmente** – o documento da ordem de transferência tem uma ou mais linhas ou quantidades de linhas parciais que foram lançadas como remetidas pelo depósito de saída. Essas linhas enviadas estão disponíveis para serem recebidas por meio da operação de entrada.
- **Totalmente remetido** – a ordem de transferência teve todas as linhas e quantidades completas de linha lançadas como foram remetidas pelo depósito de saída.
- **Em andamento** – esse status é usado para informar aos usuários de dispositivos que o documento está sendo trabalhado ativamente por outro usuário.
- **Em pausa** – esse status é mostrado depois que o **Recebimento de pausa** é selecionado para interromper temporariamente o processo de recebimento.
- **Processamento em HQ** – o documento foi enviado à sede da Sede do Commerce (HQ) do aplicativo PDV, mas ainda não foi lançado com êxito na sede da Sede do Commerce (HQ). O documento está passando pelo processo de lançamento de documentos assíncronos. Depois que o documento for lançado com êxito na Sede do Commerce (HQ), seu status deverá ser atualizado para **Recebimento total** ou **Parcialmente recebido**.
- **Falha no processamento** – o documento foi lançado para a sede da Sede do Commerce (HQ) e rejeitado. O painel **Detalhes** mostra o motivo da falha no lançamento. O documento deve ser editado para corrigir problemas de dados e, depois, deve ser reenviado para a sede da Sede do Commerce (HQ) para processamento.

Quando você seleciona uma linha de documento na lista, um painel **Detalhes** é exibido. Este painel mostra informações adicionais sobre o documento, como informações de remessa e data. Uma barra de progresso mostra quantos itens ainda devem ser processados. Se o documento não tiver sido processado com êxito para a sede da Sede do Commerce (HQ), o painel **Detalhes** também mostrará mensagens de erro relacionadas à falha.

No modo de exibição página de lista de documentos, você pode selecionar **Detalhes da ordem** na barra de aplicativos para exibir os detalhes do documento. Também é possível ativar o processamento de recibos em linhas de documentos elegíveis.

Na exibição da página de listagem de documentos também é possível criar uma ordem de transferência de saída para um repositório.

## <a name="transfer-order-shipping-process"></a>Processo de envio da ordem de transferência

Após selecionar um documento da ordem de transferência na guia **Ativo**, é possível selecionar **Detalhes da ordem** para começar o processo de preenchimento do recebimento. A **Lista de ordem completa** é exibida. Esta página mostra todas as linhas de documento que contêm o item. Também mostra detalhes da quantidade encomendada.

Cada verificação de um código de barras atualiza a quantidade no campo **Enviando agora** por uma unidade. Como alternativa, você pode inserir uma quantidade de remessa, selecionando **Enviar produto** na barra de aplicativos, inserindo uma ID de item e inserindo a quantidade. Se o item for controlado por local, você poderá confirmar ou definir o local de remessa da linha do documento.

Na exibição **Lista de ordem completa**, você pode selecionar manualmente uma linha na lista e depois atualizar a quantidade **Enviando agora** da linha selecionada no painel **Detalhes**.

### <a name="over-delivery-shipping-validations"></a>Validações de remessa de entrega excedente

As validações ocorrem durante o processo de recebimento para as linhas do documento. Eles incluem validações para entrega excedente. Se um usuário tentar receber um estoque maior que o solicitado na ordem de compra, mas a entrega excedida não tiver sido configurada ou se a quantidade recebida exceder a tolerância de entrega excedida configurada para a linha da ordem de compra, o usuário receberá uma mensagem de erro e não conseguirá receber a quantidade em excesso.

### <a name="underdelivery-close-lines"></a>Linhas de fechamento insuficiente

No Commerce versão 10.0.12, a funcionalidade foi adicionada, que permite aos usuários do PDV fechar ou cancelar quantidades restantes durante a remessa da ordem de saída se o depósito de saída determinar que ele não pode remeter a quantidade total solicitada. As quantidades também podem ser fechadas ou canceladas posteriormente. Para usar esse recurso, a empresa deve ser configurada para permitir a entrega de ordens de transferência. Além disso, uma porcentagem de entrega insuficiente deve ser definida para a linha da ordem de transferência.

Para configurar a empresa para permitir a subentrega de ordens de transferência, na Sede do Commerce (HQ), vá para **Gerenciamento de estoque \> Configuração \> Parâmetros de gerenciamento de estoque e depósito**. Na página **Parâmetros de gerenciamento de estoque e de depósito**, na guia **Transferir pedidos**, ative o parâmetro **Aceitar entrega insuficiente**. Em seguida, execute o trabalho do agendador de distribuição **1070** para sincronizar as alterações de parâmetro no canal de armazenamento.

As porcentagens de entrega insuficiente para uma linha da ordem de transferência podem ser predefinidas em produtos como parte da configuração do produto na Sede do Commerce. Como alternativa, eles podem ser definidos ou substituídos em uma linha de ordem de transferência específica por meio da Sede do Commerce (HQ).

Depois que uma organização concluir a configuração da entrega insuficiente da ordem de transferência, os usuários do PDV verão uma nova opção **Fechamento da quantidade restante** no painel **Detalhes** quando selecionarem uma linha da ordem de transferência de saída na função **Operação de saída**. Quando o usuário concluir a remessa usando a operação **Conclusão final**, poderão enviar uma solicitação aa Sede do Commerce (HQ) para cancelar a quantidade não remetida restante. Se o usuário fechar a quantidade pendente, o Commerce faz uma validação para verificar se a quantidade que está sendo cancelada está dentro da tolerância da porcentagem de entrega insuficiente definida na linha da ordem de transferência. Se a tolerância de entrega insuficiente for ultrapassada, uma mensagem de erro será exibida e o usuário não poderá fechar a quantidade restante até que a quantidade remetida e a quantidade "remeter agora" atendam ou ultrapassem a tolerância de entrega insuficiente.

Depois que a remessa é sincronizada com a Sede do Commerce (HQ), as quantidades definidas no campo **Remeter agora** para a linha da ordem de transferência no PDV são atualizadas para um status remetido na Sede do Commerce (HQ). Todas as quantidades não remetidas que anteriormente teriam sido consideradas como "quantidades de remessa restantes" (ou seja, as quantidades que serão remetidas posteriormente) serão consideradas as quantidades canceladas. A quantidade de "remessa restante" para a linha da ordem de transferência é definida como **0** (zero) e a linha é considerada totalmente remetida.

### <a name="shipping-location-controlled-items"></a>Enviando itens controlados pelo local

Se os itens que estiverem sendo enviados forem controlados pelo local, os usuários podem escolher o local no qual desejam emitir o o estoque durante o processo de envio. Recomendamos configurar um local de saída padrão para o depósito de loja, tornando esse processo mais eficiente. Mesmo se um local padrão for configurado, os usuários podem substituir o local de saída nas linhas selecionadas de acordo com a necessidade.

A operação respeita a configuração **Recibo em branco permitido** na dimensão de armazenamento **Local** e não requer que uma dimensão de localização seja inserida se o recebimento em branco for configurado. Se não forem permitidos locais de recebimento em branco para um item, o aplicativo de PDV mostrará um erro e exigirá que uma localização seja inserida antes que o recebimento possa ser lançado.

### <a name="ship-all"></a>Remeter tudo

Conforme necessário, é possível selecionar **Enviar tudo** na barra de aplicativos para atualizar rapidamente a quantidade de **Enviando agora** de todas as linhas de documento até o valor máximo disponível a ser preenchido para essas linhas.

### <a name="cancel-fulfillment"></a>Cancelar atendimento

Use a função **Cancelar preenchimento** na barra de aplicativos somente se quiser sair do documento sem salvar as alterações. Por exemplo, você inicialmente selecionou o documento incorreto e não deseja salvar os dados de envio anteriores.

### <a name="pause-fulfillment"></a>Pausar atendimento

Se estiver preenchendo a ordem de transferência, é possível usar a função **Pausar preenchimento** se desejar fazer um intervalo durante o processo. Por exemplo, pode ser necessário realizar outra operação de PDV, como escolher uma venda de cliente ou adiar o lançamento do envio à sede da Sede do Commerce (HQ).

Ao selecionar **Pausar preenchimento**, o status do documento será alterado para **Pausado**. Portanto, o usuário saberá quais dados foram inseridos no documento, mas o documento ainda não foi confirmado. Quando você estiver pronto para continuar o processo de preenchimento, selecione o documento pausado e, em seguida, selecione **Detalhes da ordem**. Todas as quantidades de **Enviando agora** que foram salvas previamente serão retidas e podem ser visualizadas na exibição **Lista completa da ordem**.

### <a name="review"></a>Revisar

Antes da confirmação final do preenchimento na Sede do Commerce (HQ), é possível usar a função **Revisão** para validar o documento de saída. Essa função alerta o usuário sobre possíveis dados ausentes ou incorretos que podem provocar uma falha no processamento e fornecerá a oportunidade de corrigir problemas antes de enviar a solicitação de preenchimento. Para habilitar a função **Revisar** na barra de aplicativos, habilite o recurso **Habilitar validação nas operações de entrada e saída do estoque no PDV** no Gerenciamento de recursos na Sede do Commerce (HQ).

A função **Revisar** valida os seguintes problemas em um documento de saída:
- **Remessa em excesso** – a quantidade remetida é maior que a quantidade encomendada. A gravidade desse problema é determinada pela configuração de entrega excedente na Sede do Commerce (HQ).
- **Remessa insuficiente** – a quantidade remetida é menor que a quantidade encomendada. A gravidade desse problema é determinada pela configuração de entrega insuficiente na Sede do Commerce (HQ).
- **Número de série** – o número de série não é fornecido ou não está disponível para um item serializado que requer que um número de série seja registrado no estoque.
- **Localização não definida** – a localização não é especificada para um item controlado por localização, e a localização em branco não é permitida.
- **Linhas excluídas** – as linhas da ordem foram excluídas por um usuário da Sede do Commerce (HQ) que não é conhecido pelo aplicativo de PDV.

Se você definir o parâmetro **Habilitar validação automática** como **Sim** em **Parâmetros do Commerce** > **Estoque** > **Estoque da loja**, a validação será executada automaticamente ao selecionar a função **Concluir preenchimento**.

### <a name="finish-fulfillment"></a>Concluir atendimento

Após terminar de inserir todas as quantidades dos produtos em **Enviando agora**, selecione **Concluir preenchimento** na barra de aplicativos para processar o recebimento.

Quando o processamento assíncrono de documentos é usado, o recebimento é enviado por meio de uma estrutura de documento assíncrona. O tempo necessário para que o documento seja lançado depende do tamanho do documento (o número de linhas) e do tráfego de processamento geral que está ocorrendo no servidor. Normalmente, esse processo ocorre em questão de segundos. Se o lançamento do documento falhar, o usuário será notificado por meio da lista de documentos da **Operação de saída** na guia **Ativo**, na qual o status do documento será atualizado para **Falha do processamento**. O usuário poderá, então, selecionar o documento com falha no PDV para exibir as mensagens de erro e o motivo da falha no painel **Detalhes**. Um documento com falha permanece não lançado e requer que o usuário retorne às linhas do documento selecionando **Detalhes da ordem** no PDV. O usuário deve atualizar o documento com as correções com base nos erros. Depois que um documento for corrigido, o usuário poderá tentar processá-lo novamente selecionando **Concluir preenchimento** na barra de aplicativos.

## <a name="create-an-outbound-transfer-order"></a>Criar uma ordem de transferência de saída

No PDV, os usuários podem criar novos documentos de ordem de transferência. Para iniciar o processo, selecione **Novo** na barra de aplicativos enquanto estiver na lista de documentos **Operação de saída**. Em seguida, você será solicitado a selecionar um depósito ou um repositório como **Transferir para** para o qual sua loja enviará o estoque. Os valores são limitados à seleção definida na configuração do grupo de atendimento do armazenamento. Em uma solicitação de transferência de saída, o repositório atual será sempre o depósito registrado em **Transferir de** na ordem de transferência. Esse valor não pode ser alterado.

Você pode inserir valores nos campos **Data de remessa** **Data de recebimento** e **Modo de entrega**, conforme necessário. Você também pode adicionar uma nota que será armazenada juntamente com o cabeçalho da ordem de transferência, como um anexo do documento na Sede do Commerce (HQ).

Depois que as informações de cabeçalho são criadas, você pode adicionar produtos à ordem de transferência. Para iniciar o processo de inclusão de itens e quantidades solicitadas, leia o código de barras ou selecione **Adicionar produto**.

Depois que as linhas forem inseridas na ordem de transferência de saída, selecione **Salvar** para salvar as alterações de documento localmente ou **Enviar solicitação** para enviar os detalhes da ordem para a Sede do Commerce (HQ) para processamento adicional. Se você selecionar **Salvar**, o documento de rascunho será armazenado no banco de dados do canal e o depósito de saída não poderá executar o documento até ter sido processado com êxito por **Solicitação de envio**. Selecione **Salvar** somente se não estiver pronto para confirmar a solicitação para o processamento da Sede do Commerce (HQ).

Se um documento for salvo localmente, ele poderá ser encontrado na guia **Rascunhos** da lista de documentos **Operação de entrada**. Enquanto um documento está em um status**Rascunho**, você pode editá-lo selecionando **Editar**. Você pode atualizar, adicionar ou excluir linhas conforme necessário. Também é possível excluir o documento inteiro durante o status **Rascunho**, selecionando **Excluir** na guia **Rascunhos**.

Depois que o documento de rascunho for enviado com êxito para a Sede do Commerce (HQ), ele aparecerá na guia **Ativo** e terá o status **Solicitado**. Nesse momento, somente os usuários no depósito de saída podem editar o documento selecionando **Operação de saída** no aplicativo do POS. Os usuários no depósito de entrada podem exibir a ordem de transferência na guia **Ativo** da lista de documentos **Operação de entrada**, mas não podem editá-la nem excluí-la. O bloqueio de edição garante que nenhum conflito ocorra porque um solicitante de entrada altera a ordem de transferência ao mesmo tempo em que o remetente de saída está selecionando e enviando ativamente a ordem. Se forem necessárias alterações do armazenamento de entrada ou depósito depois que a ordem de transferência for enviada, o remetente de saída deverá ser contatado e solicitado a inserir as alterações.

Depois que o documento estiver com o status **Solicitado**, ele está pronto para o processamento de preenchimento pelo depósito de saída. Conforme a remessa é processada usando a operação de saída, o status dos documentos de ordem de transferência é atualizado a partir de **Solicitado** para **Totalmente remetido** ou **Parcialmente remetido**. Depois que os documentos estiverem com status **Totalmente remetido** ou **Entrega parcial**, o repositório ou depósito de entrada poderá lançar recebimentos relacionados a eles usando o processo de recebimento da operação de entrada.

As ordens de transferência totalmente remetidas são movidas para a guia **Concluído** da lista de documentos **Operação de saída**. Ali, eles permanecem visíveis para os usuários no depósito ou armazenamento de saída, no modo somente leitura, por sete dias.

## <a name="related-topics"></a>Tópicos relacionados

[Operação de estoque de entrada no POS](pos-inbound-inventory-operation.md)
