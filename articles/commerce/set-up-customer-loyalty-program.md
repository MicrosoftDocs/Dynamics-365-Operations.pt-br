---
title: Visão geral de fidelidade
description: Este tópico descreve os recursos de fidelidade no Dynamics 365 Commerce e as etapas de instalação correspondentes para oferecer ao fornecedor uma introdução aos programas programas de fidelidade.
author: scott-tucker
manager: AnnBe
ms.date: 07/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailLoyaltyPrograms, RetailPriceDiscGroup
audience: Application User
ms.reviewer: josaw
ms.custom: 16201
ms.assetid: f79559d2-bc2d-4f0b-a938-e7a61524ed80
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 085071cb7aa314dd8a8c19b8ef2ac926a6ab4103
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985802"
---
# <a name="loyalty-overview"></a>Visão geral de fidelidade

[!include [banner](includes/banner.md)]

Os programas de fidelidade podem ajudar a aumentar a fidelidade do cliente ao recompensarem os clientes por suas interações com a marca do varejista. No Dynamics 365 Commerce, você pode configurar programas de fidelidade simples ou complexos que se apliquem a suas entidades legais em qualquer canal de comércio. Este tópico descreve os recursos de fidelidade no Commerce e as etapas de instalação correspondentes para oferecer ao fornecedor uma introdução aos programas de fidelidade.

Você pode configurar o programa de fidelidade de modo que ele tenha as opções a seguir.

- Configure vários tipos de recompensas que você oferece em seus programas de fidelidade e controle a participação em seus programas de fidelidade.
- Configure programas de fidelidade que representam os diferentes incentivos de recompensa oferecidos por você. Você pode incluir camadas do programa de fidelidade para oferecer maiores incentivos e recompensas aos clientes que comprem com mais frequência ou gastem mais dinheiro em suas lojas.
- Defina regras de ganhos para identificar as atividades que um cliente deverá concluir para conquistar recompensas. Você também pode definir regras de redenção para identificar quando e como um cliente poderá resgatar recompensas.
- Emita cartões de fidelidade de qualquer canal que participe de seus programas de fidelidade e vincule cartões de fidelidade a um ou mais programas de fidelidade em que o cliente possa participar. Você também pode vincular um registro de cliente a um cartão de fidelidade, para que o cliente possa agrupar pontos de fidelidade de vários cartões e resgatá-los.
- Ajuste manualmente cartões-fidelidade ou transfira o saldo de recompensas de fidelidade de um cartão para outro para acomodar ou recompensar um cliente.

## <a name="setting-up-loyalty-programs"></a>Configurando programas de fidelidade

Você deve configurar vários componentes para habilitar o recurso de fidelidade no Commerce. O diagrama a seguir ilustra os componentes do programa de fidelidade e como eles se relacionam uns com os outros.

![Fluxo do processo de configuração do programa de fidelidade](./media/loyaltyprocess.gif "Componentes de fidelidade e como eles estão relacionados")

## <a name="loyalty-components"></a>Componentes do programa de fidelidade

A tabela a seguir descreve cada componente e o local onde ele será usado na configuração do programa de fidelidade.

