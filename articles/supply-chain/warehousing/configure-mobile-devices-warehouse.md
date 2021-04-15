---
title: Configurar dispositivos móveis para trabalho de depósito
description: Este tópico descreve como configurar os itens de menu que os trabalhadores de depósito usam para executar o trabalho em um dispositivo móvel.
author: MarkusFogelberg
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFSysDirSort, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d3acbc15b6dc5f698f26aae96c75cc942189c6c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808789"
---
# <a name="set-up-mobile-devices-for-warehouse-work"></a>Configurar dispositivos móveis para trabalho de depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar os itens de menu que os trabalhadores de depósito usam para executar o trabalho em um dispositivo móvel.

> [!NOTE]
> Este tópico se aplica a recursos do Gerenciamento de depósito. Ele não se aplica aos recursos do Gerenciamento de estoque. Os itens de menu que aparecem nos menus em um dispositivo móvel do depósito são configurados na página **Itens de menu do dispositivo móvel**. Como os itens de menu podem ser inseridos em menus diferentes, é fácil configurar estruturas de menu de forma que somente os tipos específicos de trabalho sejam expostos a usuários específicos. Você pode configurar itens de menu para executar as seguintes tarefas:

- Processar uma consulta ou executar uma atividade, como imprimir um rótulo, gerar números da placa de licença, iniciar uma ordem de produção ou pesquisar rapidamente informações sobre itens em um local.
- Criar o trabalho a ser executado por meio de outro processo. Por exemplo, o recebimento de um item para uma ordem de compra pode criar trabalho de armazenamento para outro trabalhador.
- Executar o trabalho que foi criado por outro processo (trabalho existente), como o trabalho de armazenamento que foi criado quando um item foi recebido para uma ordem de compra.

Para criar um item de menu para uma atividade ou uma consulta, defina o campo **Modo** como **Indireto**. Uma lista opções do **Código de atividade** torna-se disponível, de forma que você possa selecionar o tipo de consulta ou atividade do item de menu. Para criar um item de menu para gerar o trabalho de depósito, defina o campo **Modo** como **Trabalho**. Uma lista de opções do **Processo de criação de trabalho**, em seguida, fica disponível. Para criar um item de menu para processar o trabalho de depósito existente, defina o campo **Modo** como **Trabalho** e, em seguida, defina a opção **Usar trabalho existente** como **Sim**. 

> [!NOTE]
> Outros campos podem estar disponíveis para itens de menu, dependendo do modo selecionado para o item de menu e se o item de menu é usado para executar um trabalho existente. Para obter informações sobre as seleções de campo adicionais, consulte a seção “Opções de item de menu adicionais” posteriormente neste tópico.

## <a name="configure-menu-items-for-activities-and-inquiries"></a>Configurar itens de menu para atividades e consultas
Se o campo **Modo** de um item de menu for definido como **Indireto**, você poderá criar um item de menu para executar uma atividade ou uma consulta geral que não cria o trabalho. Os exemplos incluem reimpressão de rótulos de matrícula e uma consulta sobre os itens em um local. A tabela a seguir lista as opções disponíveis.

