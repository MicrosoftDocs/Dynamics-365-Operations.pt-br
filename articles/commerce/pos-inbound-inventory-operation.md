---
title: Operação de estoque de entrada no POS
description: Este tópico descreve os recursos da operação de entrada do estoque do ponto de venda (POS).
author: hhaines
manager: annbe
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f3dd442f979c23a87ae4b7e69a37de65d5d9bd70
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972621"
---
# <a name="inbound-inventory-operation-in-pos"></a>Operação de estoque de entrada no POS

[!include [banner](includes/banner.md)]

No Microsoft Dynamics 365 Commerce versão 10.0.10 e posterior, as operações de entrada e saída no ponto de venda (PDV) substituem a operação de separação e recebimento.

> [!NOTE]
> Na versão 10.0.10 e posteriores do Commerce, todos os novos recursos do aplicativo do PDV que estão relacionados ao recebimento do estoque da loja em relação às ordens de compra e às ordens de transferência serão adicionados à operação do PDV da **Operação de entrada**. Se você estiver usando a operação de separação e recebimento no PDV, recomendamos que você crie uma estratégia para mover-se dessa operação para as novas operações de entrada e saída. Embora a operação de separação e recebimento não seja removida do produto, não haverá mais investimentos nela, de uma perspectiva funcional ou de desempenho, após a versão 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>Pré-requisito: configurar uma estrutura de documento assíncrona

A operação de entrada inclui melhorias de desempenho para garantir que os usuários com altos volumes de lançamentos de recebimentos em diversos repositórios ou empresas e documentos de estoques grandes, possam processar esses documentos para a Sede do Commerce sem apresentar tempos limite ou falhas. Esses aperfeiçoamentos exigem o uso de uma estrutura de documento assíncrona.

Ao usar uma estrutura de documentos assíncrona, é possível confirmar alterações de documento de entrada do POS para a Sede do Commerce e, em seguida, realizar outras tarefas enquanto o processamento para a Sede do Commerce é executado em segundo plano. É possível verificar o status de um documento por meio da página da lista de documentos da **Operação de entrada** no POS para garantir que o lançamento foi bem-sucedido. No aplicativo do POS, também é possível usar a lista de documentos ativos da operação de entrada para ver todos os documentos que não foram lançados na Sede do Commerce. Se um documento falhar, os usuários do PDV poderão fazer correções e tentar novamente processá-lo para a sede do Commerce.

> [!IMPORTANT]
> A estrutura de documentos assíncrona deve ser configurada antes que uma empresa tente usar a operação de entrada no POS.

Para configurar uma estrutura de documento assíncrona, conclua os procedimentos a seguir.

### <a name="create-and-configure-a-number-sequence"></a>Criar e configurar uma sequência numérica

1. Vá para **Administração da organização \> Sequências numéricas \> Sequências numéricas**.
2. Na página **Sequências numéricas**, crie uma sequência numérica.
3. Nos campos **Código de sequência numérica** e **Nome**, insira valores definidos pelo usuário.
4. Na Guia Rápida **Referências**, selecione **Adicionar**.
5. No campo **Área**, selecione uma opção **Parâmetros do Commerce**.
4. No campo **Referência**, selecione **Identificador da operação do documento de varejo**.
5. Na Guia Rápida **Geral**, na seção **Configuração**, defina a opção **Contínuo** como **Não** para garantir que não haja problemas de desempenho.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>Criar e agendar dois trabalhos em lote para o processamento de documentos e as tarefas de monitoramento

> [!NOTE]
> No Commerce versão 10.0.13 e posterior, você não precisa configurar esses trabalhos em lotes por meio da estrutura do trabalho em lotes. Os processos em lotes podem ser configurados no menu **Retail e Commerce > TI de Varejo e Comércio**. Use as opções de menu **Monitor da operação do documento de varejo** e **Processamento da operação de documento de varejo** para configurar os trabalhos em lotes.

Os trabalhos em lotes que você criar serão usados para processar documentos que falharam ou expiram. Eles também serão usados quando o número de documentos de estoque ativos que estão sendo processados no PDV exceder um valor configurado pelo sistema.