| Componente                                        | descrição | Onde é usado |
|--------------------------------------------------|-------------|-----------------|
| Configurar descontos (pré-requisito)                  | Configurar descontos que você oferece ao seus clientes do programa de fidelidade. Por exemplo, você pode oferecer 5% de desconto em todos os produtos de equipamento. | Os descontos devem ser adicionados a grupos de preços antes de serem incluídos em um programa de fidelidade. Os grupos de preços são atribuídos a programas de fidelidade e a camadas do programa de fidelidade. |
| Configurar grupos de preços (pré-requisito)               | Grupos de preços são usados para criar e gerenciar preços e descontos para produtos. Configure os grupos de preços que incluem os descontos que se aplicam aos seus programas de fidelidade. | Os grupos de preços são atribuídos a seus programas de fidelidade e às camadas do programa de fidelidade. |
| Configurar canais (pré-requisito)                   | Os canais de comércio são as lojas que participam de seus programas de fidelidade, como uma loja tradicional, uma loja online ou um call center. Você deve configurar os canais para poder atribuir programas de fidelidade a eles. | Você atribuirá canais a um programa de fidelidade caso o canal esteja participando dele. |
| Configurar o método de pagamento de fidelidade (pré-requisito) | Para garantir que os pontos de fidelidade sejam resgatados em qualquer canal, como lojas tradicionais, lojas online ou call centers, é necessário configurar o intervalo binário para cartões-fidelidade na página **Números de cartão**. | Configure um método de pagamento do tipo de programa de fidelidade e então atribua o método de pagamento de programa de fidelidade aos canais que estejam participando do programa de fidelidade. |
| Configurar intervalos de datas                            | Os intervalos de datas fornecem uma maneira flexível de definir o período aplicado a camadas do programa de fidelidade. Use os intervalos de datas para especificar por quanto tempo um cliente poderá ficar em uma camada ou quanto tempo o cliente tem para concluir uma atividade para se qualificar para uma camada. | Os intervalos de datas só se aplicarão se você usar camadas em seus programas de fidelidade. Selecione o intervalo de datas que se aplique a camadas do programa e também os intervalos de datas que se apliquem a regras de camada do programa. |
| Configurar pontos de recompensa                             | Os pontos de recompensa são os tipos de recompensa que você oferece aos seus clientes. Os pontos de recompensa podem ser resgatáveis ou não resgatáveis. Os pontos de recompensa resgatáveis podem ser trocados por produtos. Os pontos de recompensa não resgatáveis são usados para fins de rastreamento ou para fazer um cliente avançar para a próxima camada de um programa de fidelidade. | Os pontos de recompensa são mencionados na camada de regra e são usados para qualificar um cliente para uma camada específica. Os pontos de recompensa também são mencionados em esquemas de fidelidade em regras de ganhos e de resgate. Em regras de ganhos, você especifica as recompensas que um cliente poderá ganhar para uma atividade específica. Em regras de resgate, você especifica a recompensa que o cliente pode resgatar. |
| Configurar programas de fidelidade                          | Os programas de fidelidade são a entidade principal de fidelidade que você oferece. Cada programa de fidelidade também pode ter camadas de fidelidade atribuídas a ele. Os grupos de descontos e preços são atribuídos aos programas de fidelidade no nível de programa ou de camada. | Você cria esquemas de fidelidade para seus programas de fidelidade. Você atribui cartões-fidelidade a seus programas de fidelidade, e podem ser atribuídos cartões-fidelidade a um cliente. Os canais participam dos programas de fidelidade atribuídos aos esquemas de fidelidade. Qualquer cliente com um cartão-fidelidade pode participar de programas de fidelidade atribuídos ao cartão. |
| Configurar camadas de programa de fidelidade e regras de camada              | As camadas de fidelidade são níveis opcionais que você pode definir para seus programas de fidelidade. Você pode configurar descontos base e recompensas para todos os clientes que participam do programa de fidelidade, e pode configurar descontos e recompensas adicionais para clientes que atinjam os níveis diferentes no programa. Para cada camada de fidelidade definida, será possível configurar as regras que qualificam um cliente para essa camada. Também é possível definir por quanto tempo os clientes permanecerão naquela camada depois de atingi-la. | As camadas de fidelidade e as regras de camada de fidelidade são definidas nos programas de fidelidade. Se você não definir camadas de fidelidade, todos os clientes que participarem do programa de fidelidade se qualificarão para os descontos atribuídos no grupo de preços do programa de fidelidade. Se você definir camadas de fidelidade, poderá configurar regras de ganhos e regras de resgate para as camadas de fidelidade no esquema de fidelidade. |
| Configurar esquemas de fidelidade                           | Esquemas de fidelidade especificam as regras de ganhos e as regras de resgate que se aplicam a um programa de fidelidade selecionado. Atribua os canais a um esquema de fidelidade para identificar quais programas de fidelidade, regras de ganhos e regras de resgate se aplicam a uma loja. | Um esquema de fidelidade é atribuído a um programa de fidelidade e a canais. Você pode atribuir diversos esquemas de fidelidade ao mesmo programa de fidelidade, e pode atribuir diversos esquemas de fidelidade a vários canais. |
| Configurar cartões-fidelidade                             | Um cartão-fidelidade qualifica o titular do cartão a participar dos programas de fidelidade atribuídos ao cartão. Os cartões-fidelidade podem ser emitidos de forma anônima ou podem ser atribuídos a um cliente específico. Você pode exibir as transações de fidelidade para um cartão específico, e pode exibir um resumo dos pontos de fidelidade que foram acumulados no cartão. Você pode emitir cartões-fidelidade de qualquer canal. Você também pode ajustar manualmente um cartão-fidelidade para atualizar o cliente para uma camada diferente, adicionar pontos de fidelidade ou transferir o saldo dos pontos de fidelidade de um cartão para outro. | Você atribui programas de fidelidade a um cartão-fidelidade. |