| Opção | Descrição |
|---|---|
| Nenhum | Esse valor padrão não habilita uma atividade ou uma consulta. |
| Sobre | Exiba informações sobre o sistema, como o número de versão, a ID do depósito e o trabalhador que está conectado. |
| Alterar depósito | Altere o depósito ao qual um trabalhador esteja conectado. |
| Consulta de localização | Exiba informações sobre todos os itens e quantidades para um local. |
| Consulta de placa de licença | Exiba a quantidade de itens em uma placa de licença e o local da placa de licença. |
| Começar ordem de produção | Inicie uma ordem de produção. |
| Sucata de produção | Insira a quantidade de sucata criada durante a produção de cada linha da lista de materiais (BOM). |
| Último palete de produção | Indica que o último palete de itens foi produzido para uma ordem de produção e que o status da ordem de produção deve ser atualizado para **Informado como concluído**. O status das matérias-primas que não foram consumidas durante a produção é revertido de **Separado** para **Em ordem** e os itens podem ser retornados para o estoque. |
| Consulta de item | Verifique um item para determinar sua localização no depósito. A consulta retorna todas as localizações e quantidades do item verificado. |
| Reimprimir etiqueta | Imprimir novamente uma etiqueta da placa de licença. |
| Criação da placa de licença | Crie uma placa de licença pai combinando várias placas de licença no mesmo local. Esta opção é útil se você mover várias placas de licença ao mesmo tempo. Depois que a placa de licença pai for movida, você deverá executar uma interrupção de placa de licença antes de poder separar itens de cada placa de licença. <p></p>**Dica:** Para mover uma matrícula pai, você deve usar um dispositivo móvel configurado para criar trabalho para movimentos. |
| Interrupção da placa de licença | Divida uma criação de placa de licença para poder separar itens das placas de licença que estavam na criação. |
| Check-in do motorista | Se você estiver usando o Gerenciamento de transporte, registre a chegada de um motorista verificando a ID da carga de saída, a ID do compromisso ou a ID da remessa. Para esta opção, uma carga deve ser atribuída ao compromisso, e o status da carga deve ser **Carregado**. |
| Check-out do motorista | Registre que um motorista concluiu o compromisso. |
| Liberar cache de sequência numérica | Exclua números de sequência numérica do cache de sequência numérica. Essa atividade é normalmente executada por um administrador do sistema para resolver problemas do cache quando os dispositivos móveis são usados. |
| Alterar disposição em lotes | Permite que um trabalhador especifique o código de disposição do lote de um item e lote. Essa seleção atualiza o código de disposição especificado para o lote. |
| Exibir lista de trabalhos abertos | Mostra a lista de trabalho disponível para um usuário específico. O usuário pode selecionar o trabalho para executar e será direcionado a ele. Esta lista é para ser exibida em dispositivos tablet com telas de 7 polegadas ou mais. Quando você seleciona esta opção, os itens de menu **Editar consulta** e **Lista de campos** ficam disponíveis. A página **Editar consulta** permite que você configure critérios para o trabalho que aparece na lista. A página **Lista de campos** permite selecionar os campos que aparecem na lista de trabalho. Por exemplo, você pode optar por reduzir o número de campos que aparecem, de forma que o usuário possa selecionar o item de trabalho mais apropriado, de forma mais rápida. Na Guia Rápida **Geral**, no campo **Registros por página**, também é possível selecionar quantos registros de trabalho devem ser exibidos por página. Se a opção **Permitir que usuários filtrem o trabalho por tipo de transação** for selecionada, a lista de trabalho terá um controle **Filtrar trabalho** que o usuário poderá usar para filtrar por tipo de transação. Na lista de trabalho, os usuários verão apenas o trabalho que eles têm permissão para acessar. Você precisa ter certeza de que os usuários têm permissão para um ou mais itens de menu específicos de usuário, que suportam os tipos de classe de trabalho específicos que eles precisam acessar. As permissões são verificadas quando um usuário tentar executar o trabalho na lista.|
| Criar ordem de transferência das placas de licença | Permite que os trabalhadores de depósito criem e processem ordens de transferência diretamente do aplicativo móvel do Gerenciamento de Depósito. Os trabalhadores do depósito começam selecionando o depósito de destino e podem, então, verificar uma ou mais placas de licença usando o aplicativo. Quando o trabalho de depósito selecionar **Ordem completa**, um trabalho em lotes criará a ordem de transferência e as linhas de ordem necessárias com base no estoque disponível registrado para essas placas de licença. Para obter mais informações, consulte [Criar ordens de transferência do aplicativo de depósito](create-transfer-order-from-warehouse-app.md).


## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>Configurar itens de menu para criar trabalho para outro trabalhador ou processo
Você pode configurar um item de menu que cria trabalho para outro trabalhador, após uma ação inicial ser executada no dispositivo móvel. Por exemplo, quando um trabalhador usa um dispositivo móvel para receber um item, o trabalho de armazenamento é criado para outro trabalhador. Para configurar um item de menu que cria o trabalho, na página **Itens de menu do dispositivo móvel**, no campo **Modo**, selecione **Trabalho**. Na tabela a seguir, as opções no campo **Processo de criação de trabalho** são organizadas por tipo de ordem de trabalho.


