---
title: Consultar dados usando desvios do aplicativo móvel do Warehouse Management
description: Este artigo descreve como configurar os itens de menu de consulta de dados para o dispositivo móvel e usá-los como parte de desvios.
author: perlynne
ms.date: 08/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour,WHSMobileAppFlowStepDetourSelectFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c3ea53379badb3cb2ed71b7f102956d71c3f047a
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220511"
---
# <a name="query-data-using-warehouse-management-mobile-app-detours"></a>Consultar dados usando desvios do aplicativo móvel do Warehouse Management

[!include [banner](../includes/banner.md)]

## <a name="feature-introduction"></a>Introdução ao recurso

Ao fornecer o recurso de digitalização de código de barras, o aplicativo móvel Warehouse Management oferece uma maneira fácil e precisa de capturar dados como parte de seus processos de depósito. No entanto, às vezes os códigos de barras são danificados e tornam-se ilegíveis, ou as informações de dados necessárias podem não existir como um código de barras nos fluxos de processos empresarial. Nesses casos, a entrada manual dos dados pode levar muito tempo e pode até causar a captura de dados incorretos. Os resultados podem ter uma eficácia reduzida e um nível de serviço mais baixo.

Usando um processo de consulta de dados flexível, os trabalhadores podem consultar facilmente as informações necessárias como parte dos fluxos de aplicativo móvel do Warehouse Management incorporado e aplicar opções de filtragem para que somente os dados relevantes sejam mostrados. Portanto, a seleção manual é mais rápida e precisa.

Por exemplo, no fluxo de recebimento da ordem de compra, é necessário um número de ordem de compra para fazer a correspondência do estoque de chegada. Como parte desse processo, você pode configurar facilmente itens de menu para fornecer uma exibição de lista de cartões dos números de ordem de compra relevantes. Dessa forma, você pode continuar o fluxo de recebimento usando uma abordagem de ponto de seleção rápida. Este artigo oferece cenários de exemplo, mas a funcionalidade também pode ser usada em qualquer um ou em todos os fluxos de aplicativo móvel do Warehouse Management.

## <a name="turn-on-the-data-inquiry-flow-feature-and-its-prerequisites"></a>Ativar o recurso de fluxo de consulta de dados e seus pré-requisitos

Para usar a funcionalidade descrita neste artigo, você deve concluir o procedimento a seguir para ativar os recursos necessários.

