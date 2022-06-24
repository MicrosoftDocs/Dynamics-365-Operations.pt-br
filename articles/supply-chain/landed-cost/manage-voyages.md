---
title: Gerenciar viagens
description: Este artigo descreve como trabalhar com viagens. Uma viagem normalmente representa uma embarcação. No entanto, dependendo de suas práticas e procedimentos, ela pode representar um fornecedor, uma ordem de compra ou outro item que faz sentido para sua organização.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 43f28a7e30dbbe15bb02d26483289f25515fcfca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905853"
---
# <a name="manage-voyages"></a>Gerenciar viagens

[!include [banner](../../includes/banner.md)]

Uma viagem normalmente representa uma embarcação. No entanto, dependendo de suas práticas e procedimentos, ela pode representar um fornecedor, uma ordem de compra ou outro item que faz sentido para sua organização.

A página **Todas as viagens** fornece detalhes da viagem, informações de entrega e custos, e informações sobre itens, ordens de compra e ordens de transferência. Para abrir a página **Todas as viagens**, acesse **Custo de entrega \> Viagens \> Todas as viagens**. Esta página mostra uma lista de todas as viagens atuais. Você pode usar os botões no Painel de Ações para criar, excluir e trabalhar com viagens. Selecione uma viagem na lista para exibir detalhes.

> [!NOTE]
> Os contêineres de remessa e os fólios estão vinculados a uma viagem. As linhas de compra são vinculadas a um contêiner de remessa. Se os contêineres de remessa e os fólios estiverem desativados, eles também poderão ser vinculados diretamente a uma viagem. Além disso, os custos inseridos aqui são distribuídos para todas as linhas de compra associadas.

## <a name="action-pane"></a>Painel de Ação

O Painel de Ações da página **Viagens** fornece botões que permitem trabalhar com uma viagem selecionada. Cada botão executa uma única ação. O Painel de Ações também inclui guias; cada uma, por sua vez, fornece um conjunto de botões relacionados. Exceto onde indicado, todos os botões e guias estão disponíveis na exibição de lista da página **Todas as viagens** e na exibição detalhada de uma única viagem selecionada.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Botões que aparecem diretamente no Painel de Ações

A tabela a seguir descreve os botões disponíveis diretamente no Painel de Ações.

| Botão | Descrição |
|---|---|
| Criar | Crie uma viagem. <!-- KFM: Link to scenario --> |
| Excluir | Exclua a viagem atual. Somente as viagens com o status *Confirmado* podem ser excluídas. Após deixar a porta e processar as mercadorias em trânsito, a viagem não poderá mais ser excluída. |
| Editor de viagens | Abra a página **Editor de viagens**, em que você pode adicionar ou remover linhas de compra para a viagem, criar novos contêineres e modificar detalhes da própria viagem. |
| Custos de viagem | Abre a página **Custos de viagem**, em que você pode exibir e adicionar custos de viagem para todas as mercadorias na viagem. Quando os custos de viagem são adicionados manualmente à viagem, eles são adicionados automaticamente à página **Consulta de custos** e distribuídos a cada mercadoria de acordo com o método especificado na página **Custos de viagens**. |

### <a name="buttons-on-the-voyage-tab"></a>Botões na guia Viagem

A tabela a seguir descreve os botões disponíveis na guia **Viagem** do Painel de Ações. Esta guia estará disponível apenas quando você estiver trabalhando na exibição de lista da página **Todas as viagens**.

| Botão | Descrição |
|---|---|
| Contêiner de remessa | Abra uma página que mostre todos os contêineres de remessa associados à viagem selecionada. Pode haver um ou vários contêineres. |
| Fólio | Abra uma página que mostre todos os fólios associados à viagem selecionada. Pode haver um ou vários fólios. |

### <a name="buttons-on-the-manage-tab"></a>Botões na guia Gerenciar

A tabela a seguir descreve as ações disponíveis na guia **Gerenciar** do Painel de Ações.