<table>
<tbody>
<tr>
<th>Tipo de ordem de serviço</th>
<th>Opção</th>
<th>Descrição</th>
</tr>
<tr>
<td rowspan="8">Ordem de Compra</td>
<td>Recebimento da linha da ordem de compra</td>
<td>Registre o recebimento de uma quantidade de um item usando o número da ordem de compra e o número da linha da ordem de compra e crie o trabalho de armazenamento para outro trabalhador.</td>
</tr>
<tr>
<td>Recebimento da linha da ordem de compra e armazenamento</td>
<td>Registre o recebimento de uma quantidade de um item usando o número da ordem de compra e o número da linha da ordem de compra e armazene os itens. O mesmo trabalhador executa as duas ações.</td>
</tr>
<tr>
<td>Recebimento do item da ordem de compra</td>
<td>Registre o recebimento de uma quantidade de um item de uma ordem de compra registrando o número da ordem de compra e o número do item e crie o trabalho de armazenamento para outro trabalhador.</td>
</tr>
<tr>
<td>Recebimento e armazenamento do item da ordem de compra</td>
<td>Registre o recebimento de uma quantidade de um item para uma ordem de compra registrando o número da ordem de compra e armazene o item. O mesmo trabalhador executa as duas ações.</td>
</tr>
<tr>
<td>Recebimento da placa de licença</td>
<td>Receba um aviso de embarque de entrada (ASN) usando a ID da placa de licença.</td>
</tr>
<tr>
<td>Recebimento e armazenamento da placa de licença</td>
<td>Receba e armazene um aviso de embarque de entrada (ASN) usando a ID da placa de licença.</td>
</tr>
<tr>
<td>Recebimento do item de carga</td>
<td>Registre o recebimento de uma quantidade de carga usando a ID de carga e crie o trabalho de armazenamento para outro trabalhador. O número do item e as dimensões do produto correspondem ao recebido para as linhas da ordem de compra.</td>
</tr>
<tr>
<td>Recebimento e armazenamento do item de carga</td>
<td>Registre o recebimento de uma carga usando a ID da carga e armazene os itens. O número do item e as dimensões do produto correspondem ao recebido para as linhas da ordem de compra. O mesmo trabalhador executa as duas ações.</td>
</tr>
<tr>
<td rowspan="2">Ordem de Devolução</td>
<td>Recebimento da ordem de devolução</td>
<td>Registre o recebimento de uma quantidade de um item, registrando o número RMA e crie trabalho de armazenamento para outro trabalhador.</td>
</tr>
<tr>
<td>Recebimento e armazenamento da ordem de devolução</td>
<td>Registre o recebimento de uma quantidade de um item registrando o número RMA e armazene os itens. O mesmo trabalhador executa as duas ações.</td>
</tr>
<tr>
<td rowspan="6">Ordem de transferência</td>
<td>Recebimento do item da ordem de transferência</td>
<td>Registre o recebimento de uma quantidade de um item e crie trabalho de armazenamento para outro trabalhador.

<strong>Observação:</strong> Use essa opção somente se os itens forem remetidos de um depósito que não esteja habilitado para processos de gerenciamento de depósito.</td>
</tr>
<tr>
<td>Recebimento e armazenamento do item da ordem de transferência</td>
<td>Registre o recebimento de uma quantidade de um item e armazene os itens. O mesmo trabalhador executa as duas ações.

<strong>Observação:</strong> Use essa opção somente se os itens forem remetidos de um depósito que não esteja habilitado para processos de gerenciamento de depósito.</td>
</tr>
<tr>
<td>Recebimento da linha da ordem de transferência</td>
<td>Registre o recebimento de uma quantidade de um item e crie trabalho de armazenamento para outro trabalhador.</td>
</tr>
<tr>
<td>Transferir recebimento e armazenamento do recebimento da linha de ordem</td>
<td>Registre o recebimento de uma quantidade de um item e armazene os itens. O mesmo trabalhador executa as duas ações.</td>
</tr>
<tr>
<td>Recebimento da placa de licença</td>
<td>Receba um aviso de embarque de entrada (ASN) usando a ID da placa de licença.</td>
</tr>
<tr>
<td>Recebimento e armazenamento da placa de licença</td>
<td>Receba e armazene um aviso de embarque de entrada (ASN) usando a ID da placa de licença.</td>
</tr>
<tr>
<td rowspan="4">Produção</td>
<td>Relatório de Conclusão</td>
<td>Registre uma quantidade de um item concluído que tenha sido concluído para uma produção e crie o trabalho de armazenamento para outro trabalhador. A quantidade pode ser parte ou toda a quantidade planejada para a produção.</td>
</tr>
<tr>
<td>Relatar como concluído e armazenado</td>
<td>Registre uma quantidade de um item concluído que tenha sido concluído para uma produção e armazene os itens. A quantidade pode ser parte ou toda a quantidade planejada para a produção. O mesmo trabalhador executa as duas ações.</td>
</tr>
<tr>
<td>Kanban</td>
<td>Indique que um Kanban foi concluído e crie trabalho de armazenamento para outro trabalhador.</td>
</tr>
<tr>
<td>Armazenamento kanban</td>
<td>Indique quem um kanban foi concluído e armazene os itens. O mesmo trabalhador executa as duas ações.</td>
</tr>
<tr>
<td rowspan="5">Estoque</td>
<td>Movimento</td>
<td>Registre que itens foram movidos de um local para outro. O trabalhador especifica o local de onde os itens são movidos e para onde eles são movidos.</td>
</tr>
<tr>
<td>Quarentena</td>
<td>Altere o status do estoque disponível para uma placa de licença ou um local para indisponibilizar itens de estoque danificados ou ausentes.</td>
</tr>
<tr>
<td>Movimento por modelo.</td>
<td>Mova itens de um local para outro de uma maneira semiautomatizada. O trabalhador seleciona o local de onde os itens serão movidos, o sistema usa a diretiva de localização para determinar para onde os itens serão movidos.</td>
</tr>
<tr>
<td>Transferência de depósito</td>
<td>Registre que itens foram transferidos de um depósito para outro. Esta opção requer que o trabalhador tenha permissão de executar trabalho em ambos os depósitos.