## <a name="loyalty-processes"></a>Processos de fidelidade

A tabela a seguir descreve os processos que devem ser executados para enviar as configurações e os dados do programa de fidelidade às lojas, e para recuperar as transações de fidelidade de suas lojas.

| Nome do processo                         | Descrição | Nome da página |
|--------------------------------------|-------------|-----------|
| 1050 (informações de fidelidade)           | Execute este processo para enviar os dados do programa de fidelidade do Commerce para as lojas. É recomendável agendar este processo para ser executado frequentemente, de modo que os dados do programa de fidelidade sejam transmitidos a todas as lojas. | Agenda de distribuição |
| Processar esquemas de fidelidade              | Execute este processo para associar os esquemas de fidelidade aos canais aos quais o esquema de fidelidade foi atribuído. Esse processo pode ser agendado para execução como um processo em lote. Você deve executar esse processo se alterar dados de configuração do programa de fidelidade, como esquemas de fidelidade, programas de fidelidade ou pontos de recompensa do programa de fidelidade. | Processar esquemas de fidelidade |
| Lançar os pontos de fidelidade ganhos em lotes | Execute este processo para atualizar cartões-fidelidade, de forma que eles incluam transações processadas offline. Esse processo será aplicável somente se a caixa de seleção **Lançar pontos ganhos em lotes** for selecionada na página **Parâmetros compartilhados do Commerce**, de tal modo que as recompensas possam ser obtidas offline. | Lançar os pontos de fidelidade ganhos em lotes |
| Atualizar camadas de cartão-fidelidade            | Execute este processo para avaliar a atividade de ganhos do cliente em relação às regras de camada para um programa de fidelidade e para atualizar o status de camada do cliente. Este processo só será necessário se você alterar as regras da camada em programas de fidelidade e quiser que as regras atualizadas sejam aplicadas retroativamente aos cartões-fidelidade já emitidos. Este processo pode ser agendado como um processo em lote ou para cartões individuais. | Atualizar camadas de cartão-fidelidade |

## <a name="loyalty-capabilities"></a>Recursos de fidelidade

- Usando os grupos de preços associados ao programa de fidelidade e às camadas de fidelidade, os varejistas podem criar facilmente preços e descontos especiais para os membros de fidelidade.