| Botão | descrição |
|---|---|
| Documentos recebidos | Atualize a viagem para que a opção **Documentos recebidos** seja definida como *Sim*. Você pode usar este botão para bloquear o item e/ou a linha de compra para que ele não possa ser atualizado. |
| Em trânsito | Atualize o campo **Status da viagem** com o status em trânsito estabelecido na página **[Parâmetros de custo de entrega](landed-cost-parameters.md)**. Não há mais lógica neste processo. Uma viagem também pode ser atualizada automaticamente com o status em trânsito, com base nas configurações do [Centro de controle de acompanhamento](delivery-information-setup.md).
| Pronto para avaliação de custo | Atualize o campo **Status da viagem** com o status pronto para avaliação de custo estabelecido na página **[Parâmetros de custo de entrega](landed-cost-parameters.md)**. Uma viagem poderá ser orçada quando todas as faturas forem processadas (as faturas de estoque e de custo da viagem) e as mercadorias forem recebidas. Se os custos estimados associados a uma viagem não tiverem sido orçados, ocorrerá um erro quando você tentar processar a avaliação de custo de uma viagem. |
| Orçado | Limpe as irregularidades de avaliação de custo após a existência de uma fatura para todas as ordens de compra e custos com viagens. Quando você seleciona este botão, a caixa de diálogo **Atualização de viagem - Orçado** é exibida. Você pode optar por lançar na data financeira padrão ou especificar uma data de lançamento e, em seguida, executar a ação. É possível reexecutar a ação quantas vezes você quiser. Você também pode usar a caixa de diálogo **Atualização de viagem - Orçado** para estabelecer uma agenda para executar a ação como uma tarefa periódica (trabalho em lotes). Recomendamos que você execute regularmente a ação, configurando-a como um trabalho em lotes. |
| Lançar lista de recibos | Lance uma lista de recebimentos para todas as linhas de ordem de compra na viagem.  |
| Lançar recebimento de produto | Lance um recebimento de produtos para todas as linhas de ordem de compra na viagem. O processo de recebimento de produtos para as linhas da ordem de compra associadas a uma viagem será usado apenas se as mercadorias **não** passarem por processamento de mercadorias em trânsito. Se as mercadorias passarem por processamento de mercadorias em trânsito, você receberá um erro quando tentar lançar o recebimento de produtos para uma linha da ordem de compra.  |
| Lançar fatura | Lance uma fatura para todas as linhas de ordem de compra na viagem. Se as mercadorias da viagem passarem por processamento de mercadorias em trânsito, as linhas da ordem de compra serão faturadas antes da realização do processo de recebimento. Quando a ordem de compra original for faturada, as ordens de mercadorias em trânsito associadas com as linhas da ordem de compra original serão criadas. Essas ordens podem ser recebidas pelo depósito.  |
| Remeter ordem de transferência | Lance uma viagem de ordem de transferência para todas as linhas de ordem de transferência na viagem. Quando este botão for selecionado, somente as ordens de transferência estarão disponíveis para atualização. |
| Receber ordem de transferência | Lance um recebimento de ordem de transferência para todas as linhas de ordem de transferência na viagem. |
| Receber mercadorias em trânsito | Receba todas as linhas de ordem que estão em trânsito na viagem. Este botão é uma das três opções disponíveis para o recebimento de mercadorias em trânsito em uma viagem. (As outras duas opções são o botão **Criar diário de entrada**, descrito posteriormente nesta tabela, e o aplicativo móvel do Gerenciamento de Depósito). Esta opção é a mais simples e processará as mercadorias em trânsito do depósito de mercadorias em trânsito para o depósito de destino final. Se você desejar ter mais controle do processo, use o diário de entrada ou um dispositivo móvel para processar o recebimento de mercadorias. |
| Localizar custos automáticos | Localize os custos relevantes da viagem. Se esses custos já tiverem sido encontrados ou atualizados, você receberá a seguinte mensagem: "Há linhas de custo não faturadas. Deseja substituí-los?" Qualquer custo não associado à viagem no momento da criação será encontrado. Os custos de viagem associados a uma viagem e que foram faturados não serão substituídos. |
| Criar diário de entrada | <p>Abra a caixa de diálogo **Criar diário de entrada**, na qual você pode criar um diário de entrada que especifica uma localização. A caixa de diálogo fornece as seguintes opções:</p><ul><li>**Criar a partir de mercadorias em trânsito** ou **Criar a partir da ordem de transferência** – o rótulo dessa opção é alterado de acordo com o uso do processo de mercadorias em trânsito. Defina-o como *Sim* para abrir uma página de diário de entrada que permita processar um diário de entrada padrão para as mercadorias em trânsito associadas à viagem. Se o item já foi recebido no depósito de destino final, ele não será adicionado às linhas do diário de entrada.</li><li>**Inicializar quantidade** – defina esta opção como *Sim* para inicializar a quantidade que será recebida, com base na quantidade de mercadorias especificada na linha de viagem. Se a linha de viagem tiver sido parcialmente recebida, essa quantidade será a quantidade pendente. Recomendamos definir essa opção como *Sim*.</li><li>**Criar a partir de linhas da ordem** – defina esta opção como *Sim* para usar o valor das linhas da ordem.</li></ul><p>Este botão é uma das três opções disponíveis para o recebimento de mercadorias em uma viagem. (As outras opções são o botão **Receber mercadorias em trânsito** descrito anteriormente nesta tabela e no aplicativo móvel do Gerenciamento de Depósito.)</p> |
| Acumular custos | Você pode acumular custos em que um tipo de custo tenha uma conta contábil especificada para o débito. Este botão geralmente é usado quando o estoque está em trânsito ou quando as mercadorias são recebidas e faturadas. |
| Custos agregados | Mova os custos do nível do contêiner de remessa para o nível de viagem. Você pode usar este botão em um cenário de serviços compartilhados/remessa, em que várias entidades compartilham um contêiner de remessa ou um espaço de caixa. Por exemplo, a viagem tem um contêiner de remessa de 12 metros e um contêiner de remessa de 6 metros, e a divisão é feita pelo volume. Neste caso, as mercadorias/entidades que compartilham ou usam o espaço no contêiner de remessa de 6 metros podem ser penalizadas. Para distribuir os custos de forma justa, algumas organizações podem desejar transferir os custos para a viagem e distribuí-los com base no método de divisão em nível de viagem. |
| Alterar modelo de percurso | Abra uma caixa de diálogo em que você possa alterar o modelo de viagem. Depois que você alterar o modelo, os custos de viagem serão excluídos. Portanto, talvez seja necessário selecionar **Localizar custos automáticos** (consulte a descrição anteriormente nesta tabela) ou adicionar custos manualmente novamente. |