<strong>Observação:</strong> Este item de menu requer um diário padrão de transferência de estoque onde o campo <strong>Emissão de comprovante</strong> é definido como <strong>Lançamento</strong>.</td>
</tr>
<tr>
<td>Carregamento da placa de licença:</td>
<td>Use esta opção quando estiver configurando o depósito pela primeira vez. Verifique todas as placas de licença em todos os locais do depósito. Os locais devem ser controlados por placa de licença. Não é possível usar esta opção se <strong>Número de série</strong> ou <strong>Número de lote</strong> está acima de <strong>Local</strong> na hierarquia de reserva de estoque.</td>
</tr>
<tr>
<td rowspan="3">Contagem cíclica</td>
<td>Ajuste de entrada</td>
<td>Aumente a quantidade de itens em estoque. Especifique o local, a placa de licença, o item, a quantidade, a unidade de medida e o status.</td>
</tr>
<tr>
<td>Ajuste de saída</td>
<td>Reduza a quantidade de itens em estoque. Especifique o local, a placa de licença, o item, a quantidade, a unidade de medida e o status do estoque.</td>
</tr>
<tr>
<td>Contagem cíclica pontual</td>
<td>Inicie uma contagem para um local. O trabalhador deve contar todos os itens do local. Quando o resultado de uma contagem for menor do que a quantidade prevista, a quantidade ausente será considerada como uma perda.</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>Configure itens de menu para processar o trabalho existente
Além de configurar itens de menu para criar o trabalho de depósito, você pode configurar itens de menu para processar o trabalho que já foi criado. Defina o campo **Modo** como **Trabalho** e selecione a opção **Usar trabalho existente**. Algumas opções adicionais então ficam disponíveis na guia **Geral**. Você pode controlar o acesso ao item de menu atribuindo uma ou mais classes de trabalho na Guia Rápida **Classe de trabalho**. As classes de trabalho definem o trabalho que o item de menu pode processar. A classe de trabalho também pode ser usada para conceder acesso às funções de usuário específico ou ao processamento separado para tipos diferentes de operações. A tabela a seguir descreve as opções disponíveis. A opção pode ser escolhida no campo **Direcionado por** na página **Itens de menu do dispositivo móvel**. 

<table>




