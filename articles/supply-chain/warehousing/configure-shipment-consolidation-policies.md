---
title: Configurar políticas de consolidação de remessa
description: Este artigo explica como configurar políticas de consolidação de remessa padrão e personalizadas.
author: Mirzaab
ms.date: 09/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0312d425d2ebc5311e894030423a916b90f1881a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427973"
---
# <a name="configure-shipment-consolidation-policies"></a>Configurar políticas de consolidação de remessa

[!include [banner](../includes/banner.md)]

O processo de consolidação de remessa que usa políticas de consolidação de remessa permite a consolidação de remessa automatizada durante a liberação automatizada e manual para o depósito. Depois de ativar esse recurso, você deve configurar as políticas iniciais. Se nenhuma política estiver configurada, cada linha de venda gerará uma remessa separada com uma única linha de carga.

Os cenários apresentados neste artigo mostram como configurar políticas de consolidação de remessa padrão e personalizadas.

> [!WARNING]
> Se você atualizar um sistema Microsoft Dynamics 365 Supply Chain Management no qual esteve usando o recurso de consolidação de remessa herdada, a consolidação pode parar de funcionar como esperado, a menos que você siga o aviso fornecido aqui.
>
> Em instalações do Supply Chain Management em que o recurso *Políticas de consolidação de remessa* está desativado, habilite a consolidação de remessa usando a configuração **Consolidar remessa na liberação para o depósito** para cada depósito individual. Este recurso é obrigatório a partir da versão 10.0.29. Quando estiver ativado, a configuração **Consolidar remessa na liberação para o depósito** será ocultada e a funcionalidade será substituída pelas *Políticas de consolidação de remessa* descritas neste artigo. Cada política estabelece regras de consolidação e inclui uma consulta para controlar o local em que a política se aplica. Quando você ativar o recurso pela primeira vez, nenhuma política de consolidação de remessa será definida na página **Políticas de consolidação de remessa**. Quando nenhuma política é definida, o sistema usa o comportamento herdado. Portanto, cada depósito existente continuará respeitando a configuração **Consolidar remessa na liberação para o depósito**, mesmo que a configuração esteja oculta. No entanto, depois de criar pelo menos uma política de consolidação de remessa, as configurações **Consolidar remessa na liberação para o depósito** não terão mais efeito algum e a funcionalidade de consolidação será totalmente controlada pelas políticas.
>
> Depois de definir pelo menos uma política de consolidação de remessa, o sistema verificará as políticas de consolidação toda vez que uma ordem for liberada para o depósito. O sistema processa as políticas usando a classificação definida pelo valor **Sequência de políticas** de cada política. Ele aplica a primeira política em que a consulta corresponde à nova ordem. Se nenhuma consulta corresponder à ordem, cada ordem gerará uma remessa separada com uma única linha de carga. Portanto, como alternativa, recomendamos que você crie uma política padrão que se aplique a todos os depósitos e grupos por número de ordem. Dê a essa política de fallback o maior valor de **Sequência de políticas**, para que ela seja processada por último.
>
> Para reproduzir o comportamento herdado, você deve criar uma política que não agrupe por número de ordem e que tenha critérios de consulta que incluam todos os depósitos relevantes.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Ative o recurso de políticas de consolidação de remessa

Para usar o recurso *Políticas de consolidação de remessa*, ele precisa estar ativado no sistema. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão ativar ou desativar essa funcionalidade procurando o recurso *Políticas de consolidação da remessa* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-your-initial-consolidation-policies"></a><a name="initial-policies"></a>Configurar suas políticas de consolidação iniciais

Se você estiver trabalhando com um novo sistema ou um sistema no qual você acabou de ativar o recurso *Políticas de consolidação de remessa* pela primeira vez, siga estas etapas para configurar suas diretivas de consolidação de remessa iniciais.

1. Acesse **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. No Painel de Ações, selecione **Criar configuração padrão** para criar as seguintes políticas:

    - Uma política que tem o nome *Padrão* para o tipo de política *Ordens de venda*.
    - Uma política que tem o nome *Padrão* para o tipo de política *Emissão de transferência*.
    - Uma política que tem o nome *CrossOrder* para o tipo de política *Emissão de transferência*. (Essa diretiva é criada somente se você tiver pelo menos um depósito no qual a configuração herdada **Consolidar remessa na liberação para o depósito** tiver sido habilitada.)
    - Uma política que tem o nome *CrossOrder* para o tipo de política *Ordens de venda*. (Essa diretiva é criada somente se você tiver pelo menos um depósito no qual a configuração herdada **Consolidar remessa na liberação para o depósito** tiver sido habilitada.)

    > [!NOTE]
    > - As duas políticas *CrossOrder* consideram o mesmo conjunto de campos que a lógica anterior. No entanto, eles também consideram o campo número da ordem. (Esse campo é usado para consolidar linhas em remessas, com base em fatores como o depósito, o modo de transporte de entrega e o endereço.)
    > - As duas políticas *Padrão* consideram o mesmo conjunto de campos que a lógica anterior. No entanto, eles também consideram o campo número da ordem. (Esse campo é usado para consolidar linhas em remessas, com base em fatores como o número da ordem, o modo de transporte de entrega e o endereço).