### <a name="buttons-on-the-general-tab"></a>Botões na guia Geral

A tabela a seguir descreve os botões disponíveis na guia **Geral** do Painel de Ações.

| Botão | Descrição |
|---|---|
| Lista de recebimentos | Abra uma lista de recebimentos de produtos para todas as linhas de ordem de compra na viagem.  Se nenhuma lista de recebimento de produtos tiver sido processada, este botão não estará disponível. |
| Recebimento de produtos | Abra o registro de recebimento de produtos para as linhas da ordem de compra associadas à viagem, caso esse registro seja usado. Se nenhum recebimento de produtos tiver sido lançado, este botão não estará disponível. O processo de recebimento de produtos não será usado se você estiver usando o processamento de mercadorias em trânsito. |
| Entrada de item | Abra o diário de entrada de itens, se for usado. |
| Rastreamento | Abra a página **Acompanhamento de entrada**, na qual você pode atualizar a data de chegada esperada de mercadorias em um contêiner de remessa e uma viagem e, depois, atualizar as datas de entrega esperadas de linhas da ordem de compra. |
| Consulta de custos | <p>Abre a página **Consulta de custos**, que mostra todos os custos de uma viagem.</p><p>Selecione **Exibir** no Painel de Ações para ajustar a exibição. Você pode exibir qualquer um dos níveis, mais o item e o código de tipo de custo.</p><p>Somente os códigos de tipo de custo relacionados diretamente às transações de estoque aparecem na página **Consulta de custos**. Ao remover códigos de tipo de custo, você pode ajustar a página agrupando custos juntos. Esse recurso poderá ser útil se você estiver usando tamanhos e cores.</p><p>A página **Consulta de custos** mostra somente códigos de tipo de custo em que o campo **Débito** está definido como *Item*.</p> |
| Ordens de mercadorias em trânsito | Abra a página **Ordens de mercadorias em trânsito**, que mostra os registros de mercadorias em trânsito somente para a viagem selecionada. |