<thead>
<tr class="header">
<th>Opção</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nenhuma</td>
<td>Este valor padrão não processa trabalho.</td>
</tr>
<tr class="even">
<td>Sistema direcionado</td>
<td>O Supply Chain Management controla o tipo de trabalho atribuído a um trabalhador e a ordem em que ele executa o trabalho. Ao selecionar essa opção, você pode selecionar <strong>Trabalho direcionado pelo sistema</strong> no Painel de Ação para abrir a página <strong>Ordem de classificação direcionada pelo sistema</strong>, na qual você pode configurar os critérios de classificação para o trabalho. Os critérios de classificação controlam a ordem na qual o trabalhador executa o trabalho. Você pode adicionar quantos critérios forem necessários.</td>
</tr>
<tr class="odd">
<td>Usuário direcionado</td>
<td>O trabalhador seleciona o trabalho a ser executado e a ordem para executá-lo.</td>
</tr>
<tr class="even">
<td>Agrupamento de usuários</td>
<td>O trabalhador agrupa manualmente o trabalho. Esta opção é útil quando, por exemplo, um trabalhador puder separar vários itens ao mesmo tempo em um local. Depois que o trabalhador tiver terminado de separar todos os itens necessários, ele poderá armazenar os itens.</td>
</tr>
<tr class="odd">
<td>Agrupamento do sistema</td>
<td>O Supply Chain Management agrupa o trabalho para o trabalhador com base em um campo especificado. Por exemplo, o trabalho de separação é agrupado quando um trabalhador verifica uma ID de remessa, uma ID de carga ou qualquer valor que possa vincular cada unidade de trabalho. Se você selecionar essa opção, estes campos serão obrigatórios:
<ul>
<li><strong>Campo de agrupamento do sistema</strong> – Selecione o campo que o trabalhador verificará para agrupar o trabalho.</li>
<li><strong>Etiqueta de agrupamento do sistema</strong> – Insira texto para informar ao trabalhador sobre o que verificar para agrupar o trabalho.</li>
</ul></td>
</tr>
<tr class="even">
<td>Usuário validado direcionado</td>
<td>O trabalhador selecionará o trabalho a ser executado quando o trabalho estiver associado a uma entidade maior, como uma carga ou uma remessa. O trabalhador determina a ordem na qual os itens são separados. Se você selecionar essa opção, estes campos serão obrigatórios:
<ul>
<li><strong>Campo Direcionado do Usuário Validado</strong> – Selecione o campo que o trabalhador pesquisa para agrupar o trabalho.</li>
<li><strong>Etiqueta Direcionada do Usuário Validado</strong> – Insira o texto que informará ao trabalhador sobre o que verificar quando o trabalho de separação for agrupado pelo sistema.</li>
</ul>
Esta opção será útil quando, por exemplo, vários paletes foram preparados para uma carga. Se você selecionar <strong>LoadId</strong> no campo <strong>Direcionado do Usuário Validado</strong>, o trabalhador poderá escolher qualquer palete que esteja associado à carga. O trabalhador receberá uma mensagem de erro se verificar um item não associado à carga.</td>
</tr>
<tr class="odd">
<td>Separação de cluster</td>
<td>O trabalhador agrupa trabalho em clusters. Os clusters permitem que os trabalhadores separem itens de um único local para várias ordens de trabalho ao mesmo tempo.</td>
</tr>
<tr class="even">
<td>Agrupamento de contagens cíclicas</td>
<td>O trabalhador seleciona uma zona, um pool de trabalho ou um local, e o Supply Chain Management atribui o trabalho com base na seleção. Se selecionar esta opção, você poderá clicar em <strong>Contagem cíclica</strong> no Painel de Ações para especificar informações adicionais a serem exibidas, além de especificar o número de vezes que o trabalhador deverá repetir a contagem caso seja encontrada uma diferença.</td>
</tr>
 <tr class="odd">
<td>Carga de transporte</td>
<td>Esse recurso permite que vários trabalhadores do depósito carreguem o estoque de cargas iguais ou diferentes para o mesmo caminhão, com cargas que foram remetidas de forma completa ou parcial.</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>Opções de item de menu adicionais
As opções adicionais dos itens de menu estarão disponíveis na página **Itens de menu do dispositivo móvel**. As opções variam, dependendo do processo que você está configurando no item de menu. 

A seguinte tabela descreve as opções.

<table>