1. Se o sistema tiver gerado uma política *CrossOrder* para o tipo de política *Ordens de venda*, selecione-a e ,depois, no Painel de Ações, selecione **Editar consulta**. No editor de consultas, você pode ver para qual dos seus depósitos a configuração **Consolidar remessa na liberação para o depósito** foi habilitada. Portanto, essa política reproduz as configurações anteriores para esses depósitos.
1. Personalize as novas políticas padrão, conforme a necessidade, adicionando ou removendo campos e/ou editando as consultas. Você também pode adicionar quantas políticas forem necessárias. Para obter exemplos que mostram como personalizar e configurar suas políticas, consulte o cenário de exemplo mais adiante neste artigo.

## <a name="scenario-configure-custom-shipment-consolidation-policies"></a>Cenário: configurar políticas de consolidação de remessa personalizadas

Este cenário fornece um exemplo que mostra como configurar políticas de consolidação de remessa personalizadas e testá-las usando dados de demonstração. As políticas personalizadas podem dar suporte aos requisitos de negócios complexos em que a consolidação de remessa depende de várias condições. Para cada exemplo de política mais adiante neste cenário, é incluída uma breve descrição do caso de negócio. Essas políticas de exemplo devem ser configuradas em uma sequência que garanta uma avaliação do tipo pirâmide das consultas. (Em outras palavras, as políticas com mais condições devem ser avaliadas como as de maior prioridade.)

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Este cenário faz referência a valores e registros incluídos nos [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) padrão que são fornecidos para o Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como *USMF* antes de começar.

### <a name="prepare-master-data-for-this-scenario"></a>Preparar dados mestres para este cenário