- Como parte de um esquema de fidelidade, os varejistas podem criar regras diferentes de ganhos e de resgate por camadas para diferenciar as recompensas para clientes em camadas diferentes. Os varejistas também podem incluir “afiliações” como parte de regras de ganhos e de resgate de forma que determinado grupo de clientes possa fazer parte de camadas existentes, mas ser recompensado de formas diferentes. Isso evita a necessidade de criar camadas adicionais.
    
    > [!NOTE]
    > As regras de ganhos em um esquema de fidelidade são adicionais. Por exemplo, se você criar uma regra para recompensar um membro da camada ouro com 10 pontos para cada dólar americano e também criar uma regra para recompensar um cliente com afiliação de "veterano" com 5 pontos para cada dólar americano, então um veterano que também for um membro da camada ouro ganhará 15 pontos para dólar americano, já que o cliente se qualifica para as duas linhas. Entretanto, se o cliente veterano não for membro da camada ouro, então ganhará 5 pontos para cada dólar. Para refletir as alterações nos canais, execute os trabalhos **Processar esquemas de fidelidade** e **1050** (informações de fidelidade).
    
    ![Ganhos baseados em afiliação](./media/Affiliation-based-earning.png "Ganhos baseados em afiliação")

- Com frequência, os varejistas têm preços especiais para um determinado grupo de clientes aos quais não desejam aplicar programas de fidelidade. Por exemplo, os atacadistas ou os funcionários que obtêm preços especiais e nenhum ponto de fidelidade. Geralmente, as "afiliações" são usadas para conceder o preço especial a esses grupos de clientes. Para restringir determinados grupos de clientes de clientes dos pontos de fidelidade de ganho, o varejista pode especificar uma ou várias afiliações na seção **Afiliações excluídas** do esquema de fidelidade. Dessa forma, quando o clientes pertencentes às afiliações excluídas forem membros existentes do programa de fidelidade, eles não poderão ganhar pontos de fidelidade por suas compras. Para refletir as alterações nos canais, execute os trabalhos **Processar esquemas de fidelidade** e **1050** (informações de fidelidade).

    ![Afiliações excluídas](./media/Excluded-affiliations.png "Excluir afiliações do ganho de pontos de fidelidade")
    
- O Ponto de Venda permite que a flexibilidade dos varejistas use os cartões-fidelidade físicos ou gere automaticamente um número de cartão-fidelidade exclusivo. Para permitir a geração automática cartões-fidelidade em lojas, ative **Gerenciar número de cartão-fidelidade** no perfil de funcionalidade associado à loja. Para os canais online, os varejistas podem usar a API IssueLoyaltyCard para emitir cartões-fidelidade para os clientes. Os varejistas também podem fornecer um número de cartão-fidelidade a essa API, que será usado para gerar o cartão-fidelidade, ou o sistema usará a sequência numérica dos cartões-fidelidade definida no Commerce. Entretanto, se a sequência numérica não estiver presente, e se o varejista não fornecer um número de cartão-fidelidade ao chamar a API, um erro será exibido.

    ![Gerar cartão de fidelidade](./media/Generate-loyalty-card.png "Gerar número do cartão-fidelidade automaticamente")

- Os pontos de fidelidade obtidos e resgatados agora podem ser salvos para cada transação e ordens de venda em relação à linha de vendas, para que o mesmo valor possa ser reembolsado ou devolvido no caso de devoluções completas ou parciais. Além disso, ter visibilidade para pontos no nível da linha de vendas oferece o recurso de usuários de call center responderem a perguntas de clientes sobre quantos pontos foram ganhos ou resgatados para cada linha. Antes dessa alteração, os pontos de recompensa eram sempre recalculados durante as devoluções, o que resultava em um valor diferente do original caso as regras de ganhos ou de resgate fossem alteradas e se os usuários do call center não tivessem a visibilidade da divisão de pontos. Os pontos podem ser exibidos no formulário **Transações de cartão** para cada cartão-fidelidade. Para habilitar esse recurso, ative a configuração **Lançar pontos de fidelidade por linha de venda** na guia **Parâmetros compartilhados do Commerce** \> **Geral**.

    > [!NOTE]
    > Recomendamos enfaticamente ativar esse recurso para garantir, em caso de devoluções, que o valor correto de pontos possa ser reembolsado ou retirado do cliente.