<thead>
<tr class="header">
<th>Campo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Permitir divisão de trabalho</td>
<td>Marque essa opção para permitir que os usuários coloquem itens de uma ordem de trabalho em mais de uma placa de licença de destino. Esta opção é útil quando, por exemplo, uma placa de licença de destino estiver cheia e o trabalhador tiver de adicionar os itens restantes a outra placa de licença. O trabalhador pode selecionar <strong>Cheia</strong> para indicar que a placa de licença está cheia e parar de receber trabalho de separação para ela. A localização colocada para os itens separados será exibida em seguida, e o trabalho de separação que já tiver sido concluído será movido para uma nova ordem de trabalho. O trabalho de separação restante para a placa de licença de destino permanecerá na ordem de trabalho original.</td>
</tr>
<tr class="even">
<td>Ancoragem</td>
<td>Selecione esta opção para permitir que os trabalhadores especifiquem um local que substituirá o local de preparo ou de carga sugerido. Todo o trabalho de armazenamento restante será direcionado para o novo local. Esta opção é útil quando, por exemplo, um trabalhador tiver de armazenar itens da ordem 1 em um local de preparo da Doca 1, mas não consegue porque uma carga anterior ainda não liberou o local. Em vez de aguardar que o local de preparo da Doca 1 fique disponível, o trabalhador decide usar o local de preparo da Doca 2. Nesse caso, ele substitui o local de preparo sugerido. O local de armazenamento de todos os itens restantes da ordem de trabalho é, em seguida, atualizado para o local de preparo da Doca 2. Se selecionar esta opção, você deverá definir o campo <strong>Ancorar em</strong>.</td>
</tr>
<tr class="odd">
<td>Ancorar em</td>
<td>Se você estiver usando a ancoragem, deverá especificar se quer ancorar por remessa ou por carga.</td>
</tr>
<tr class="even">
<td>ID do modelo de auditoria</td>
<td>Selecione o modelo de auditoria de trabalho que interromperá o processo de trabalho para esse item de menu de forma que outra operação possa ser executada. Por exemplo, se esse item de menu for para o trabalho de entrada, o modelo de auditoria poderá exigir que o trabalhador verifique a temperatura no contêiner de entrega. O ponto em que o processo for interrompido é especificado no modelo de auditoria. Este ponto pode ser, por exemplo, quando o trabalho é iniciado ou concluído ou quando seu status muda.</td>
</tr>
<tr class="odd">
<td>ID do perfil de cluster</td>
<td>Selecione o perfil de cluster a ser usado para separação de cluster. O perfil do cluster inclui configurações, como por exemplo, se cria clusters automaticamente, os nomes de posições e o número de unidades de trabalho que eles podem atribuir, quando dividir clusters em unidades individuais e se a verificação é necessária. Este campo só estará disponível se <strong>Separação de cluster</strong> for selecionado no campo <strong>Direcionado por</strong>.</td>
</tr>
<tr class="even">
<td>Contar quantidade total de itens primeiro</td>
<td>Marque essa opção para exigir que um trabalhador conte a quantidade total primeiro durante uma contagem. Se uma diferença for encontrada, o trabalhador deverá fornecer informações adicionais, como o número da placa de licença, o número do lote e números de série.</td>
</tr>
<tr class="odd">
<td>Criar movimento</td>
<td>Marque essa opção para permitir que um trabalhador crie trabalho para um movimento, mas sem exigir que o trabalhador execute o trabalho imediatamente. Esta opção é útil, por exemplo, se uma inspeção de qualidade tiver sido concluída, e o inspetor quiser que o item seja movido da área de inspeção de qualidade.</td>
</tr>
<tr class="even">
<td>Código de diretiva</td>
<td>Para usar uma diretiva de localização específica, selecione o código de diretiva associado à diretiva de localização. Este campo fica disponível quando você cria o trabalho e o processo de criação do trabalho é <strong>Movimento por modelo</strong>.</td>
</tr>
<tr class="odd">
<td>Desabilitar restrições de contagem cíclica</td>
<td>Marque esta opção para ignorar os limites de contagem cíclica. Se você selecionar esta opção, o trabalho de contagem cíclica não será criado quando os valores limite forem excedidos.</td>
</tr>
<tr class="even">
<td>Exibir código de disposição em lotes</td>
<td>Selecione esta opção para exibir códigos de disposição de lote. Por exemplo, você pode exibir códigos de disposição de lote quando receber um lote devolvido. Os trabalhadores podem então avaliar o status ou a qualidade de um lote e selecionar o código adequado. As regras no código de disposição de lote determinam se o lote estará disponível para outros processos do depósito. Se você não selecionar esta opção, será usado um dos seguintes códigos de disposição do lote:
<ul>
<li>Se você receber um novo número de lote, o código de disposição de lote padrão será especificado no grupo de modelos de item.</li>
<li>O código de disposição de lote que já foi atribuído ao lote.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Exibir código de disposição</td>
<td>Selecione esta opção para exibir códigos de disposição. Por exemplo, você pode exibir códigos de disposição quando receber itens devolvidos. Os trabalhadores podem então avaliar o status ou a qualidade dos itens e selecionar o código adequado. As regras no código de disposição determinam se os itens estarão disponíveis para outros processos do depósito.</td>
</tr>
<tr class="even">
<td>Exibir status do estoque</td>
<td>Marque essa opção para exibir o status de itens em estoque. Essa opção está disponível para todos os itens de menu que usam trabalho existente, exceto a contagem cíclica.</td>
</tr>
<tr class="odd">
<td>Exibir resumo de tela de separação</td>
<td>Marque essa opção para exibir um resumo de trabalho de separação para a ordem de trabalho selecionada. O resumo será exibido até a primeira linha do trabalho ser processada para a ordem de trabalho.</td>
</tr>
<tr class="even">
<td>Gerar placa de licença</td>
<td>Marque essa opção para gerar um número da placa de licença exclusivo com base na seleção da sequência numérica. Por exemplo, você pode gerar um número da placa de licença para itens recebidos para ordens de compra.</td>
</tr>
<tr class="odd">
<td>Armazenamento de grupo</td>
<td>Marque essa opção para agrupar o trabalho de armazenamento. Essa opção está disponível quando o trabalho foi agrupado pelo trabalhador ou pelo Supply Chain Management. Quando o trabalhador tiver concluído todo o trabalho de separação no grupo, o trabalho de armazenamento será criado para o mesmo grupo.</td>
</tr>
<tr class="even">
<td>Tipos de ajuste de estoque</td>
<td>Selecione o tipo de ajuste de estoque que determina o diário de contagem de estoque usado para lançar o ajuste e se as reservas serão removidas. Este campo só está disponível para os processos de <strong>Ajuste de entrada</strong> ou <strong>Ajuste de saída</strong>.</td>
</tr>
<tr class="odd">
<td>Substituir número do lote</td>
<td>Marque essa opção para permitir que os trabalhadores que estejam informando uma quantidade como concluída para uma ordem de produção insiram um número de lote diferente do número de lote atribuído à ordem de produção.</td>
</tr>
<tr class="even">
<td>Substituir placa de licença de destino</td>
<td>Selecione esta opção para permitir que os trabalhadores especifiquem um número da placa de licença de destino diferente da placa de licença de destino sugerida. Use essa opção quando a primeira separação para uma ordem de trabalho for para toda a quantidade de um item em uma placa de licença. Esta opção é útil, por exemplo, na reutilização de um palete.</td>
</tr>
<tr class="odd">
<td>Separar e empacotar</td>
<td>Selecione esta opção para permitir que trabalhadores combinem trabalho para uma ordem de venda ou para uma carga em uma única unidade de trabalho. Um trabalhador só poderá executar trabalho para a ordem de venda ou para a carga. Esta opção é útil quando, por exemplo, você precisar aumentar uma quantidade para uma ordem de venda depois que a carga, a remessa e o trabalho tiverem sido criados para a ordem de venda. Essa opção estará disponível quando o item de menu usar trabalho existente e quando o trabalho for direcionado pelo usuário ou pelo sistema.</td>
</tr>
<tr class="even">
<td>Separar lote mais antigo</td>
<td>Indique se o trabalhador deve separar o lote mais antigo em um local primeiro. As opções a seguir estão disponíveis:
<ul>
<li><strong>Nenhum</strong> – O trabalhador pode separar qualquer lote no local. O trabalhador não recebe nenhuma mensagem.</li>
<li><strong>Aviso</strong> – o trabalhador pode separar qualquer lote no local, mas receberá uma mensagem de aviso se um lote não for o mais antigo.</li>
<li><strong>Forçar</strong> – O trabalhador deve separar o lote mais antigo no local. O trabalhador receberá uma mensagem de erro se um lote não for o lote mais antigo. <strong>Observação:</strong> Esta opção é relevante somente se o <strong>Número do lote</strong> for menor do que a <strong>Localização</strong> na hierarquia de reserva atribuída ao item.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Imprimir etiqueta</td>
<td>Marque essa opção para permitir que trabalhadores imprimam etiquetas de placa de licença.</td>
</tr>
<tr class="even">
<td>Campo de agrupamento do sistema</td>
<td>Selecione o campo que determina como o Supply Chain Management agrupará o trabalho de separação para os trabalhadores. Por exemplo, se você selecionar o campo <strong>ShipmentId</strong>, o trabalhador verificará a ID da remessa para agrupar o trabalho de separação. Todo o trabalho para a remessa será então atribuído ao trabalhador. Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema. Você também deve inserir texto no campo <strong>Etiqueta de agrupamento do sistema</strong> para instruir o trabalhador sobre o que verificar.</td>
</tr>
<tr class="odd">
<td>Etiqueta de agrupamento do sistema</td>
<td>Insira o texto que informará ao trabalhador o que verificar quando o trabalho de separação for agrupado pelo Supply Chain Management. Por exemplo, se você estiver usando o campo <strong>ShipmentId</strong> para agrupar o trabalho de separação por remessa, poderá inserir <strong>ID da remessa</strong> no campo. Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema. Você também deverá selecionar o campo para agrupar no campo <strong>Agrupamento do sistema</strong>.</td>
</tr>
<tr class="even">
<td>Usar dados padrão</td>
<td>Selecione esta opção para habilitar o botão <strong>Dados padrão</strong> no Painel de Ação, onde é possível selecionar campos para exibir os dados que um trabalhador geralmente precisa em seu trabalho diário. Esta opção é útil, se, por exemplo, um trabalhador normalmente separar itens do mesmo local. Você pode selecionar o campo <strong>Localização de origem</strong> para exibir a localização por padrão.</td>
</tr>
<tr class="odd">
<td>Campo Direcionado do Usuário Validado</td>
<td>Selecione o campo que o trabalhador verificará para agrupar o trabalho. Por exemplo, se você selecionar <strong>LoadId</strong>, um trabalhador poderá separar qualquer trabalho associado a uma carga selecionada. Você também deve inserir texto no campo <strong>Etiqueta Direcionada do Usuário Validado</strong> para instruir o trabalhador sobre o que verificar.</td>
</tr>
<tr class="even">
<td>Etiqueta Direcionada do Usuário Validado</td>
<td>Insira o texto que informará ao trabalhador sobre o que verificar quando o trabalho de separação for agrupado por um campo direcionado por usuário validado. Por exemplo, se você estiver usando o campo <strong>LoadId</strong> para agrupar o trabalho de separação por uma carga, poderá inserir <strong>ID da Carga</strong> no campo.</td>
</tr>
<tr class="odd">
<td>Código do modelo de trabalho</td>
<td>Selecione o modelo de trabalho que criará o trabalho para um processo. Por exemplo, se você receber um item para uma ordem de compra, o trabalho de armazenamento será gerado com base no modelo de trabalho. Se você não selecionar um modelo de trabalho, o Supply Chain Management atribuirá um modelo com base nos critérios de consulta. Para obter mais informações sobre modelos de trabalho, consulte <a href="control-warehouse-location-directives.md">Como controlar o trabalho do depósito com modelos de trabalho e diretivas de localização</a>.</td>
<tr class="even">
<td>Mostrar lista de linhas de trabalho</td>
<td>Selecione uma opção para como os trabalhadores poderão exibir e interagir com as linhas do trabalho de separação selecionado no momento. Para obter mais informações sobre essa opção, consulte <a href="pick-line-overview.md">Configurar um item de menu de dispositivo móvel para fornecer uma visão geral da linha de separação</a>.</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>Exija que os trabalhadores confirmem o produto, o local ou a quantidade ao separarem os itens
Você pode configurar confirmações de trabalho que exijam que um trabalhador use um dispositivo móvel para registrar o local ou a quantidade ao executar trabalho no depósito. As confirmações de trabalho ajudam a garantir que o trabalhador esteja no local correto ou que esteja manipulando a quantidade correta de itens. Você também pode permitir que o Supply Chain Management confirme o registro do trabalhador automaticamente. Se você habilitar a confirmação automática, não poderá exigir também confirmações de local ou de quantidade. As confirmações de trabalho também incluem produtos e variantes de produto. Além disso, você pode registrar confirmações ao digitalizar um código de barras. Para confirmar produtos e variantes de produto, você deve inserir uma ID para o produto ou a variante do produto. Este ID pode ser um ID do produto, ID de pesquisa de produto, ID externa, GTIN ou código de barras. Depois de inserir a ID verificação ou de digitalizar o código de barras, as dimensões para a variante de produto serão exibidas no dispositivo móvel. 