Antes de passar pelos exercícios deste cenário, você deve preparar os dados mestre necessários para fazer a filtragem, conforme descrito nas subseções a seguir. (Esses pré-requisitos também se aplicam aos cenários que são listados na seção [Exemplos de cenários de como usar políticas de consolidação de remessa](#example-scenarios).)

#### <a name="create-two-new-product-filter-codes"></a>Criar dois novos códigos de filtro de produtos

1. Acesse **Gerenciamento de depósito \> Configuração \> Filtros de produtos \> Filtros de produtos** e adicionar dois filtros de produtos:

    - Filtro de produto 1:

        - **Código do filtro:** *Inflamável*
        - **Título do filtro:** *Código 4*

    - Filtro de produto 2:

        - **Código do filtro:** *Explosivo*
        - **Título do filtro:** *Código 4*

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Abra o produto que tem número de item *M9200*. (O produto selecionado deve estar habilitado para processos de depósito avançado \[WMS\] e este produto é pré-habilitado para processos WMS em dados de demonstração do **USMF**.)
1. Na Guia Rápida **Depósito**, defina o campo **Código 4** como *Inflamável*.
1. Feche a página.
1. Abra o produto que tem número de item *M9201*. (Este produto também é pré-habilitado para processos WMS em dados de demonstração do **USMF**.)
1. Na Guia Rápida **Depósito**, defina o campo **Código 4** como *Explosivo*.
1. Feche a página.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Crie um novo modo de transporte de entrega

1. Acesse **Gerenciamento de transporte \> Configuração \> Transportadoras \> Modo**.
1. Crie um modo de transporte que será usado em consultas de consolidação e nomeie-o *Airways*.
1. Acesse **Gerenciamento de transporte \> Configurar \> Transportadoras \> Transportadoras**.
1. Crie uma transportadora com as seguintes configurações:

    - **Transportadora:** *Airways*
    - **Nome:** *Airways*
    - **Modo:** *Airways*

1. Na Guia Rápida **Serviços** da nova transportadora, adicione uma linha com as seguintes configurações:

    - **Serviço da transportadora:** *Aéreo*
    - **Método de transporte:** *Aéreo*

1. No Painel de ações, selecione **Salvar**.

    > [!NOTE]
    > Quando você salva a nova transportadora, o campo **Modo de entrega** para a nova linha na grade **Serviços** é automaticamente definido como *Airwa-Air*. Quando você usar o modo de entrega *Airwa-Air* para uma ordem de venda, o modo de transporte *Airways* será usado para remessas relacionadas.

#### <a name="create-an-order-pool"></a>Crie um grupo de ordens

1. Acesse **Vendas e marketing \> Configuração \> Ordens de venda \> Grupos de ordens**.
1. Crie um grupo de ordens que será usado para a consulta de consolidação. Esse grupo de ordens deve ter as seguintes configurações:

    - **Grupo:** Insira um número inteiro que não esteja sendo usado por outro grupo.
    - **Nome:** *ShipCons*

1. Acesse **Vendas e marketing \> Clientes \> Todos os clientes**.
1. Abra o cliente que tem número de conta *US-003*.
1. Na Guia Rápida **Padrões da ordem de venda**, defina o campo **Grupo de ordens de venda** como o grupo de ordens que você acabou de criar.
1. Feche a página e, depois, repita as etapas 4 e 5 para o cliente que tem número de conta *US-004*.

### <a name="create-example-policy-1"></a>Crie o exemplo de política 1

Neste exemplo, você criará uma política *Cliente+Modo* que pode ser usada para o seguinte caso de negócios:

- A política consultará uma conta de cliente específica (*US-001*) e um modo de entrega específico (*Airwa-Air*).
- A consolidação com remessas abertas está desativada.
- A consolidação é feita por ID da ordem. (Em outras palavras, haverá remessas separadas por ordem, depósito etc.)

Siga as etapas a seguir para criar a política de consolidação de remessa para este caso de negócios.

1. Acesse **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. Defina o campo **Tipo de política** como *Ordens de venda*.
1. No Painel de Ações, selecione **Novo** para criar uma política com as seguintes configurações:

    - **Nome da política:** *CustomerMode*
    - **Descrição da política:** *Conta do cliente e modo de entrega*

1. Mantenha a opção **Consolidar com remessas abertas** definida como *Não*.
1. No Painel de ações, selecione **Salvar**.
1. Na Guia Rápida **Campos de consolidação**, na lista **Campos restantes**, selecione a linha na qual o campo **Nome do campo** está definido como *Modo de entrega*.
1. Selecione o botão **Adicionar** ![Seta para a direita.](media/forward-button.png) para mover o campo para a lista **Campos selecionados**.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo Editor de consultas, na guia **Intervalo**, na grade, localize a linha na qual o campo **Campo** está definido como *Conta de cliente* e defina o campo **Critérios** dessa linha como *US-001*.
1. Selecione **Adicionar** para adicionar uma linha com as seguintes configurações à grade:

    - **Tabela:** *Linhas da ordem*
    - **Tabela derivada:** *Linhas da ordem*
    - **Campo:** *Modo de entrega*
    - **Critérios:** *Airwa-Air*

1. Selecione **OK** para fechar a caixa de diálogo.

> [!NOTE]
> Para esse caso de negócios, as linhas de ordem para o cliente *US-001* que usam o modo *Airwa-Air* de entrega não serão consolidadas em ordens. Essa política deve ser usada primeiro em uma sequência, em casos nos quais as remessas para todos os outros modos de entrega são consolidadas para esse cliente.

### <a name="create-example-policy-2"></a>Crie o exemplo de política 2

Neste exemplo, você criará uma política *Mercadorias perigosas* que pode ser usada para o seguinte caso de negócios:

- A política consultará um código de filtro específico (*perigoso*) e um modo de entrega específico (*Airwa-Air*).
- A consolidação com remessas abertas está ativada.
- A consolidação é feita em ordens. (Em outras palavras, haverá remessas separadas por conta, depósito e assim por diante, mas somente no grupo de itens especificado na consulta.)

Siga as etapas a seguir para criar a política de consolidação de remessa para este caso de negócios.

1. Acesse **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. Defina o campo **Tipo de política** como *Ordens de venda*.
1. No Painel de Ações, selecione **Novo** para criar uma política com as seguintes configurações:

    - **Nome da política:** *Tipo de item*
    - **Descrição da política:** *Consolidar o mesmo tipo de item em ordens*

1. Defina a opção **Consolidar com remessas abertas** como *Sim*.
1. No Painel de ações, selecione **Salvar**.
1. Na Guia Rápida **Campos de consolidação**, na lista **Campos restantes**, selecione a linha na qual o campo **Nome do campo** está definido como *Modo de entrega*.
1. Selecione o botão **Adicionar** ![Seta para a direita.](media/forward-button.png) para mover o campo para a lista **Campos selecionados**.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Junções**, expanda e selecione **Tabelas \> Carregar detalhes** na árvore.
1. Selecione **Adicionar junção de tabela**.
1. Na grade de relações que aparece, localize e selecione a linha na qual o campo **Relação** está definido como *Número de item de depósito (Número de item)* e marque **Selecionar**. 
1. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha com as seguintes configurações à grade:

    - **Tabela:** *Número de item de depósito*
    - **Tabela derivada:** *Número de item de depósito*
    - **Campo:** *Código 4*
    - **Critérios:** *Inflamável*

1. Selecione **OK** para fechar a caixa de diálogo.

> [!NOTE]
> Para esse caso de negócios, todas as linhas de ordem em que os itens têm um código de filtro específico (ou seja, o código de filtro no qual o campo **Código 4** está definido como *Inflamável*) será consolidado com outros itens do mesmo tipo em ordens. Se houver uma remessa aberta para a mesma conta, depósito e grupo de itens, as novas linhas serão anexadas a ela.

### <a name="create-example-policy-3"></a>Crie o exemplo de política 3

Neste exemplo, você criará uma política *Requisitos de clientes* que pode ser usada para o seguinte caso de negócios:

- A política consultará uma conta de cliente específica.
- A consolidação com remessas abertas está ativada.
- A consolidação é realizada em ordens, mas se baseia nas requisições dos clientes. (Em outras palavras, várias ordens serão agrupadas em remessas, com base no mesmo número de requisição do cliente e depósito.)

Siga as etapas a seguir para criar a política de consolidação de remessa para este caso de negócios.

1. Acesse **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. Defina o campo **Tipo de política** como *Ordens de venda*.
1. No Painel de Ações, selecione **Novo** para criar uma política com as seguintes configurações:

    - **Nome da política:** *CustomerOrderNo*
    - **Descrição da política:** *Consolidar linhas com base na OC do cliente*

1. Defina a opção **Consolidar com remessas abertas** como *Sim*.
1. No Painel de ações, selecione **Salvar**.
1. Na Guia Rápida **Campos de consolidação**, na lista **Campos restantes**, selecione a linha na qual o campo **Nome do campo** está definido como *Requisição do cliente*.
1. Selecione o botão **Adicionar** ![Seta para a direita.](media/forward-button.png) para mover o campo para a lista **Campos selecionados**.
1. Na lista **Campos restantes**, selecione a linha na qual o campo **Nome do campo** está definido como *Modo de entrega*.
1. Selecione o botão **Adicionar** ![Seta para a direita.](media/forward-button.png) para mover o campo para a lista **Campos selecionados**.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo**, localize a linha na qual o campo **Campo** está definido como *Conta de cliente* e defina o campo **Critérios** dessa linha como *US-001*.
1. Selecione **OK** para fechar a caixa de diálogo.

> [!NOTE]
> Para esse caso de negócios, todas as linhas de ordem nas quais as ordens de venda têm o mesmo número de requisição do cliente serão consolidadas em uma remessa, independentemente do número da ordem de venda. (O número da requisição do cliente é usado como o número da ordem de compra do cliente \[OC\].) Se houver uma remessa aberta para a mesma conta, depósito e requisição de cliente, as novas linhas serão anexadas a ela. Esta política poderá ser usada se o cliente enviar linhas de ordem adicionais com o mesmo número de OC várias vezes durante um dia e desejar que todas as linhas sejam agrupadas em uma remessa. (Ou seja, haverá um conhecimento de embarque e uma guia de remessa.)

### <a name="create-example-policy-4"></a>Crie o exemplo de política 4

Neste exemplo, você criará uma política *Clientes permitem consolidação* que pode ser usada para o seguinte caso de negócios:

- A política consultará um grupo de ordens específico para identificar clientes que aceitam remessas consolidadas.
- A consolidação com remessas abertas está desativada.
- A consolidação é realizada em ordens usando os campos selecionados pela política CrossOrder padrão (para replicar a caixa de seleção **Consolidar a remessa na liberação para o depósito** anterior).

- Você pode substituir a regra em uma ordem de venda selecionando um grupo de ordens diferente.

Siga as etapas a seguir para criar a política de consolidação de remessa para este caso de negócios.

1. Acesse **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. Defina o campo **Tipo de política** como *Ordens de venda*.
1. No Painel de Ações, selecione **Novo** para criar uma política com as seguintes configurações:

    - **Nome da política:** *Grupo de ordens*
    - **Descrição da política:** *Consolidar em ordens com base no grupo de ordens*

1. Mantenha a opção **Consolidar com remessas abertas** definida como *Não*.
1. No Painel de ações, selecione **Salvar**.
1. Na Guia Rápida **Campos de consolidação**, na lista **Campos restantes**, selecione a linha na qual o campo **Nome do campo** está definido como *Modo de entrega*.
1. Selecione o botão **Adicionar** ![Seta para a direita.](media/forward-button.png) para mover o campo para a lista **Campos selecionados**.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consulta, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha com as seguintes configurações à grade:

    - **Tabela:** *Ordens de venda*
    - **Tabela derivada:** *Ordens de venda*
    - **Campo:** *Grupo*
    - **Critérios:** *ShipCons*

1. Selecione **OK** para fechar a caixa de diálogo.

> [!NOTE]
> Para esse caso de negócios, todas as linhas de ordem nas quais as ordens de venda pertencem ao mesmo grupo de ordens serão consolidadas em uma remessa em ordens de venda para a mesma conta, depósito e modo de transporte de entrega. Em vez do grupo de ordens, você pode usar qualquer outro campo para diferenciar um grupo de clientes e usar o cabeçalho da ordem de venda por padrão. Você poderá usar essa abordagem se o cliente, não o depósito, estiver gerando a necessidade de consolidação. (Na lógica de consolidação anterior, o depósito levou à necessidade de consolidação.)

### <a name="create-example-policy-5"></a>Crie o exemplo de política 5

Neste exemplo, você criará uma política *Depósitos permitem consolidação* que pode ser usada para o seguinte caso de negócios:

- A política consultará um grupo de ordens específico para identificar depósitos que podem consolidar remessas.
- A consolidação com remessas abertas está desativada.
- A consolidação é realizada em ordens usando os campos selecionados pela política CrossOrder padrão (para replicar a caixa de seleção **Consolidar a remessa na liberação para o depósito** anterior).

Normalmente, esse caso de negócios pode ser resolvido usando as políticas padrão criadas no [Configurar suas políticas de consolidação iniciais](#initial-policies). No entanto, você também pode criar manualmente políticas semelhantes seguindo essas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. Defina o campo **Tipo de política** como *Ordens de venda*.
1. No Painel de Ações, selecione **Novo** para criar uma política com as seguintes configurações:

    - **Nome da política:** *Ordem cruzada*
    - **Descrição da política:** *Consolidação de ordem cruzada para depósitos específicos*

1. Mantenha a opção **Consolidar com remessas abertas** definida como *Não*.
1. No Painel de ações, selecione **Salvar**.
1. Na Guia Rápida **Campos de consolidação**, no campo **Campos restantes**, selecione a linha na qual o campo **Nome do campo** está definido como *Modo de entrega*.
1. Selecione o botão **Adicionar** ![Seta para a direita.](media/forward-button.png) para mover o campo para a lista **Campos selecionados**.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo**, localize a linha na qual o campo **Campo** está definido como *Depósito* e defina o campo **Critérios** dessa linha como *61, 63*.
1. Selecione **OK** para fechar a caixa de diálogo.

### <a name="set-the-order"></a>Defina a ordem

Você criou todas as suas políticas e agora deve estabelecer a ordem em que elas serão aplicadas. Para usar uma abordagem de pirâmide, em que as políticas com mais condições são avaliadas como de maior prioridade, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. Defina o campo **Tipo de política** como *Ordens de venda*.
1. Selecione cada política listada na coluna esquerda e use os botões **Mover para cima** e **Mover para baixo** no Painel de Ações para organizar as políticas na seguinte ordem:

    1. CustomerMode
    1. Tipo de item
    1. CustomerOrderNo
    1. Grupo de ordens
    1. Ordem cruzada
    1. Padrão

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Exemplos de cenários de como usar políticas de consolidação de remessa

Os cenários a seguir ilustram como você pode usar as políticas de consolidação de remessa criadas durante a leitura deste artigo. Cada cenário explica o processo de consolidação de uma remessa que usa políticas de consolidação de remessa durante a liberação automatizada ou manual para o depósito:

- Cenário 1: [Consolidar remessas quando são liberadas para o depósito usando a liberação automática de ordens de venda](../warehousing/consolidate-shipments-automatic.md)
- Cenário 2: [Consolidar remessas quando a política de consolidação de remessa for substituída da página Liberar para depósito](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Cenário 3: [Consolidar remessas usando Liberar para o depósito da bancada de planejamento de carga](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Cenário 4: [Consolidar remessas usando a bancada de consolidação de remessa](../warehousing/consolidate-shipments-manual-workbench.md)
- Cenário 5: [Consolidar remessas manualmente usando a página Consolidar remessas](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de políticas de consolidação de remessa](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