- Agora, os varejistas podem definir o período de carência para cada ponto de recompensa. Uma configuração de período de carência definirá a duração da data de ganho, após a qual os pontos de recompensa seriam disponibilizados aos clientes. Os pontos sem benefício proporcional diferido podem ser exibidos na coluna **Pontos sem benefício proporcional diferido** na página **Cartões-fidelidade**. Quando os clientes retornam alguns itens para os quais os pontos de fidelidade foram obtidos, por padrão, o sistema irá deduzir os pontos não mais colados primeiro e, depois, deduzir qualquer saldo dos pontos disponíveis. No entanto, você pode configurar para deduzir somente os pontos disponíveis em vez de deduzir de pontos inferidos.

Adicionalmente, os varejistas podem definir o limite máximo de pontos de recompensa de fidelidade por cartão-fidelidade. Esse campo pode ser usado para reduzir o impacto de fraude de fidelidade. Quando o máximo de pontos de recompensa for atingido, o usuário não poderá ganhar mais pontos. O varejista pode decidir bloquear tais cartões até a conclusão da investigação de uma potencial fraude. Se o varejista determinar a fraude, ele poderá bloquear o cartão-fidelidade do cliente e marcar o cliente como bloqueado. Para fazer isso, defina a propriedade **Bloquear cliente para registro de fidelidade** como **Sim** em **Todos os clientes** na Guia Rápida **Commerce**. Os clientes bloqueados não poderão receber cartões-fidelidade em nenhum canal.

   ![Benefício e pontos máximos de premiação](./media/Vesting-and-maximum-reward-points.png "Definir benefício e pontos máximos de premiação")

- As afiliações são usadas para conceder preços e descontos especiais, mas há algumas afiliações que os varejistas não querem que os clientes vejam. Por exemplo, uma afiliação intitulada "Cliente com altos gastos" pode não ser bem recebida por alguns clientes. Além disso, existem algumas afiliações que não devem ser gerenciadas na loja, por exemplo, os funcionários, porque você não deseja que os caixas decidam quem é funcionário e assim concedam descontos para funcionários. Os varejistas agora podem selecionar as afiliações que devem ser ocultadas nos canais. As afiliações marcadas como **Ocultar nos canais** não podem ser exibidas, adicionadas ou removidas no PDV. Entretanto, os preços e os descontos associados à afiliação ainda serão aplicados aos produtos.

    ![Ocultar afiliações](./media/Hide-affiliations.png "Ocultar afiliações nos canais")
    
- Os usuários de call center agora podem procurar com mais facilidade um cliente usando as informações do cartão-fidelidade e navegar até as páginas do cartão-fidelidade e de transação de cartão-fidelidade do cliente desde a página **Atendimento ao cliente**.

    ![Serviço de atendimento ao consumidor](./media/Customer-service.png "Localizar informações de fidelidade para o cliente")
    
- Se um cartão-fidelidade tiver sido comprometido, será necessário gerar um cartão de substituição e transferir os pontos existentes para o novo cartão. O fluxo do cartão de substituição foi simplificado nesta versão. Adicionalmente, os clientes podem presentear os amigos e familiares com alguns ou todos os pontos de fidelidade. Quando os pontos forem transferidos, as entradas de ajuste de pontos serão criadas para cada cartão-fidelidade. A funcionalidade de cartão de substituição e transferir saldo pode ser acessada na página **Cartões-fidelidade**.

    ![Substituir e transferir pontos](./media/Replace-and-transfer-points.png "Substituir o cartão-fidelidade ou saldo de transferência")
    