## <a name="lines-view"></a>Exibição de linhas

Para abrir o modo de exibição **Linhas**, abra uma viagem e selecione a guia **Linhas** no canto superior direito do título viagem.

### <a name="information-on-the-voyage-header-fasttab"></a>Informações na FastTab Cabeçalho da viagem

A FastTab **Cabeçalho da viagem** na exibição **Linhas** de uma viagem contém informações básicas que descrevem a viagem. Muitos dos campos que aparecem nessa FastTab também aparecem no modo de exibição **Cabeçalho**, conforme descrito posteriormente neste artigo.

### <a name="information-on-the-voyage-lines-fasttab"></a>Informações na FastTab Linhas da viagem

A FastTab **Linhas da viagem** no modo de exibição **Linhas** de uma viagem está relacionada aos detalhes da viagem e informações de avaliação de custo que se aplicam ao nível de viagem. Aqui, você pode revisar os contêineres de remessas, fólios e itens que estão anexados à viagem. O preço e a quantidade dos itens na viagem também são mostrados. Você pode exibir um contêiner de remessa ou fólio listado ao selecionar o link relevante.

### <a name="information-on-the-line-details-fasttab"></a>Informações na FastTab Detalhes da linha

A FastTab **Detalhes da linha** no modo de exibição **Linhas** de uma viagem fornece mais informações sobre a linha selecionada no momento na FastTab **Linhas da viagem**. Observe que essa FastTab inclui detalhes sobre a posição que cada linha ocupa no contêiner e a quantidade declarada.

## <a name="header-view"></a>Exibição do cabeçalho

Para abrir o modo de exibição **Cabeçalho**, abra uma viagem e selecione a guia **Cabeçalho** no canto superior direito do título viagem.

### <a name="settings-on-the-general-fasttab"></a>Configurações na FastTab Geral

A tabela a seguir descreve os campos disponíveis na FastTab **Geral** no modo de exibição **Cabeçalho** de uma viagem.