1. Vá para **Administração do sistema \> Consultas \> Trabalhos em lotes**.
2. Na página **Trabalho em lotes**, crie dois trabalhos em lote:

    - Configure um trabalho para executar a classe **RetailDocumentOperationMonitorBatch**.
    - Configure o outro trabalho para executar a classe **RetailDocumentOperationProcessingBatch**.

2. Programar os novos trabalhos em lotes a serem executados periodicamente. Por exemplo, defina o plano para que os trabalhos sejam executados a cada cinco minutos.

## <a name="prerequisite-add-inbound-operation-to-the-pos-screen-layout"></a>Pré-requisito: adicionar a operação de entrada ao layout da tela do POS

Antes que a sua organização possa usar a funcionalidade de operação de entrada, ela deve configurar a operação do POS da **Operação de entrada** em um ou mais [layouts de tela do POS](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). Antes de implantar a nova operação em um ambiente de produção, certifique-se de testá-la exaustivamente e treine os usuários para usá-la.

## <a name="overview"></a>Visão geral

A operação de entrada permite que os usuários do POS executem as seguintes tarefas:

- Receba o estoque no estoque do repositório de documentos de ordens de compra confirmados ou de documentos de ordens de transferência enviados.
- Exiba as informações de recebimentos de estoque históricos por um período de sete dias após o documento ter sido totalmente recebido.
- Crie novas solicitações de ordem de transferência de entrada.

Quando a operação de entrada for iniciada no aplicativo do POS, uma página de listagem será exibida. Essa exibição mostra documentos da ordem de compra e da ordem de transferência em aberto contendo linhas de estoque que estão agendadas para serem recebidas pelo repositório atual. Para localizar e selecionar um documento específico, os usuários podem rolar a lista ou usar o recurso de pesquisa.

A lista de documentos do estoque de entrada tem três guias:

- **Ativo** – esta guia mostra documentos totalmente ou parcialmente em aberto e que contêm linhas ou quantidades nas linhas que ainda devem ser recebidas.
- **Rascunho** – esta guia mostra novas solicitações de ordem de transferência de entrada criadas pelo repositório. No entanto, os documentos foram salvos somente localmente. Eles ainda não foram enviados para a sede do Commerce para processamento.
- **Concluído** – esta guia mostra uma lista documentos de ordens de compra ou de ordens de transferência que o repositório recebeu totalmente nos últimos sete dias. Esta guia é meramente informativa. Todas as informações sobre os documentos são dados somente leitura da loja.

Quando você exibe documentos em qualquer uma das guias, o campo **Status** pode ajudá-lo a compreender o estágio em que o documento está.

- **Rascunho** – o documento da ordem de transferência foi salvo apenas localmente no banco de dados de canal do armazenamento. Nenhuma informação sobre a solicitação de ordem de transferência foi enviada para a sede do Commerce.
- **Solicitado** – a ordem de compra ou de transferência foi criada na Sede do Commerce e está totalmente em aberto. Nenhum recebimento foi processado em relação ao documento. Para documentos do tipo de documento da ordem de compra, o recebimento pode ser iniciado a qualquer momento enquanto o status estiver como **Solicitado**.
- **Enviado parcialmente** – o documento da ordem de transferência tem uma ou mais linhas ou quantidades de linhas parciais que foram lançadas como remetidas pelo depósito de saída. Essas linhas enviadas estão disponíveis para serem recebidas por meio da operação de entrada.
- **Totalmente remetido** – a ordem de transferência teve todas as linhas e quantidades completas de linha lançadas como foram remetidas pelo depósito de saída. O documento inteiro está disponível para ser recebido por meio da operação de entrada.
- **Parcialmente recebido** – algumas das linhas ou quantidades de linha no documento da ordem de compra ou da ordem de transferência foram recebidas pelo repositório, mas outras permanecem em aberto.
- **Totalmente recebido** – todas as linhas e as quantidades no documento da ordem de compra ou da ordem de transferência foram totalmente recebidas. Os documentos podem ser acessados somente na guia **Concluído** e no modo somente leitura para os usuários do repositório.
- **Em andamento** – esse status é usado para informar aos usuários de dispositivos que o documento está sendo trabalhado ativamente por outro usuário.
- **Em pausa** – esse status é mostrado depois que o **Recebimento de pausa** é selecionado para interromper temporariamente o processo de recebimento.
- **Processamento em HQ** – o documento foi enviado à sede do Commerce do aplicativo PDV, mas ainda não foi lançado com êxito na sede do Commerce. O documento está passando pelo processo de lançamento de documentos assíncronos. Depois que o documento for lançado com êxito na Sede do Commerce, seu status deverá ser atualizado para **Recebimento total** ou **Parcialmente recebido**.
- **Falha no processamento** – o documento foi lançado para a sede do Commerce e rejeitado. O painel **Detalhes** mostra o motivo da falha no lançamento. O documento deve ser editado para corrigir problemas de dados e, depois, deve ser reenviado para a sede do Commerce para processamento.