- Os varejistas podem querer capturar a eficácia de um determinado canal para registrar clientes em um programa de fidelidade. A origem do registro para cartões de fidelidade agora é salva para que os varejistas possam executar relatórios sobre esses dados. A origem dos registros é automaticamente capturada para todos os cartões-fidelidade emitidos de MPOS/CPOS ou de canais de comércio eletrônico. Para os cartões-fidelidade emitidos desde o aplicativo de back office, o usuário de call center poderá selecionar um canal apropriado.
- Nas versões anteriores, os varejistas podiam usar MPOS/CPOS para resgatar pontos de fidelidade para clientes em uma loja. Entretanto, nessas versões, como o saldo de fidelidade era exibido em pontos de fidelidade, o caixa não conseguia ver o valor na moeda que poderia ser aplicado à transação atual. O caixa tinha que fazer a conversão de pontos para moeda antes de pagar por pontos de fidelidade. Na versão atual, depois que as linhas são adicionadas à transação, o caixa pode ver o valor que os pontos de fidelidade podem cobrir para a transação atual, simplificando a aplicação de alguns ou de todos os pontos de fidelidade à transação. Adicionalmente, o caixa pode ver os pontos que vão expirar nos próximos 30 dias, de forma a fazer uma venda adicional ou uma venda cruzada para motivar o cliente a gastar os pontos a expirar nessa transação.

    ![Pontos cobertos por saldo de fidelidade](./media/Points-covered-by-loyalty-balance.png "Exibir saldo coberto por pontos de fidelidade")

    ![Pontos em vencimento](./media/Expiring-points.png "Exibir pontos em vencimento")

- Com a versão 8.1.3, habilitamos a opção "pagar por fidelidade" no canal do call center. Para habilitar essa opção, crie um tipo de concurso de fidelidade e associe-o ao call center. 

    > [!NOTE]
    > Como os pagamentos de fidelidade são configurados como pagamentos de cartão, você terá que selecionar um cartão na página **Configuração do cartão**. 

    ![Configuração do cartão-fidelidade](./media/LoyaltyCardSetup.png "Configuração do cartão-fidelidade")

    Depois da configuração, os clientes podem resgatar seus pontos de fidelidade no call center. Além disso, estamos aprimorando ainda mais a experiência do usuário para mostrar o "Valor coberto por pontos de fidelidade", para que os usuários do call center não precisem navegar para uma tela diferente para visualizar o saldo de fidelidade.

- Muitos varejistas concedem os pontos de fidelidade com base apenas em transações de vendas, mas os varejistas centrados nos clientes desejam recompensá-los por qualquer atividade de envolvimento com a marca. Por exemplo, eles desejam oferecer recompensas pelo preenchimento de uma pesquisa online, pela visita a uma loja, por curtidas no Facebook ou tweets sobre o varejista. Para isso, o varejista poderá definir qualquer número de "Outro tipo de atividade" e definir as regras de ganhos correspondentes para essas atividades. Há também uma API do Commerce Scale Unit exposta "PostNonTransactionalActivityLoyaltyPoints" que pode ser chamada quando uma atividade é identificada e deve recompensar o cliente com pontos de fidelidade. Essa API espera a ID do cartão-fidelidade, a ID do canal e a ID do outro tipo de atividade para que o cliente a ser recompensado possa ser localizado e a regra de ganho para a atividade possa ser identificada. 

    A atribuição de pontos para atividades sem transação geralmente tem duas etapas principais:

    - Identificação de uma atividade que deve ser recompensada.
    - Atribuição dos pontos apropriados.

    A primeira etapa é externa ao Commerce, como tweets sobre a marca ou curtidas da marca no Facebook. Depois que essa atividade for reconhecida, os varejistas poderão chamar a API do Commerce Scale Unit mencionada acima e conceder pontos de fidelidade em tempo real. Em tais cenários, não há necessidade de uma etapa de revisão porque uma atividade ocorreu e pontos correspondentes devem ser concedidos. Contudo, há cenários em que o varejista gostaria de revisar os registros antes de conceder os pontos. Por exemplo, o varejista configurou um workshop na loja para o qual os clientes se inscrevem no site de comércio eletrônico ou qualquer outro aplicativo de registro de eventos. No entanto, apenas os clientes presentes devem ganhar pontos de fidelidade. Para tais cenários, na versão 10.0, introduzimos uma entidade de dados denominada **Linhas de tipo de outra atividade de fidelidade de varejo**. Essa entidade de dados permite que os varejistas usem a Estrutura de Importação/Exportação de Dados (DIXF) ou a API OData para registrar as atividades que devem conceder aos clientes pontos de fidelidade. A entidade de dados armazena as atividades em um diário chamado **Linhas de fidelidade para outras atividades**, que pode ser usado para fins de revisão e modificação. Após a revisão dos dados, o usuário de TI pode postar manualmente as linhas de atividade ou executar um trabalho chamado **Processar outro tipo de atividade para linhas de fidelidade**, que publicará todas as linhas de atividade não publicadas e atribuirá os pontos aos clientes com base nas regras de ganho. No cenário acima, o aplicativo de registro de eventos chamaria a API OData para enviar as informações do cliente para o Commerce. No entanto, o usuário de TI pode postar as linhas de atividade apenas para os clientes que participaram do workshop e excluir as linhas de atividade dos outros clientes. 

    > [!NOTE]
    > Atualmente, o sistema obriga os usuários a configurar uma sequência numérica para "outros tipos de atividade", mas isso não será uma etapa obrigatória em versões futuras. Para configurar uma sequência numérica, acesse **Parâmetros compartilhados do Commerce** \> **Sequências numéricas** e selecione uma sequência numérica para **Outra ID de tipo de atividade de fidelidade**.

