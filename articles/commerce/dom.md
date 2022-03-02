---
title: Gerenciamento de ordem distribuído (DOM)
description: Este tópico descreve a funcionalidade Gerenciamento de ordem distribuído (DOM) do Dynamics 365 Commerce.
author: josaw1
ms.date: 02/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f19fbe2a9f768a91c495a6a4bcb0e475adb867ae
ms.sourcegitcommit: 8bea5a0c232ac31dcafddfcc0d715c496d8dd445
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102000"
---
# <a name="distributed-order-management-dom"></a>Gerenciamento de ordem distribuído (DOM)

[!include [banner](includes/banner.md)]

Este tópico descreve a funcionalidade Gerenciamento de ordem distribuído (DOM) do Microsoft Dynamics 365 Commerce.

O DOM é uma solução de otimização de processamento de ordens de omnicanal que ajuda a maximizar o processamento de ordens em uma rede de cadeia de fornecimento. DOM ajuda você a garantir que os produtos sejam entregues aos clientes nas quantidades corretas, das fontes certas e no momento adequado. O DOM também pode ajudar você a maximizar lucros, minimizar custos e atender a requisitos de nível de serviço.

O DOM usa modelos de inteiro misto (MIP) e de análise de previsão para realizar otimizações a nível de lote e ordens individuais. Esse recurso permite que os varejistas usem regras definidas para equilibrar várias necessidades de processamento de ordens conflitantes. Em uma rede de fornecimento moderno, em que o processamento de produtos pode vir de vários canais, as organizações devem se adaptar rapidamente a alterações de ordens, questões de disponibilidade do fornecedor e picos na demanda. O DOM ajuda a maximizar o processamento da ordem e a encontrar as fontes corretas para a entrega de produtos, com base nas restrições e objetivos comerciais, como minimizar os custos ao processar ordens de fontes mais próximas. O DOM usa a distância entre as fontes de processamento de produtos e os destinos de remessa, os fatores de custo definidos como objetivos de otimização e as regras definidas como restrições, como estoque em nós de processamento para otimizar o processamento da ordem. O DOM permite a definição de vários perfis que permitem que as empresas executem diferentes estratégias de otimização, dependendo do tipo de segmento comercial ou de consumidor. 

A ilustração a seguir mostra o ciclo de vida de uma ordem de venda em um sistema de DOM.

![Ciclo de vida da ordem de venda no contexto de DOM.](./media/flow.png "Ciclo de vida da ordem de venda no contexto do DOM")

## <a name="set-up-dom"></a>Configurar DOM