Quando você seleciona uma linha de documento na lista, um painel **Detalhes** é exibido. Este painel mostra informações adicionais sobre o documento, como informações de remessa e data. Uma barra de progresso mostra quantos itens ainda devem ser processados. Se o documento não tiver sido processado com êxito para a sede do Commerce, o painel **Detalhes** também mostrará mensagens de erro relacionadas à falha.

No modo de exibição página de lista de documentos, você pode selecionar **Detalhes da ordem** na barra de aplicativos para exibir os detalhes do documento. Também é possível ativar o processamento de recibos em linhas de documentos elegíveis.

Na exibição da página de listagem de documentos também é possível criar uma solicitação da ordem de transferência de entrada para um repositório. Os documentos permanecem com status **Rascunho** e podem ser ajustados ou excluídos até serem enviados para a Sede do Commerce para processamento. Depois de serem enviados para a Sede do Commerce, as linhas da ordem de transferência não serão mais alteradas no aplicativo do POS.

## <a name="receiving-process"></a>Processo de recebimento

Após selecionar um documento da ordem de compra ou da ordem de transferência na guia **Ativo**, é possível selecionar **Detalhes da ordem** para começar o processo de recebimento.

Por padrão, a exibição **Recebendo agora** é mostrada. Essa exibição é otimizada para a leitura do código de barras. Pode ser usada para criar uma lista dos itens digitalizados, para que eles possam ser recebidos. Para começar o processo de recebimento, você pode iniciar a leitura dos códigos de barras dos itens.

Conforme os códigos de barras dos itens são digitalizados na exibição **Recebendo agora**, o aplicativo valida os itens em relação ao documento da ordem de compra ou de transferência para garantir que todos os itens digitalizados correspondam a um item válido no documento. Na exibição **Recebendo agora**, presume-se que a digitalização de cada código de barras representa o recebimento da quantidade de uma unidade, a menos que a quantidade esteja vinculada ao código de barras. Você pode digitalizar códigos de barras repetidamente nessa exibição para criar uma lista contendo todos os itens e as quantidades do recebimento.

### <a name="example-scenario"></a>Cenário de exemplo

Um usuário recebe uma ordem de compra contendo 10 unidades do código de barras 5657900266. O usuário pode digitalizar esse código de barras 10 vezes para atualizar o campo **Recebendo agora** em uma unidade por leitura. Quando o usuário tiver concluído as digitalizações, o campo **Recebendo agora** da linha do item exibirá uma quantidade de 10 itens recebidos.

Como alternativa, em um cenário no qual a quantidade de itens é grande, o usuário poderá preferir inserir a quantidade de itens manualmente, em vez de digitalizar o código de barras de cada item recebido. Nesse caso, o usuário pode digitalizar o código de barras uma vez para adicionar o item à lista **Recebendo agora**. Em seguida, o usuário pode selecionar a linha associada na exibição **Recebendo agora** e, no painel **Detalhes** que aparece do lado direito da página, atualizar o campo **Quantidade de recebimento** do item.