| Campo | descrição |
|---|---|
| Viagem | Insira o número da viagem ou do voo. |
| Referência de reserva | Se o seu remetente ou o centro de remessa fornecer um número de referência para identificar a viagem (ou seja, a referência interna da transportadora ou do centro de remessa), insira-o aqui. |
| Embarcação | Insira ou selecione a embarcação. Se a embarcação não estiver listada como um valor, você poderá inserir a ID da embarcação como texto livre. Nesse caso, a tabela principal não é atualizada de forma que a ID da embarcação possa ser selecionada neste campo posteriormente. |
| ID de viagem externa | Insira a ID disponível publicamente para a viagem (como o número do voo). |
| Conhecimento aéreo/conhecimento de embarque mestre | Insira o número de conhecimento de embarque aéreo mestre ou do conhecimento de embarque. Você pode especificar esse valor no transporte aéreo. |
| Conhecimento aéreo/conhecimento de embarque doméstico | Insira o conhecimento de embarque aéreo interno ou o conhecimento de embarque para o contêiner de remessa. |
| Locação | Marque esta caixa de seleção para indicar que o contêiner é um contêiner de aluguel que deve ser devolvido. |
| descrição | Insira uma descrição da viagem para facilitar o reconhecimento. |
| Status da viagem | O status da viagem. Os valores incluem *Criado*, *Em trânsito*, *Documentos recebidos* e *Orçado*. Este campo não é calculado com base na lógica. Ele só é atualizado por meio da ação de lançamento. O valor *Orçado* indica que foi recebida uma fatura para o estoque e todos os custos de viagem. A menos que uma fatura seja recebida, uma viagem não pode atingir o status *Orçado*. |
| Status da ordem de compra | O status mais alto que foi atingido entre todas as ordens de compra associadas à viagem. |
| Documentos recebidos | Um valor que indica se a sua empresa recebeu todos os documentos associados à viagem. Para alterar o valor, selecione **Documentos recebidos** no grupo **Atualização de viagens** na guia **Gerenciar** do Painel de Ações. |
| Transportadora | Selecione a transportadora para esta viagem. Este campo pode ser usado para determinar os custos automáticos. |
| Nome | O nome da empresa selecionada no campo **Transportadora**. |
| Medição | Este campo permite que uma medida seja especificada em um custo automático. Medidas são usadas por organizações que não sabem o volume ou o peso individual das mercadorias, mas que exigem uma divisão mais precisa do o fornecido pelo valor ou pela quantidade. O controlador de frete fornecerá a medida de peso ou cúbica e você pode colocá-la no nível de um item ou da ordem de compra. Ele poderá ser atualizado automaticamente se o parâmetro for selecionado ou poderá ser inserido manualmente. |
| Unidade de medida | A unidade de medida que se aplica ao número no campo **Medida**. |
| Número de paletes | Especifique o número de paletes na linha de viagens. Este campo será atualizado automaticamente se a opção **Atualizar número de cartões automaticamente** estiver definida como *Sim* na guia **Geral** da página **Parâmetros de custo de entrega**. |

### <a name="settings-on-the-delivery-fasttab"></a>Configurações na FastTab Entrega

A tabela a seguir descreve os campos disponíveis na FastTab **Entrega** no modo de exibição **Cabeçalho** de uma viagem.

| Campo | Descrição |
|---|---|
| Data e hora de criação | A data e a hora em que o registro de viagem foi criado. |
| Data de posto na fábrica | Este campo seleciona a data da ex-fábrica por exemplo, entre as ordens de compra vinculadas à viagem. A data da ex-fábrica está disponível no cabeçalho da ordem de compra e é atualizada com o recurso controle de acompanhamento. |
| Data da remessa | A data estimada em que o avião ou a embarcação deixa o ponto de origem. |
| Data da partida | A data de partida é geralmente a data em que o avião ou a embarcação realmente deixa o porto do exterior. A data de remessa e a data de partida não precisam coincidir. O campo **Data de partida** é somente para fins informativos. Ele não é usado para estimar a data de entrega esperada. O recurso de controle de acompanhamento é usado para estimar a data de entrega esperada. Este campo pode ser configurado de forma que seja preenchido automaticamente pelo recurso controle de acompanhamento. |
| Na data de armazenamento | Este campo seleciona a primeira data em que as mercadorias das ordens de compra vinculadas à viagem estarão disponíveis para venda. |
| Data de entrega estimada | A data de entrega estimada geralmente é a data em que as mercadorias devem chegar no depósito. Este campo é meramente informativo. Ela não é usada para planejamento mestre de mercadorias. A data de entrega esperada na linha da ordem de compra é usada para planejamento mestre de mercadorias em uma viagem e é atualizada usando o recurso de controle de acompanhamento. Este campo pode ser configurado de forma que seja preenchido pelo recurso de controle de acompanhamento. |
| Data de entrega real | A primeira data de entrega, com base nas mercadorias vinculadas à viagem. |
| ETA na porta de remessa | Digite a data em que você espera que a viagem chegue na porta de remessa, com base nas informações fornecidas pelo agente de remessa. |
| Documentos originais recebidos | Insira a data em que os documentos originais foram recebidos. |
| Agente aconselhado | Insira a data em que o agente foi aconselhado. |
| Conhecimento de embarque original enviado | Insira a data em que o conhecimento de embarque original foi enviado. |
| Mercadorias lançadas | Insira a data em que as mercadorias foram liberadas da alfândega. |
| Compromisso do cliente | Insira a data de compromisso do cliente, que é a data em que você espera que o cliente se aproprie das mercadorias. |
| Entrega no depósito | Insira a data em que as mercadorias foram entregues ao depósito. |
| Data de verificação | Insira a data de verificação. |
| Instruções de entrega | Insira a data em que as instruções de entrega foram recebidas. |
| Modo de entrega | Este campo fornece informações sobre o método usado para entregar a viagem e a seleção de custo de custos automáticos associados a esse método de entrega. |
| Porta de origem | A porta de remessa de onde a viagem parte. |
| Porta de destino | A porta de remessa na qual a viagem chega. Os contêineres de remessa podem ter portas diferentes, pois a remessa pode ser interrompida em várias portas. Ao verificar a porta "para" no nível do contêiner de remessa, você fornece detalhes precisos da porta para cada contêiner de remessa em uma viagem. O custo automático associado ao frete é determinado com base na combinação do tipo de contêiner de remessa, na porta "para" e na porta "de". |
| Encaminhador local | Este campo é meramente informativo. O encaminhador local deve ser selecionado na tabela de fornecedores. |
| Data de transporte local | A data para a qual o transporte local está reservado. Este campo pode ajudar o depósito no planejamento. |
| Hora de transporte local | O intervalo de tempo para o qual o transporte local está reservado. Este campo pode ajudar o depósito no planejamento. |
| Modelo de diário | O modelo de percurso especificado para a viagem. O modelo de percurso é usado para inserir as portas "para" e "de" do contêiner de remessa e viagem. Esses valores, por sua vez, ajudam a identificar os custos automáticos associados à viagem. |