A tabela a seguir descreve os vários tipos de trabalho que você pode usar em confirmações de trabalho.

| Opção | Descrição |
|------------------------|----------------------------------------------------------------------------|
| Separar | Exija confirmação quando os itens são separados. |
| Colocar | Exija confirmação quando os itens forem colocados em um local. |
| Contando | Exija confirmação durante a contagem cíclica. |
| Ajustes | Exija confirmação ao ajustar quantidades em estoque forem ajustadas. |
| Personalizado | Exija confirmação do trabalho personalizado. |
| Quarentena | Exija confirmação quando os itens forem movidos para a quarentena. |
| Criação da placa de licença | Exija confirmação quando os itens forem consolidados para criar uma placa de licença. |
| Imprimir | Exija confirmação quando as etiquetas da placa de licença forem impressas. |
| Alteração de status | Exija confirmação quando o status do estoque for alterado. |

> [!NOTE]
> Você pode exigir a confirmação do produto somente para separar e colocar tipos de trabalho.

<a name="additional-resources"></a>Recursos adicionais
--------

[Configurar um item de menu do dispositivo móvel para concluir o trabalho do tipo Ordem de compra](tasks/set-up-mobile-device-menu.md)

[Configurar um item de menu do dispositivo móvel para registrar itens recebidos](tasks/set-up-mobile-device-menu-item-register-received-items.md)

[Status do estoque](../inventory/inventory-statuses.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]