1. Acesse **Administração do sistema \> Configurar \> Configuração de licença**.
2. Na guia **Chaves de configuração**, expanda o nó **Commerce** e marque a caixa de seleção **Gerenciamento de ordem distribuído**.
3. Vá para **Retail e Commerce \> Gerenciamento de ordem distribuído \> Configuração \> Parâmetros de DOM**.
4. Na guia **Geral**, defina os seguintes valores:

    - **Habilite o gerenciamento de ordem distribuído** – Defina esta opção como **Sim**.
    - **Confirmar o uso do Bing Mapas para DOM** – Defina esta opção como **Sim**.

        > [!NOTE]
        > Você poderá definir esta opção como **Sim** somente se a opção **Habilitar Bing Mapas** na guia **Bing Mapas** da página **Parâmetros compartilhados de comércio** (**Retail e Commerce \> Configuração de sedes \> Parâmetros \> Parâmetros compartilhados do Commerce**) também estiver configurada como **Sim** e se uma chave válida for inserida no campo **Chave do Bing Mapas**.
        >
        > No portal [Centro de Desenvolvedores do Bing Mapas](https://www.bingmapsportal.com/), você pode restringir o acesso nas chaves de API do Bing Mapas a um conjunto de domínios especificados. Com este recurso, os clientes podem definir um conjunto estrito de valores de referenciais ou intervalos de endereços IP para os quais a chave será validada. As solicitações originadas na sua lista de permissões serão processadas normalmente, enquanto as solicitações de fora da lista retornarão uma resposta de acesso negado. A adição da segurança de domínio à chave da API é opcional e as chaves não alteradas continuarão funcionando. A lista de permissões para uma chave é independente de todas as outras chaves, permitindo que você tenha regras distintas para cada uma delas. O Gerenciamento de Ordem Distribuído não é compatível com a configuração de propriedades referidas pelo domínio.

    - **Período de retenção em dias** – Especifique por quanto tempo os planos de atendimento que as execuções do DOM geram são mantidos no sistema. O trabalho em lotes da **configuração de trabalho de exclusão de dados de atendimento do DOM** excluirá qualquer plano de atendimento que tenha excedido o número de dias especificado aqui.
    - **Período de rejeição (em dias)** – Especifique quanto tempo deve passar para que uma linha da ordem rejeitada possa ser atribuída ao mesmo local.

5. Na guia **Agente de resolução**, defina os seguintes valores:

    - **Máximo de tentativas de atendimento automático** – Especifique quantas vezes o mecanismo de DOM tentará agenciar uma linha da ordem para um local. Se o mecanismo de DOM não conseguir agenciar uma linha da ordem para um local em determinando número de tentativas, marcará a linha da ordem como uma exceção. Ele vai ignorar essa linha nas execuções futuras até que o status seja redefinido manualmente.
    - **Raio de lojas locais na região** – Insira um valor. Este campo ajuda a determinar como os locais são agrupados e considerados iguais em termos de distância. Por exemplo, se você inserir **161**, todas as loja ou centros de distribuição no raio do 161 km do endereço de atendimento serão considerados iguais em termos da distância.
    - **Tipo de agente de resolução** – Selecione um valor. Dois tipos de agentes da resolução foram liberados com o Commerce: **Agente de Resolução de Produção** e **Agente de Resolução Simplificado**. Para todos os computadores que executarão o DOM (ou seja, todos os servidores que fazem parte do grupo DOMBatch), o **Agente de Resolução de Produção** deve estar selecionado. O Agente de Resolução de Produção exige a chave de licença especial que, por padrão, é licenciada e implantada em ambientes de produção. Em ambientes de nível 2+ mais recentes, o Agente de Resolução de Produção já estará autorizado. Para ambientes de não produção, essa chave de licença deve ser implantada manualmente. Para implantar manualmente a chave de licença, siga estas etapas:

        1. No Microsoft Dynamics Lifecycle Services, abra a Biblioteca de ativos compartilhados, selecione **Modelo** como o tipo de ativo e baixe o arquivo **Licença do DOM**.
        1. Inicie o Gerenciador dos Serviços de Informações da Internet (IIS) da Microsoft, clique com o botão direito do mouse no **Site de Serviço do AOS** e selecione **Explorar**. Uma janela do Windows Explorer será aberta em **\<AOS service root\>\\webroot**. Anote o caminho da \<AOS Service root\>, porque ele será usado na próxima etapa.
        1. Copie o arquivo de configuração no diretório **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        1. Acesse o cliente do Headquarters e abra a página **Parâmetros do DOM**. Na guia **Agente de Resolução**, no campo **Tipo de Agente de Resolução**, selecione **Agente de Resolução de Produção** e confirme que nenhuma mensagem de erro aparecerá.

        > [!NOTE]
        > O Agente de Resolução Simplificado é fornecido para que os varejistas possam experimentar o recurso DOM sem precisarem implantar a licença especial. As organizações não devem usar o Agente de Resolução Simplificado em ambientes de produção.
        >
        > O Agente de Resolução de Produção melhora o desempenho (como o número de ordens e linhas de ordem que podem ser processadas em uma execução) e da convergência de resultados (já que um lote de ordens pode não produzir os melhores resultados em alguns cenários). Algumas regras, como a regra de **Ordens parciais** e a de **Número máximo de localizações**, exigem o Agente de Resolução de Produção.

6. Volte para **Retail e Commerce \> Gerenciamento de ordem distribuído \> Configuração \> Parâmetros de DOM**.
7. Na guia **Sequências numéricas**, atribua as sequências numéricas necessárias às várias entidades de DOM.

    > [!NOTE]
    > Para que as sequências numéricas possam ser atribuídas às entidades, elas devem ser definidas na página **Sequências numéricas** (**Administração da organização \> Sequências numéricas \> Sequências numéricas**).

8. O recurso DOM tem suporte para a definição de vários tipos de regras do DOM, e as organizações podem configurar várias regras, dependendo de suas necessidades empresariais. As regras do DOM podem ser definidas para um grupo de locais ou para locais individuais, e para uma categoria de produtos, um produto ou uma grade específicos. Para criar o agrupamento de locais que devem ser usados para as regras do DOM, siga estas etapas:

    1. Vá para **Retail e Commerce \> Configuração de canal \> Grupos de atendimento**.
    2. Selecione **Novo** e digite um nome e uma descrição para o novo grupo.
    3. Selecione **Salvar**.
    4. Selecione **Adicionar linha** para adicionar um único local ao grupo. Como alternativa, selecione **Adicionar linhas** para adicionar vários locais.

    > [!NOTE]
    > Na versão 10.0.12 e posterior do Commerce, a opção **Capacidade para especificar locais como "Remessa" ou "Retirada" no Grupo de processamento** deve estar habilitada na espaço de trabalho **Gerenciamento de Recursos**.
    >
    > Este recurso adiciona novas configurações na página **Grupo de processamento** para que você possa definir se o depósito pode ser usado para remessa ou se a combinação de depósito/armazenamento pode ser usada para remessa, retirada ou as duas opções. 
    >
    > Se você habilitar o recurso, as opções disponíveis para a seleção de local quando você criar ordens de remessa ou retiradas no PDV serão atualizadas.
    >
    > A habilitação do recurso também resulta em páginas atualizadas no PDV quando as operações "remeter tudo" ou "remeter selecionado" são selecionadas.

9. Para definir regras, vá para **Retail e Commerce \> Gerenciamento de ordem distribuído \> Configurar \> Gerenciar regras**. Há suporte para as seguintes regras do DOM atualmente:

    - **Regra de estoque mínimo** – Este tipo de regra permite que as organizações restrinjam uma quantidade específica de um produto para fins diferentes do atendimento da ordem. Por exemplo, as organizações podem não querer que o DOM considere todo o estoque disponível em uma loja para o atendimento de ordens. Em vez disso, talvez queiram reservar parte do estoque para os clientes que visitam as lojas. Quando esse tipo de regra for usado, você poderá definir um estoque mínimo para manter para uma categoria de produtos, um produto individual ou uma grade de produto por local ou grupo de locais. Você também pode definir o estoque mínimo usando uma hierarquia de categoria adicional. Se um produto se enquadrar em várias categorias, uma categoria adicional será considerada de maior importância em todas as regras nas quais você pode usar categorias.
    - **Regra de prioridade de local de processamento** – Este tipo de regra permite que as organizações definam uma hierarquia de locais para estabelecer a prioridade que o mecanismo de DOM considera quando tenta identificar locais de processamento para produtos específicos. O intervalo de validade das prioridades vai de 1 a 10, onde 1 é a maior prioridade e 10 a menor. Os locais com as prioridades mais altas são considerados antes dos locais com as prioridades mais baixas. Se a regra for definida como uma regra de restrição rígida, as ordens serão agenciadas somente para locais para os quais as prioridades estão definidas. O DOM concede preferência às ordens de remessa de um único local. Portanto, se uma ordem inteira e suas linhas não estiverem disponíveis em um local com prioridade 1, o DOM tentará processá-la de um local com prioridade 2.
    - **Regra de ordens parciais** – Na versão de 10.0.5 do Retail, o parâmetro **Processar a ordem somente de um local** foi alterado para **Máximo de locais de processamento**. O parâmetro antigo permitiu que os usuários configurassem se as ordens poderiam ser executadas somente de um local ou do máximo de locais possível. O novo parâmetro permite que os usuários especifiquem se o processamento pode ser de um conjunto definitivo de locais (até cinco) ou do maior número de locais possível. Para todas as opções, exceto o processamento de um local, o DOM dividirá a linha, porque o processamento da ordem ocorre por linha. Esta regra funciona apenas com o Agente de Resolução de Produção.
    - **Regra de local de processamento offline** – Esta regra permite que as organizações especifiquem um local ou grupo de locais como offline ou indisponível para o DOM, para que as ordens não possam ser atribuídas a esses locais para processamento.
    - **Regra de máximo de rejeições** – Esta regra permite que as organizações definam um limite para rejeições. Quando o limite é atingido, o processador do DOM marca uma ordem ou uma linha da ordem como uma exceção, e a exclui do processamento futuro. Para garantir o desempenho, o DOM não analisa o histórico de todas as rejeições. 

        Depois que as linhas da ordem são atribuídas a um local, o local pode rejeitar uma linha de ordem atribuída, pois pode não conseguir atender essa linha por algumas razões. As linhas rejeitadas são marcadas como uma exceção e colocadas novamente no pool para processamento na próxima execução. Durante a próxima execução, o DOM tentará atribuir a linha rejeitada a um local diferente. O novo local também pode rejeitar a linha da ordem atribuída. Esse ciclo de atribuição e rejeição pode ocorrer várias vezes. Quando a contagem de rejeição bater o limite definido, o DOM marcará a linha da ordem como uma exceção permanente e não escolherá a linha para atribuição novamente. O DOM só vai considerar novamente a linha da ordem para reatribuição se um usuário redefinir manualmente o status da linha da ordem.

    - **Regra da distância máxima** – Esta regra permite às organizações definir a distância máxima que um local ou um grupo de locais pode estar para que a ordem seja atendida. Se forem definidas para um local regras de distância máxima sobrepostas, o DOM aplicará a menor distância máxima definida para esse local.
    - **Regra de máximo de ordens** – Esta regra permite que as organizações definam o número máximo de ordens que um local ou um grupo de locais pode processar. Durante o processo de otimização, o sistema levará em consideração as ordens que não foram enviadas desses locais. Essa verificação é feita entre os perfis. Portanto, se os números máximos de ordens sobrepostas forem definidos pelos perfis para a mesma localização, o sistema considerará o número máximo de ordens definido em todos os perfis. 

    Veja alguns atributos comuns que podem ser definidos para todos os tipos de regras acima:

    - **Data inicial** e **Data final** – Você pode usar esses campos para tornar cada data de regra mais eficiente.
    - **Desabilitado** – Apenas as regras com um valor **Não** para este campo são consideradas em uma execução do DOM.
    - **Restrição rígida** – Uma regra pode ser definida como uma restrição rígida ou uma restrição não rígida. Todas as execuções do DOM passam por duas iterações. Na primeira iteração, todas as regras são tratadas como uma regra de restrição rígida, independentemente da configuração deste campo. Ou seja, todas as regras se aplicam. A única exceção é a regra **Prioridade do local**. Na segunda iteração, as regras que não foram definidas como regras de restrição rígidas serão removidas, e a ordem ou linhas da ordem que não foram atribuídas a locais quando todas as regras foram aplicadas serão atribuídas a locais.

10. Os perfis de atendimento são usados para agrupar um conjunto de regras, entidades legais, origens de ordem de venda e modos de entrega. Todas as execuções do DOM são para um perfil de atendimento específico. Assim, as organizações podem definir e executar um conjunto de regras para um conjunto de entidades legais, em ordens que têm origens de ordem de venda e modos de entrega específicos. Portanto, se diferentes conjuntos de regras devem ser executados para diferentes conjuntos de origens de ordem de venda ou modos de entrega, os perfis de atendimento podem ser definidos de acordo. Para configurar perfis de atendimento, siga estas etapas:  

    1. Vá para **Retail e Commerce \> Gerenciamento de ordem distribuído \> Configuração \> Perfil de atendimento**.
    2. Selecione **Novo**.
    3. Insira os valores nos campos **Perfil** e **Descrição**.
    4. Defina a opção **Aplicar resultado automaticamente**. Se você definir essa opção como **Sim**, os resultados da execução do DOM para o perfil serão aplicados automaticamente nas linhas da ordem de venda. Se definir como **Não**, os resultados só poderão ser vistos no plano de atendimento. Não serão aplicados nas linhas da ordem de venda.
    5. Se quiser que o perfil DOM seja executado para ordens que tenham cada origem de ordem de venda, incluindo ordens em que a origem da ordem de venda seja indefinida, defina a opção **Processar ordens com origem de vendas vazia** como **Sim**. Para executar o perfil para apenas algumas origens de ordem de venda, você pode defini-las na página **Origens de venda**, conforme explicado posteriormente.

        > [!NOTE]
        > Na versão de lançamento 10.0.12 e posterior do Commerce, o recurso **Capacidade de atribuir Grupo de processamento a um Perfil de processamento** deve ser habilitado na espaço de trabalho **Gerenciamento de recursos**. Esse recurso permite especificar uma lista de depósitos que o DOM deve considerar quando a otimização é executada com um perfil de processamento. Se essa lista de depósitos não for especificada, o DOM verificará todos os depósitos nas entidades legais definidas no perfil.
        >
        > Este recurso adiciona uma nova configuração na página **Perfil de processamento** que pode ser associada a um único Grupo de processamento. 
        >
        > Se você selecionar o Grupo de atendimento, as regras DOM desse Perfil de atendimento serão executadas com eficiência nos depósitos de "remessa" incluídos no Grupo de atendimento. 
        > 
        > Para usar esse recurso com eficiência, verifique se há um Grupo de atendimento que contenha todos os depósitos de remessa e associe o Grupo de atendimento ao Perfil de atendimento.

    6. Na FastTab **Entidades legais**, selecione **Adicionar** e depois selecione uma entidade legal.
    7. Na FastTab **Regras**, selecione **Adicionar** e depois selecione a regra para vincular ao perfil.
    8. Repita as duas etapas anteriores até que todas as regras necessárias sejam associadas ao perfil.
    9. Selecione **Salvar**.
    10. No Painel de Ações, na guia **Configuração**, selecione **Modos de entrega**.
    11. Na página **Modos de entrega**, selecione **Novo**.
    12. No campo **Empresa**, selecione a entidade legal. A lista de empresas está limitada às entidades legais que você adicionou anteriormente.
    13. No campo **Modo de entrega**, selecione o modo de entrega para associar a este perfil. Um modo de entrega não pode ser associado a vários perfis ativos.
    14. Repita as duas etapas anteriores até que todos os modos de entrega necessários sejam associados ao perfil.
    15. Feche a página **Modos de entrega**.
    16. No Painel de Ações, na guia **Configuração**, selecione **Origens de ordem de venda**.
    17. Na página **Origens de venda** , selecione **Novo**.
    18. No campo **Empresa**, selecione a entidade legal. A lista de empresas está limitada às entidades legais que você adicionou anteriormente.
    19. No campo **Origem de venda**, selecione a origem de venda para associar a este perfil. Uma origem de venda não pode ser associada a vários perfis ativos.
    20. Repita as duas etapas anteriores até que todas as origens de venda necessárias sejam associadas ao perfil.
    21. Feche a página **Origens de vendas**.
    22. Defina a opção **Habilitar o perfil** como **Sim**. Se houver algum erro na instalação, você receberá uma mensagem de aviso.

## <a name="dom-processing"></a>DOM em processamento

O DOM só será executado em um trabalho em lotes. Para configurar o trabalho em lotes para execuções do DOM, siga as etapas a seguir.

1. Vá para **Retail e Commerce \> Gerenciamento de ordem distribuído \> Processamento em lotes \> Configuração de trabalhos do processador de DOM**.
1. Na FastTab **Parâmetros**, no campo **Perfil de atendimento**, selecione um perfil para o qual o DOM tem de ser executado.
1. Na FastTab **Executar em segundo plano**, no campo **Grupo de lotes**, selecione um grupo de lotes configurado.
1. No campo **Descrição da tarefa**, insira um nome para o trabalho em lotes.
1. Selecione **Recorrência**, e defina a recorrência do trabalho em lotes.
1. Selecione **OK**.

No momento do processamento, o DOM considerará a ordem e as linhas da ordem conforme descrito aqui:

- As linhas da ordem que atenderem aos critérios de origens de ordem de venda, modos de entrega e entidade legal conforme definidos no perfil do DOM e que também atenderem a algum destes critérios:

    - Sejam criadas em canais de comércio.
    - Nunca tenham sido agenciadas pelo DOM.
    - Foram agenciadas pelo DOM antes, mas estão marcadas como exceções e estão abaixo do limite máximo de tentativas.
    - O modo de entrega não é retirada nem entrega eletrônica.
    - Não estejam marcadas para entrega.
    - Não sejam excluídas manualmente.

- Ordens que não estejam em espera

Depois que as regras, as restrições de estoque e a otimização são aplicadas, o DOM escolhe o local mais próximo do endereço de entrega do cliente. O DOM converte os endereços do tipo **Entrega** para os valores de latitude e longitude. Em seguida, converte o endereço de entrega na ordem de venda em valores de latitude e longitude e atualiza os valores de latitude e longitude do endereço para uso futuro. O DOM depende do Bing Mapas para determinar os valores precisos de latitude e longitude com base nas informações de endereço, cidade e CEP.

O DOM usa a interface de programação de aplicativo do Bing Mapas para calcular a distância aérea ou rodoviária, dependendo das configurações. Em seguida, ele usa essas informações para determinar o custo de envio. O modelo de otimização prioriza o processamento de uma ordem completa de um local. Mesmo se parte de uma ordem estiver disponível na mesma cidade ou CEP, o modelo foi otimizado para reduzir o número de remessas. 

O DOM pesquisa o estoque disponível por meio da exibição do estoque disponível nas entidades do depósito V2. Durante cada execução em lote, o DOM quebra as ordens em lotes, dependendo do parâmetro de **Processador de DOM** das tarefas definidas no perfil. Esse parâmetro tem o valor padrão de **2000**. Por exemplo, se 10 mil linhas da ordem estiverem sendo otimizadas em uma execução, e o parâmetro **Processador DOM** for definido como o valor padrão **2000**, o DOM criará cinco lotes que serão processados simultaneamente. Depois, os planos de processamento serão obtidos do otimizador e aplicados na linha. Se a linha da ordem tiver de ser dividida entre dois locais, o DOM garantirá que os preços e os impostos se espalhem adequadamente pelas linhas.

![Critérios da ordem de venda.](./media/ordercriteria.png "Critérios da ordem de venda")

## <a name="results-of-dom-runs"></a>Resultados de execuções de DOM

Se o perfil de processamento for definido como **Aplicação automática**, os resultados da execução serão aplicados automaticamente nas linhas da ordem de venda, e o plano de processamento poderá ser visto separadamente. Entretanto, se o perfil de atendimento não estiver definido como **Aplicação automática**, os resultados da execução poderão ser vistos apenas na exibição do plano de atendimento. 

Para exibir todos os planos de atendimento gerados, siga as etapas a seguir.

1. Vá para **Retail e Commerce \> Gerenciamento de ordem distribuído \> Gerenciamento de ordem distribuído**.
2. No espaço de trabalho **Gerenciamento de ordem distribuído**, selecione o bloco **Planos de atendimento**.
3. Selecione a ID do plano de atendimento de ordem relevante para exibir o plano de atendimento.

    A seção de detalhes da ordem do plano de atendimento mostra as linhas da ordem de venda original que faziam parte da execução. Além dos campos padrão de linha da ordem de venda, a seção de detalhes da ordem também inclui os três campos relacionados ao DOM:

    - **Tipo de atendimento** – Este campo indica se a linha de ordem de venda foi totalmente agenciada, parcialmente agenciada ou nem um pouco agenciada para o local.
    - **Dividir** – Este campo indica se uma linha de ordem de venda foi dividida e agenciada para diferentes locais.
    - **Número de locais de atendimento** – Este campo indica quantas linhas de atendimento foram criadas para uma linha da ordem de venda (com base no número de locais para os quais a linha da ordem de venda original foi agenciada).

    A seção de detalhes de atendimento da ordem mostra a atribuição de linhas da ordem de venda original para locais diferentes, juntamente com as respectivas quantidades.

## <a name="order-line-actions-and-statuses"></a>Ações e status da linha da ordem

A seguir, a descrição das configurações na linha da ordem. Para abrir a linha de ordem, vá para **Retail e Commerce \> Clientes \> Todas as ordens de venda**.

- Se você definir a opção **Excluir do processamento do DOM** na guia **Geral** da linha da ordem de venda como **Sim**, a ordem ou a linha da ordem será excluída do processamento do DOM.
- O campo **Status do DOM** na guia **Geral** da linha da ordem de venda pode ser definido como um destes valores:

    - **Nenhuma** – A linha da ordem nunca foi agenciada.
    - **Concluída** – A linha da ordem foi agenciada com êxito e atribuída a um local.
    - **Exceção** – A linha da ordem foi agenciada mas não pode ser atribuída a um local. As exceções têm vários subtipos que podem ser vistos no espaço de trabalho do DOM:

        - **Nenhuma quantidade disponível** – Não há estoque disponível para atribuir à ordem em nenhum local.
        - **Máximo de rejeições** – A linha da ordem alcançou o limite máximo de rejeições.
        - **Conflito de modificação de dados** – A linha de ordem de venda foi alterada desde que a ordem foi agenciada. Portanto, o plano de atendimento não pode ser aplicado à ordem.
        - **Exceção específica de linha de ordem** – Há várias exceções na linha de ordem.

- Durante a entrada de ordem de venda, o DOM pode ser executado em um modo interativo. Quando você inserir uma linha de ordem, depois de especificar o produto e a quantidade, poderá selecionar **Atualizar linha** e, em **DOM**, selecionar **Sugerir local de atendimento**. Você verá uma lista de locais baseada em regras do DOM que podem atender a quantidade na linha da ordem. Esta lista é classificada por distância. Selecione um local para definir o site e o depósito relevantes na linha de ordem de venda. Para que este recurso funcione, deve haver um perfil de atendimento existente ativo que corresponda à origem de venda e ao modo de entrega na linha de venda.
- Para exibir os logs de execução do DOM para uma linha da ordem de venda, selecione **Linha da ordem de venda** e, em seguida, em **DOM**, selecione **Exibir Logs do DOM**. Os logs do DOM mostram todos os eventos e logs que foram gerados pela execução do DOM. Os logs podem ajudar você a entender como um local específico foi atribuído à linha da ordem, e quais regras e restrições foram consideradas como parte da atribuição. Na guia **Gerenciar**, os logs do DOM também estão disponíveis no nível do cabeçalho de ordem de venda.

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>Execute um trabalho de limpeza de planos de atendimento do DOM

Conforme o processamento do DOM for executado, os planos de atendimento serão criados. Com o tempo, o sistema manterá vários planos de atendimento. Para gerenciar o número de planos de atendimento que o sistema mantém, você pode configurar um trabalho em lotes que exclui antigos planos de atendimento, com base no valor de **Período de retenção em dias**.

1. Vá para **Retail e Commerce \> Gerenciamento de ordem distribuído \> Processamento em lotes \> Configuração de trabalhos de exclusão de dados de atendimento do DOM**. 
1. Selecione um grupo de lotes configurado no campo **Grupo de lotes**.
1. Selecione **Recorrência**, e defina a recorrência do trabalho em lotes.
1. Selecione **OK**.

## <a name="more-information"></a>Mais informações

Veja aqui alguns aspectos a serem considerados ao usar o recurso do DOM:

- Atualmente, o DOM examina apenas ordens criadas em canais de comércio. As ordens de venda serão identificadas como ordens de venda quando a opção **Venda do Commerce** for definida como **Sim**.
- A Microsoft não testou o DOM com recursos avançados de gerenciamento de depósito. Assim, clientes e parceiros devem ser cuidadosos para determinar se o DOM é compatível com os recursos e os processos avançados de gerenciamento de depósito que são relevantes para eles. O armazenamento avançado permite dimensões configuráveis, como o status do estoque, que não fornecem uma informação precisa do estoque disponível. O DOM fornece um método extensível para definir o estoque disponível para implementações que usam o armazenamento avançado. Ele pode ser usado para trabalhar com valores personalizados de status de estoque e outras dimensões.

    A extensibilidade no DOM é limitada porque ocorre uma otimização no modelo de MIP pré-criado que considera a otimização e suas restrições. Vários pontos extensíveis já estão disponíveis para definir a otimização de estoque e pós-processamento. Os perfis DOM podem diferir entre o modo de entrega e a origem das vendas. A origem da ordem de venda pode ser definida durante a inclusão da ordem, e diferentes estratégias de otimização podem ser usadas com base nesses valores. O DOM também oferece suporte à criação de trabalhos em lotes personalizados que podem levar a tarefa de processador DOM como entrada e habilitar o perfil a ser passado como um parâmetro. Portanto, uma otimização pode ser executada depois de outra para oferecer suporte a diferentes cenários comerciais.

- O DOM está disponível apenas na versão da nuvem do Commerce. Não é compatível com implantações locais.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