### <a name="settings-on-the-other-fasttab"></a>Configurações na FastTab Outro

A tabela a seguir descreve os campos disponíveis na FastTab **Outro** no modo de exibição **Cabeçalho** de uma viagem.

| Campo | descrição |
|---|---|
| Comentários | Insira informações adicionais relacionadas à viagem. |
| Data de avaliação | Selecione a data da ex-fábrica para as ordens de compra vinculadas à viagem. |
| Viagem pendente | Você pode usar isso para indicar se a remessa ou a viagem partiu. Ela é meramente informativa.  |
| Renomear contêineres de remessa | Para viagens com mais de um contêiner, o número de contêineres que ainda não foram recebidos. |

## <a name="voyage-update-periodic-tasks"></a>Tarefas periódicas de atualização de viagens

O módulo **Custo de entrega** inclui várias tarefas periódicas relacionadas a viagens que podem atualizar em massa vários aspectos da viagem. Para executar ou programar essas tarefas periódicas, acesse **Custo de entrega \> Tarefas periódicas \> Atualizações de viagem** e selecione um dos seguintes tipos de tarefa:

- **Documentos recebidos** – esta tarefa permite definir **Documentos recebidos** como *Sim* para várias viagens ao mesmo tempo. Use as configurações de **Filtro** para definir o conjunto de viagens que você deseja atualizar.
- **Em trânsito** – esta tarefa permite definir o campo **Status da viagem** com o status em trânsito que é estabelecido na página **[Parâmetros de custo de entrega](landed-cost-parameters.md)** para várias viagens ao mesmo tempo. Use as configurações de **Filtro** para definir o conjunto de viagens que você deseja atualizar.
- **Pronto para avaliação de custo** – esta tarefa permite definir o campo **Status da viagem** com o status pronto para avaliação de custo que é estabelecido na página **[Parâmetros de custo de entrega](landed-cost-parameters.md)** para várias viagens ao mesmo tempo. Em geral, a tarefa será configurada para ser executada em uma agenda regular.
- **Orçado** – esta tarefa permite definir o campo **Status da viagem** como o status orçado estabelecido na página **[Parâmetros de custo de entrega](landed-cost-parameters.md)** para várias viagens ao mesmo tempo, desde que eles tenham sido orçados, mas ainda não estejam atualizados na viagem. Em geral, a tarefa será configurada para ser executada em uma agenda regular.