Embora a exibição **Recebendo agora** seja otimizada para a digitalização do código de barras, os usuários também podem selecionar **Receber produto** na barra do aplicativo e, em seguida, inserir o ID do item ou os dados do código de barras usando uma caixa de diálogo. Após o item ter sido inserido e validado, o usuário será solicitado a inserir a quantidade de recebimento.

A exibição **Recebendo agora** oferece uma forma objetiva de os usuários visualizarem quais produtos estão recebendo. Como alternativa, a exibição **Lista completa da ordem** pode ser usada. Essa exibição mostra a lista completa de linhas do documento da ordem de compra ou de transferência selecionado. Os usuários podem selecionar manualmente as linhas na lista e, em seguida, no painel **Detalhes**, atualizar o campo **Quantidade de recebimento** da linha selecionada. Na exibição **Lista completa da ordem**, os usuários podem digitalizar os códigos de barras ou podem usar a função **Receber produto** para inserir o ID ou o código de barras do item, além dos dados referentes à quantidade recebida, sem ter que selecionar a linha do item correspondente na lista primeiro.

### <a name="over-receiving-validations"></a>Validações de recebimento em excesso

As validações ocorrem durante o processo de recebimento para as linhas do documento. Eles incluem validações para entrega excedente. Se um usuário tentar receber um estoque maior que o solicitado na ordem de compra, mas a entrega excedida não tiver sido configurada ou se a quantidade recebida exceder a tolerância de entrega excedida configurada para a linha da ordem de compra, o usuário receberá uma mensagem de erro e não conseguirá receber a quantidade em excesso.

O recebimento em excesso não é permitido para documentos da ordem de transferência. Os usuários sempre receberão erros se tentarem receber mais do que a quantidade que foi enviada para a linha da ordem de transferência.

### <a name="close-purchase-order-lines"></a>Fechar linhas da ordem de compra

Você pode fechar a quantidade restante em uma ordem de compra de entrada durante o processo de recebimento se a transportadora tiver confirmado que não pode remeter a quantidade total solicitada. Para fazer isso, a empresa deve ser configurada para permitir a entrega insuficiente de ordens de compra. Além disso, um percentual de entrega insuficiente deve ser definido para a linha da ordem de compra.

Para configurar a empresa para permitir a entrega insuficiente de ordens de compra, no Commerce headquarters, vá até **Compras e fornecimento** > **Configuração** > **Parâmetros de compra**. Na guia **Entrega**, ative o parâmetro **Aceitar entrega insuficiente**. Em seguida, execute o trabalho de agendamento de distribuição **1070** (**Configuração global**) para sincronizar as alterações de configurações para os canais.

Os percentuais de tolerância de entrega insuficiente para uma linha da ordem de compra podem ser predefinidos em produtos como parte das configurações do produto no Commerce headquarters. Como alternativa, eles podem ser definidos ou substituídos em uma ordem de compra específica no Commerce headquarters.

Depois que uma organização concluir a configuração da entrega insuficiente da ordem de compra, os usuários do PDV verão uma nova opção **Fechamento da quantidade restante** no painel **Detalhes** quando selecionarem uma linha da ordem de compra de entrada na operação **Estoque de entrada**. Se o usuário fechar a quantidade restante o PDV faz uma validação para verificar se a quantidade que está sendo fechada está dentro do percentual de tolerância de entrega insuficiente definido na linha da ordem de compra. Se a tolerância de entrega insuficiente for excedida, será exibida uma mensagem de erro e o usuário não poderá fechar a quantidade restante até que a quantidade recebida anteriormente, além da quantidade de **Recebendo agora** atender ou ultrapassar a quantidade mínima que precisa ser recebida, com base no percentual de tolerância de entrega insuficiente. 

Com a opção **Fechamento da quantidade restante** ativada para uma linha da ordem de compra, quando o usuário concluir o recebimento usando a ação **Concluir recebimento**, uma solicitação de fechamento também será enviada para o Commerce headquarters e qualquer quantidade não recebida dessa linha da ordem será cancelada. Nesse ponto, a linha é considerada totalmente recebida. 