1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**. (Para obter mais informações sobre como usar o espaço de trabalho **Gerenciamento de recursos**, consulte [Visão geral do gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Ative o recurso listado da seguinte maneira:

    - **Módulo:** *Gerenciamento de depósito*
    - **Nome do recurso:** *instruções de etapa do aplicativo Warehouse*

    Esse recurso é um pré-requisito para o recurso *Fluxo de consulta de dados do aplicativo Warehouse Management*. Para obter mais informações sobre o recurso *Instruções de etapa do aplicativo do Warehouse*, consulte [Personalizar títulos de etapas e instruções para o aplicativo móvel do Warehouse Management](mobile-app-titles-instructions.md).

1. Ative o recurso listado da seguinte maneira:

    - **Módulo:** *Gerenciamento de depósito*
    - **Nome do recurso:** *desvios do aplicativo do Warehouse Management*

    Esse recurso é um pré-requisito para o recurso *Fluxo de consulta de dados do aplicativo Warehouse Management*. Para obter mais informações sobre o recurso *Desvios do aplicativo Warehouse Management*, consulte [Configurar desvios para as etapas nos itens de menu do dispositivo móvel](warehouse-app-detours.md).

1. Se o recurso *Desvios do aplicativo Warehouse Management* ainda não foi ativado, atualize os nomes de campos no aplicativo móvel Warehouse Management acessando **Warehouse management \> Configuração \> Dispositivo móvel \> Nomes de campo de aplicativo de depósito** e selecionando **Criar configuração padrão**. Repita esta etapa para cada entidade legal (empresa) em que você usa o aplicativo móvel do Warehouse Management. Para obter mais informações, consulte [Configurar campos para o aplicativo móvel Warehouse Management](configure-app-field-names-priorities-warehouse.md).
1. Ative o recurso listado da seguinte maneira:

    - **Módulo:** *Gerenciamento de depósito*
    - **Nome do recurso:** *Fluxo de consulta de dados do aplicativo Warehouse Management*

    Esse recurso é o descrito neste artigo.

## <a name="example-scenarios"></a>Cenários de exemplo

Este artigo usa cenários de exemplo para mostrar como você pode usar o recurso *Fluxo de consulta de dados do aplicativo Warehouse Management* para melhorar o fluxo de recibo de compra. Os cenários usam os dados de exemplo padrão, que incluem um fluxo chamado *Recebimento de compra*. Esse fluxo é iniciado, solicitando que os trabalhadores identifiquem um número de ordem de compra que eles receberão. Para ajudar os trabalhadores a identificarem mais facilmente a ordem de compra, você aperfeiçoará a primeira página do fluxo adicionando as seguintes opções de nova consulta como [desvios](warehouse-app-detours.md):

- **Pesquisar OCs por fornecedor** – abra uma página que solicita que os trabalhadores insiram um nome de fornecedor ou parte de um nome de fornecedor. Você pode usar caracteres curingas. Por exemplo, se um trabalhador estiver esperando uma entrega de entrada atualmente de um fornecedor que inclua *Tailspin* em seu nome, eles poderão inserir **Tail\*** para exibir um conjunto de cartões para ordens de compra abertas que incluem esse texto. Cada cartão tem vários campos que fornecem informações sobre cada ordem de compra. Além do nome do fornecedor, você pode criar os cartões para que mostrem o número da conta do fornecedor, a data de entrega e o status do documento.
- **Pesquisar OCs para hoje** – abra uma página que não solicita que os trabalhadores insiram dados, mas mostra filtros pré-configurados (como a data de hoje). A página mostra um conjunto de cartões que correspondem ao filtro. Os trabalhadores procedem selecionando um cartão para a ordem de compra para a qual desejam registrar itens de estoque.
- **Pesquisar OCs por item** – abra uma página que solicita que os trabalhadores verifiquem o código de barras de qualquer item no estoque recebido. O fluxo, então, lista todas as ordens de compra abertas que contêm linhas para o número de item verificado. Para cobrir situações em que um código de barras não pode ser lido, você pode adicionar outra pesquisa de desvio a esta página, na qual os colaboradores buscam números de itens em uma ordem de compra específica.

Em cada caso, o trabalhador identifica uma ordem de compra selecionando um cartão e, em seguida, retorna à primeira página, que mostra o número da ordem de compra selecionado. O trabalhador poderá então continuar o fluxo de registro de item de estoque de entrada.

## <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para trabalhar com o cenário de exemplo descrito neste artigo, você deve trabalhar em um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal (empresa) *USMF* antes de começar.

## <a name="configure-the-mobile-device-menu-items"></a>Configurar os itens de menu do dispositivo móvel

Para criar cada uma das novas opções de consulta que devem ser adicionadas à primeira página do fluxo, você deve configurá-la como um item de menu de dispositivo móvel. Posteriormente, as opções de consulta serão disponibilizadas como desvios para o fluxo de *Recebimento de compra*.

### <a name="create-the-look-up-pos-by-vendor-menu-item"></a>Criar o item de menu "Pesquisar OCs por fornecedor"

Crie o item de menu **Pesquisar OCs por fornecedor** seguindo estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ação, selecione **Novo** para adicionar um item de menu do dispositivo móvel.
1. Defina os seguintes valores para o novo item de menu:

    - **Nome do item de menu:** *Pesquisar OCs por fornecedor*
    - **Título:** *Pesquisar OCs por fornecedor*
    - **Modo:** *Indireto*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Código de atividade:** *Consulta de dados*
    - **Usar guia de processos:** *Sim* (este valor é selecionado automaticamente).
    - **Nome da tabela:** *PurchTable* (você deseja procurar os números da ordem de compra nessa tabela.)

1. No painel de ações, selecione **Editar consulta** para definir uma consulta baseada na tabela base selecionada (neste caso, a tabela de ordens de compra).
1. No editor de consultas, na guia **Intervalo**, adicione as seguintes linhas à grade.

    | Tabela | Tabela derivada | Campo | Critérios |
    |---|---|---|---|
    | Ordens de compra | Ordens de compra | Status da ordem de compra | Ordem em aberto |
    | Ordens de compra | Ordens de compra | Data de entrega | (dayRange(-10,10)) |
    | Ordens de compra | Ordens de compra | Nome do Fornecedor | |

1. Selecione **OK**.

    Neste exemplo, o novo item de menu é configurado para localizar ordens de compra abertas que esperam chegar a qualquer momento entre 10 dias no passado e 10 dias no futuro.

    Na consulta, a coluna **Critérios** para *Nome do fornecedor* foi deixada em branco. Portanto, os trabalhadores poderão especificar esse valor enquanto usarem o aplicativo móvel Warehouse Management.

    Se quiser especificar como a lista será classificada, você poderá configurar a classificação na guia **Classificação**.

1. Além de definir a consulta, você deve selecionar quais campos serão mostrados nos cartões da página de listagem de consulta. Portanto, no Painel de Ação, selecione **Lista de campos**.
1. Na página **Lista de campos**, defina os seguintes valores:

    - **Campo de exibição 1:** *PurchId* (este campo será mostrado como o cabeçalho de cada cartão).
    - **Campo de exibição 2:** *PurchStatus*
    - **Campo de exibição 3:** *PurchName*
    - **Campo de exibição 4:** *OrderAccount*
    - **Campo de exibição 5:** *DeliveryDate*
    - **Campo de exibição 6:** *displayDocumentStatus()* (esse valor é um método de exibição, pois o "()" no final indica.)

1. No Painel de ações, selecione **Salvar**. Depois feche a página.

### <a name="create-the-look-up-pos-for-today-menu-item"></a>Criar o item de menu "Pesquisar OCs para hoje"

Crie o item de menu **Pesquisar OCs para hoje** seguindo estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ação, selecione **Novo** para adicionar um item de menu do dispositivo móvel.
1. Defina os seguintes valores para o novo item:

    - **Nome do item de menu:** *Pesquisar OCs para hoje*
    - **Título:** *Pesquisar OCs para hoje*
    - **Modo:** *Indireto*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Código de atividade:** *Consulta de dados*
    - **Usar guia de processos:** *Sim* (este valor é selecionado automaticamente).
    - **Nome da tabela:** *PurchTable* (você deseja procurar os números da ordem de compra nessa tabela.)

1. No painel de ações, selecione **Editar consulta** para definir uma consulta baseada na tabela base selecionada (neste caso, a tabela de ordens de compra).
1. No editor de consultas, na guia **Intervalo**, adicione as seguintes linhas à grade.

    | Tabela | Tabela derivada | Campo | Critérios |
    |---|---|---|---|
    | Ordem de compra | Ordem de compra | Status da ordem de compra | Ordem em aberto |
    | Ordem de compra | Ordem de compra | Data de entrega | (Dia(0)) |

1. Selecione **OK**.

    Neste exemplo, o novo item de menu é configurado para localizar ordens de compra abertas que são esperadas para chegar hoje.

    Se quiser especificar como a lista será classificada, você poderá configurar a classificação na guia **Classificação**.

1. Além de definir a consulta, você deve selecionar quais campos serão mostrados nos cartões da página de listagem de consulta. Portanto, no Painel de Ação, selecione **Lista de campos**.
1. Na página **Lista de campos**, defina os seguintes valores:

    - **Campo de exibição 1:** *PurchName* (este campo será mostrado como o cabeçalho de cada cartão).
    - **Campo de exibição 2:** *PurchId*
    - **Campo de exibição 3:** *PurchStatus*
    - **Campo de exibição 4:** *DlvMode*
    - **Campo de exibição 5:** *DlvTerm*
    - **Campo de exibição 6:** *OrderAccount*
    - **Campo de exibição 7:** *VendorName()* (esse valor é um método de exibição, pois o "()" no final indica.)

1. No Painel de ações, selecione **Salvar**. Depois feche a página.

### <a name="create-the-look-up-pos-by-item-menu-item"></a>Criar o item de menu "Pesquisar OCs por item"

Crie o item de menu **Pesquisar OCs por item** seguindo estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ação, selecione **Novo** para adicionar um item de menu do dispositivo móvel.
1. Defina os seguintes valores para o novo item:

    - **Nome do item de menu:** *Pesquisar OCs por item*
    - **Título:** *Pesquisar OCs por item*
    - **Modo:** *Indireto*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Código de atividade:** *Consulta de dados*
    - **Usar guia de processos:** *Sim* (este valor é selecionado automaticamente).
    - **Nome da tabela:** *PurchLine* (você deseja procurar os números da ordem de compra com base no número do item por meio dos dados da linha).

1. No painel de ações, selecione **Editar consulta** para definir uma consulta baseada na tabela base selecionada (neste caso, a tabela linhas da ordem de compra, mas você pode usar qualquer um dos valores relacionados ao cabeçalho ao ingressar no *PurchTable*).
1. No editor de consultas, na guia **Intervalo**, adicione as seguintes linhas à grade.

    | Tabela | Tabela derivada | Campo | Critérios |
    |---|---|---|---|
    | Linhas de ordem de compra | Linhas de ordem de compra | Status da linha | Ordem em aberto |
    | Linhas de ordem de compra | Linhas de ordem de compra | Data de entrega | (dayRange(-10,10)) |
    | Linhas de ordem de compra | Linhas de ordem de compra | Número do item | |

1. Selecione **OK**.

    Neste exemplo, o novo item de menu é configurado para localizar linhas da ordem de compra abertas que devem chegar a qualquer momento entre 10 dias no passado e 10 dias no futuro.

    Na consulta, a coluna **Critérios** para *Número do item* foi deixada em branco. Portanto, os trabalhadores poderão especificar esse valor enquanto usarem o aplicativo móvel Warehouse Management.

    Se quiser especificar como a lista será classificada, você poderá configurar a classificação na guia **Classificação**.

1. Além de definir a consulta, você deve selecionar quais campos serão mostrados nos cartões da página de listagem de consulta. Portanto, no Painel de Ação, selecione **Lista de campos**.
1. Na página **Lista de campos**, defina os seguintes valores:

    - **Campo de exibição 1:** *PurchId* (este valor de campo será usado como o cabeçalho de cada cartão).
    - **Campo de exibição 2:** *VendAccount*
    - **Campo de exibição 3:** *PurchQty*
    - **Campo de exibição 4:** *PurchUnit*
    - **Campo de exibição 5:** *PurchStatus*

1. No Painel de ações, selecione **Salvar**. Depois feche a página.

## <a name="add-the-new-mobile-device-menu-items-to-a-menu"></a>Adicionar os novos itens de menu de dispositivo móvel a um menu

Agora, os três novos itens de menu do dispositivo móvel estão prontos para serem adicionados ao menu do dispositivo móvel. Essa tarefa deve ser concluída para que os itens de menu possam ser usados como parte de um processo de desvio. Neste exemplo, você criará um novo submenu e adicionará os novos itens de menu a ele.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. Defina os seguintes valores no cabeçalho do novo registro:

    - **Nome:** *Consulta*
    - **Descrição:** *Consulta*

1. Na lista **Menus e itens de menu disponíveis**, selecione o primeiro dos itens de menu do dispositivo móvel que você acabou de criar. Em seguida, selecione o botão de seta para a direita para mover esse item para a lista **Estrutura de menu**.
1. Repita a etapa anterior para os outros dois novos itens de menu.
1. No painel de lista à esquerda, selecione o menu **Principal**.
1. Na lista **Menus e itens de menu disponíveis**, role até a seção **Menus** e selecione o novo menu **Consulta**. Em seguida, selecione o botão de seta para a direita para mover esse item para a lista **Estrutura de menu**.

## <a name="configure-detours-in-your-mobile-device-steps"></a>Configurar desvios em suas etapas do dispositivo móvel

Para concluir a configuração, agora você deve usar a configuração de desvio na página **Etapas do dispositivo móvel** para adicionar os três novos itens de menu de dispositivo móvel à etapa de identificação da ordem de compra existente no fluxo de *Recebimento da compra*.

1. Acesse **Gerenciamento de depósito \> Configuração > Dispositivo móvel \> Etapas do dispositivo móvel**.
1. No campo **Filtro**, insira *PONum*. Depois *ID da Etapa: "PONum"* na lista suspensa.
1. Enquanto o registro encontrado é selecionado na grade, selecione **Adicionar configuração da etapa** no painel de ações. Na caixa de diálogo suspensa exibida, defina o campo **Item de menu** como *Recebimento de Compra*. Depois, selecione **OK** para fechar a caixa de diálogo.
1. Na página detalhes da nova configuração de etapa (**Recebimento de Compra: PONum**), na guia rápida **Desvios disponíveis (itens de menu)**, selecione **Adicionar** na barra de ferramentas.
1. Na caixa de diálogo **Adicionar desvio**, localize e selecione o item de menu **Pesquisar OCs por fornecedor** criado anteriormente.
1. Selecione **OK** para fechar a caixa de diálogo e adicionar o item de menu selecionado à lista de desvios.
1. Selecione o novo desvio e **Selecionar campos para envio** na barra de ferramentas.
1. Na caixa de diálogo **Selecionar campos para envio** não adicione nada à seção **Enviar do recebimento de compras** porque você não deseja passar nenhum valor para o item de menu de desvio. Porém, na seção **Trazer de volta de Pesquisar OCs por fornecedor**, defina o valor a seguir para a linha vazia que já foi adicionada ali:

    - **Copiar de Pesquisar OCs por fornecedor:** *Ordem de compra*
    - **Colar no recebimento de compra:** *Ordem de compra*

1. Selecione **OK** para fechar a caixa de diálogo.
1. Repita as etapas 4 a 9 para os outros dois novos itens de menu (**Pesquisar OCs para hoje** e **Pesquisar OCs por item**). Como para o **Pesquisar OCs por fornecedor**, você não deseja enviar dados para esses desvios, mas deseja retornar um número de ordem de compra.
1. Feche a página.

## <a name="try-a-purchase-receiving-flow-that-has-a-data-inquiry-as-part-of-a-detour"></a>Experimente um fluxo de recebimento de compra que tenha uma consulta de dados como parte de um desvio

Siga estas etapas para testar a configuração do seu novo aplicativo móvel.

1. Crie várias ordens de compra com linhas para o depósito 51.
1. Acesse um dispositivo móvel ou emulador que esteja executando o aplicativo móvel do Gerenciamento de Depósito e entre no depósito 51 usando *51* como a ID de usuário e *1* como a senha.
1. No menu de aplicativo móvel, selecione **Entrada** e, em seguida **Recebimento de compra**.

    Você verá a seguinte página, que inclui os três novos itens de menu.

    ![Recebimento de compra usando número da OC.](media/wma-purchase-receive-po-num-with-detours.png "Recebimento de compra usando número da OC")

1. Experimente os diferentes recursos e observe que você pode devolver um número de ordem de compra selecionando um dos cartões na lista.

    ![Recebimento de compra usando a pesquisa da OC por fornecedor, exemplo 1.](media/wma-purchase-receive-lookup-po-vendor-keyin-detours.png "Recebimento de compra usando a pesquisa da OC por fornecedor, exemplo 1")

    ![Recebimento de compra usando a pesquisa da OC por fornecedor, exemplo 2.](media/wma-purchase-receive-lookup-po-vendor-detours.png "Recebimento de compra usando a pesquisa da OC por fornecedor, exemplo 2")

> [!TIP]
> Em vez de executar o fluxo de recebimento, fazendo uma pesquisa no item de menu **Recebimento de compra**, você pode iniciar a partir de um fluxo de consulta (**Consulta \> Principal \>, Pesquisar OCs por fornecedor**) e chamar um desvio para executar o fluxo desejado, selecionando um dos cartões da lista. Para usar essa abordagem, você pode definir um desvio na página **Etapas do dispositivo móvel** para a etapa que tem um valor de **ID da Etapa** de *GenericDataInquiryList*. Como esse fluxo é um fluxo de desvio, você não pode chamar mais desvios a partir dele. Portanto, quando você chegar à tela de entrada de número de item, por exemplo, a pesquisa não estará disponível nela, pois o sistema oferece suporte apenas a um nível de desvios.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