- Para fornecer um bom atendimento ao cliente e resolver efetivamente as consultas dos clientes, é importante que os caixas tenham acesso ao perfil completo do cliente. Com a versão 10.0, os caixas poderão ver os detalhes do histórico de fidelidade juntamente com o programa de fidelidade associado e as informações sobre o PDV.
- A remessa grátis ou com desconto é um dos maiores fatores de motivação para os clientes comprarem online. Para habilitar os varejistas a configurar promoções de remessa, com a versão 10.0, introduzimos um novo tipo de promoção chamado "Desconto de limite de remessa", em que o varejista pode definir os limites que, quando atendidos, qualificarão os clientes à remessa gratuita ou com desconto. Por exemplo, gaste US$ 35 para “Remessa de dois dias” gratuita ou “Remessa de dois dias” gratuita para todos os clientes do programa de fidelidade. Este recurso aproveita o novo recurso de encargos automáticos avançados. Consulte a [documentação sobre os encargos automáticos avançados](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges). Esses encargos automáticos avançados precisam estar habilitados para promoção de remessa para funcionarem. Elas podem ser habilitadas na guia **Ordens de cliente** na página **Parâmetros do Commerce** e ative a configuração "Usar encargos automáticos avançados". Além disso, como um varejista pode configurar vários tipos de encargo, como manuseio ou instalação, o varejista precisa especificar qual encargo é considerado como encargo de remessa. Os descontos de remessa são aplicados apenas às despesas de remessa. Para especificar o encargo como Encargo de remessa, navegue até o formulário **Códigos de encargo** presente em **Retail e Commerce** \> **TI de Retail e Commerce** \> **Configuração de canal** \> **Encargos** e marque a caixa de seleção "Encargo de remessa" para os encargos desejados. Agora, você pode navegar até o formulário **Desconto limite de remessa** e configurar o desconto.

    Como descontos de produto, esse desconto respeita todos os recursos de desconto padrão existentes, como permitir que o varejista restrinja esses descontos com os cupons, para que apenas os clientes com cupons possam obter esses descontos. Além disso, esses descontos utilizam o recurso de grupos de preços para determinar a qualificação de tais descontos. Por exemplo, o varejista pode optar por executar essas promoções apenas nos canais online e/ou em canais para determinados grupos de clientes, como clientes do programa de fidelidade. Depois que as linhas da ordem com o modo de entrega especificado atendem ao limite definido, o desconto de remessa é aplicado e reduz o encargo de remessa com base na configuração do desconto. 

    > [!NOTE]
    > Diferentemente de outros descontos periódicos, como descontos por quantidade, simples, de compra combinada e de limite, o desconto de remessa não cria linhas, em vez disso, edita o encargo de remessa diretamente e anexa o nome do desconto na descrição do encargo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]