### <a name="receiving-location-controlled-items"></a>Recebendo itens controlados pelo local

Se os itens que estiverem sendo recebidos forem controlados pelo local, os usuários podem selecionar o local no qual desejam receber os itens durante o processo de recebimento. Recomendamos configurar um local de recebimento padrão para o depósito de repositório, tornando esse processo mais eficiente. Mesmo se um local padrão for configurado, os usuários podem substituir o local de recebimento nas linhas selecionadas de acordo com a necessidade.

A operação respeita a configuração **Recibo em branco permitido** na dimensão de armazenamento **Local** e não requer que uma dimensão de localização seja inserida se o recebimento em branco for configurado. Se não forem permitidos locais de recebimento em branco para um item, o aplicativo de PDV mostrará um erro e exigirá que uma localização seja inserida antes que o recebimento possa ser lançado.

### <a name="receive-all"></a>Receber tudo

Conforme necessário, é possível selecionar **Remover tudo** na barra de aplicativos para atualizar rapidamente a quantidade de **Recebendo agora** de todas as linhas de documento até o valor máximo disponível a ser recebido para essas linhas.

### <a name="receipt-of-unplanned-items-on-purchase-orders"></a>Recebimento de itens não planejados em ordens de compra

Na versão 10.0.14 e posterior do Commerce, os usuários podem receber um produto que não estava originalmente na ordem de compra. Para habilitar essa funcionalidade, ative **Adicionar linhas à Ordem de Compra durante o recebimento do Ponto de Venda**.  

Este recurso só funciona para recebimento da ordem de compra. Não é possível receber itens em ordens de transferência quando os itens não foram previamente encomendados e enviados do depósito de saída.

Os usuários não poderão adicionar novos produtos à ordem de compra durante o recebimento do PDV, se a ordem de compra [fluxo de trabalho do gerenciamento de alteração](https://docs.microsoft.com/dynamics365/supply-chain/procurement/purchase-order-approval-confirmation) estiver ativado no Commerce headquarters (HQ). Para habilitar o gerenciamento de alterações, todas as alterações em uma ordem de compra devem ser aprovadas primeiro, antes que o recebimento seja permitido. Como esse processo permite que um destinatário adicione novas linhas à ordem de compra, o recebimento falhará, se o fluxo de trabalho de gerenciamento de alterações estiver habilitado. Se o gerenciamento de alterações estiver habilitado para todas as ordens de compra ou para o fornecedor vinculado à ordem de compra que está sendo recebida ativamente no PDV, o usuário não poderá adicionar novos produtos à ordem de compra durante o recebimento no PDV.

A funcionalidade que permite a adição de linhas não pode ser usada como solução para o recebimento de quantidades adicionais de produtos que já estão na ordem de compra. O recebimento em excesso é gerenciado por meio das configurações padrão [recebimento em excesso](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation#over-receiving-validations) da linha de produto na ordem de compra.

Se a opção **Adicionar linhas à Ordem de Compra durante o recebimento do Ponto de Venda** estiver ativada e um usuário estiver recebendo com a **Operação de entrada** no PDV, se o usuário digitalizar ou digitar um código de barras ou número do produto que não é reconhecido como um item na ordem de compra atual, mas é reconhecido como um item válido, o usuário recebe uma mensagem sobre a adição do item à ordem de compra. Se o usuário adicionar o item à ordem de compra, a quantidade inserida em **Recebendo agora** é considerada a quantidade encomendada para a linha da ordem de compra.

Quando o recebimento da ordem de compra é concluído e enviado para HQ para processamento, as linhas adicionadas são criadas no documento mestre da ordem de compra. Na linha da ordem de compra no HQ, haverá um sinalizador **Adicionador por PDV** na guia **Geral** da linha da ordem de compra. O sinalizador **Adicionador por PDV** indica que a linha da ordem de compra foi adicionada pelo processo de recebimento do PDV e não é uma linha que estava na ordem de compra antes do recebimento.

### <a name="cancel-receiving"></a>Cancelar recebimento

Use a função **Cancelar recebimento** na barra de aplicativos somente se quiser sair do documento sem salvar as alterações. Por exemplo, você inicialmente selecionou o documento incorreto e não deseja salvar os dados de recebimento anteriores.

### <a name="pause-receiving"></a>Pausar recebimento

Se estiver em um estoque de recebimento, é possível usar a função **Pausar recebimento** se desejar fazer um intervalo durante o processo de recebimento. Por exemplo, pode ser necessário realizar outra operação do POS, como escolher uma venda de cliente ou adiar o lançamento do recebimento.

Ao selecionar **Pausar recebimento**, o status do documento será alterado para **Pausado**. Portanto, os usuários saberão quais dados foram inseridos no documento, mas o documento ainda não foi confirmado. Quando você estiver pronto para continuar o processo de recebimento, selecione o documento pausado e, em seguida, selecione **Detalhes da ordem**. Todas as quantidades de **Recebendo agora** que foram salvas previamente estão retidas e podem ser visualizadas na exibição **Lista completa da ordem**.

### <a name="review"></a>Revisar

Antes da confirmação final do recebimento na Sede do Commerce (HQ), é possível usar a funcionalidade de revisão para validar o documento de entrada. A revisão alertará o usuário sobre quaisquer dados ausentes ou incorretos que podem provocar falha no processamento e fornecerá a oportunidade de corrigir problemas antes de enviar a solicitação de recebimento. Para habilitar a função **Revisar** na barra de aplicativos, habilite o recurso **Habilitar validação nas operações de entrada e saída do estoque no PDV** no espaço de trabalho **Gerenciamento de recursos** na Sede do Commerce (HQ).

A função **Revisar** valida os seguintes problemas em um documento de entrada:

- **Recebimento em excesso** – a quantidade recebida é maior que a quantidade encomendada. A gravidade desse problema é determinada pela configuração de entrega excedente na Sede do Commerce (HQ).
- **Recebimento insuficiente** – a quantidade recebida é menor que a quantidade encomendada. A gravidade desse problema é determinada pela configuração de entrega insuficiente na Sede do Commerce (HQ).
- **Número de série** – o número de série não é fornecido ou validado para um item serializado que requer que o número de série seja registrado no estoque.
- **Localização não definida** – a localização não é especificada para um item controlado por localização, e a localização em branco não é permitida.
- **Linhas excluídas** – as linhas da ordem foram excluídas por um usuário da Sede do Commerce (HQ) que não é conhecido pelo aplicativo de PDV.

Defina o parâmetro **Habilitar validação automática** como **Sim** em **Parâmetros do Commerce** > **Estoque** > **Estoque da loja** para executar a validação automaticamente ao selecionar **Concluir recebimento**.

### <a name="finish-receiving"></a>Concluir recebimento

Após terminar de inserir todas as quantidades dos produtos em **Recebendo agora**, selecione **Concluir recebimento** na barra de aplicativos para processar o recebimento.

Quando os usuários concluírem o recebimento de uma ordem de compra, eles serão solicitados a inserir um valor no campo **Número de recebimento**, se essa funcionalidade estiver configurada. Normalmente, esse valor é equivalente ao identificador da guia de remessa do fornecedor. Os dados do **Número do recebimento** serão armazenados no Diário de recebimento de produtos na Sede do Commerce. Os números de recebimento não são capturados para os recebimentos de ordens de transferência.

Quando o processamento assíncrono de documentos é usado, o recebimento é enviado por meio de uma estrutura de documento assíncrona. O tempo necessário para que o documento seja lançado depende do tamanho do documento (o número de linhas) e do tráfego de processamento geral que está ocorrendo no servidor. Normalmente, esse processo ocorre em questão de segundos. Se o lançamento do documento falhar, o usuário será notificado por meio da lista de documentos da **Operação de entrada**, na qual o status do documento será atualizado para **Falha do processamento**. O usuário poderá, então, selecionar o documento com falha no PDV para exibir as mensagens de erro e o motivo da falha no painel **Detalhes**. Um documento com falha permanece não lançado e requer que o usuário retorne às linhas do documento selecionando **Detalhes da ordem** no PDV. O usuário deve atualizar o documento com as correções com base nos erros. Depois que um documento for corrigido, o usuário poderá tentar processá-lo novamente selecionando **Concluir preenchimento** na barra de aplicativos.

## <a name="create-an-inbound-transfer-order"></a>Criar uma ordem de transferência de entrada

No PDV, os usuários podem criar novos documentos de ordem de transferência. Para iniciar o processo, selecione **Novo** na barra de aplicativos enquanto estiver na lista de documentos **Operação de entrada**. Em seguida, você será solicitado a selecionar um depósito ou um repositório como **Transferir de** que fornecerá o estoque para o local do repositório. Os valores são limitados à seleção definida na configuração do grupo de atendimento do armazenamento. Em uma solicitação de transferência de entrada, o repositório atual será sempre o depósito registrado em **Transferir para** na ordem de transferência. Esse valor não pode ser alterado.

Você pode inserir valores nos campos **Data de remessa** **Data de recebimento** e **Modo de entrega**, conforme necessário. Você também pode adicionar uma nota que será armazenada juntamente com o cabeçalho da ordem de transferência, como um anexo do documento na sede do Commerce.

Depois que as informações de cabeçalho são criadas, você pode adicionar produtos à ordem de transferência. Para iniciar o processo de inclusão de itens e quantidades solicitadas, selecione **Adicionar produto**. No painel de **Detalhes**, também é possível adicionar uma observação específica da linha às linhas do diário. Essas observações serão armazenadas como anexo de linhas.

Depois que as linhas forem inseridas na ordem de transferência de entrada, selecione **Salvar** para salvar as alterações de documento localmente ou **Enviar solicitação** para enviar os detalhes da ordem para a Sede do Commerce para processamento adicional. Se você selecionar **Salvar**, o documento de rascunho será armazenado no banco de dados do canal e o depósito de saída não poderá executar o documento até ter sido processado com êxito por **Solicitação de envio**. Selecione **Salvar** somente se não estiver pronto para confirmar a solicitação para o processamento da sede do Commerce.

Se um documento for salvo localmente, ele poderá ser encontrado na guia **Rascunhos** da lista de documentos **Operação de entrada**. Enquanto um documento está em um status **Rascunho**, você pode editá-lo selecionando **Editar**. Você pode atualizar, adicionar ou excluir linhas conforme necessário. Também é possível excluir o documento inteiro durante o status **Rascunho**, selecionando **Excluir** na guia **Rascunhos**.

Depois que o documento de rascunho for enviado com êxito para a sede do Commerce, ele aparecerá na guia **Ativo** e terá o status **Solicitado**. Nesse momento, os usuários no repositório ou depósito de entrada não poderão mais editar o documento da ordem de transferência de entrada solicitado. Somente os usuários no depósito de saída podem editar o documento selecionando **Operação de saída** no aplicativo do POS. O bloqueio de edição garante que nenhum conflito ocorra porque um solicitante de entrada altera a ordem de transferência ao mesmo tempo em que o remetente de saída está selecionando e enviando ativamente a ordem. Se forem necessárias alterações do armazenamento de entrada ou depósito depois que a ordem de transferência for enviada, o remetente de saída deverá ser contatado e solicitado a inserir as alterações.

Depois que o documento for definido com o status **Solicitado**, ele ficará visível na guia **Ativo**. No entanto, ainda não poderá ser recebido pelo repositório ou depósito de entrada. Depois que o depósito de saída tiver enviado algumas ou todas as ordens de transferência, o repositório ou depósito de entrada poderá lançar recebimentos no POS. Quando a saída processar os documentos da ordem de transferência, o status será atualizado de **Solicitado** para **Entregue** ou **Entrega parcial**. Depois que os documentos estiverem com status **Entregue** ou **Entrega parcial**, o repositório ou depósito de entrada poderá lançar recebimentos relacionados a eles usando o processo de recebimento da operação de entrada.

## <a name="related-topics"></a>Tópicos relacionados

[Operação de estoque de saída no POS](pos-outbound-inventory-operation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]