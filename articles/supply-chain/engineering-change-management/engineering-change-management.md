---
title: Gerenciar alterações em produtos de engenharia
description: Este tópico fornece informações sobre o gerenciamento de alterações de engenharia. O gerenciamento de alterações de engenharia fornece processos estruturados para o gerenciamento de alterações em produtos de engenharia, a proposta, a solicitação e a realização de alterações, a revisão e a aprovação das alterações, a avaliação do impacto sobre transações existentes e a acompanhamento delas.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 55952a9b1c25b806ee4a21ef1982c5b15a41adeb9c9bfdf2fccb8c9da242ffdb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714321"
---
# <a name="manage-changes-to-engineering-products"></a>Gerenciar alterações em produtos de engenharia

[!include [banner](../includes/banner.md)]

O gerenciamento de alterações de engenharia fornece processos estruturados para gerenciar alterações em produtos de engenharia. Você pode usar o processo de *solicitação de alterações de engenharia* para propor e solicitar alterações e, depois, usar o processo de *ordem de alterações da engenharia* para de fato fazer essas alterações. Os usuários podem criar solicitações de alteração de engenharia ou ordens de alteração de engenharia. Há um processo para revisá-las e aprová-las, avaliar seu impacto sobre as transações existentes e acompanhá-las.

## <a name="engineering-change-requests"></a>Solicitações de alteração de engenharia

O processo de solicitação de alteração de engenharia permite que você capture solicitações de alterações de todos os departamentos relevantes da sua empresa. Não importa se você trabalha como um engenheiro ou no departamento de vendas, fornecimento, depósito ou venda: qualquer pessoa pode usar uma solicitação de alteração de engenharia para solicitar uma alteração. Essa alteração pode ser uma ideia para um novo produto, uma questão que você descobriu enquanto trabalhava com um produto existente, uma sugestão para melhorar um produto existente ou outra coisa.

Depois que alguém envia uma solicitação de alteração, o processo de *revisão e aprovação* é gerenciado por um fluxo de trabalho que identifica quem deve aprovar a alteração (por exemplo, o proprietário do produto).

Para configurar um fluxo de trabalho para ordens de alteração de engenharia ou solicitações de alteração de engenharia, acesse **Gerenciamento de alterações de engenharia \> Fluxos de trabalho de engenharia**. Selecione **Novo**, selecione se o fluxo de trabalho será usado para revisar ordens de alteração de engenharia ou solicitações de alteração de engenharia e configure o fluxo de trabalho.

Para obter mais informações sobre como fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md). Para obter mais informações sobre proprietários de produtos, consulte [Proprietários de produtos](product-owner.md).

### <a name="create-a-new-engineering-change-request"></a>Criar uma nova solicitação de alteração de engenharia

Para criar uma solicitação de alterações de engenharia, siga uma destas etapas.

- Acesse **Gerenciamento de alterações de engenharia \> Comum \> Gerenciamento de alterações de engenharia \> Solicitações de alterações de engenharia** e selecione **Novo** no Painel de Ações.
- Abra a página **Detalhes do produto** para um produto de engenharia existente. No Painel de Ações, na guia **Engenharia**, no grupo **Gerenciamento de alterações de engenharia**, selecione **Solicitação de alterações de engenharia \> Nova solicitação de alterações de engenharia**.

Uma nova solicitação de alterações é criada. Agora você pode definir campos em cada FastTab, conforme descrito nas subseções a seguir.

#### <a name="general-fasttab"></a>FastTab Geral

A FastTab **Geral** permite que você forneça uma descrição básica da solicitação de alterações. A tabela a seguir descreve os campos nessa FastTab.

| Campo | descrição |
|---|---|
| Solicitação de alteração | Insira um nome para a solicitação de alterações de engenharia. |
| Cargo | Digite o texto que descreve brevemente ou identifica as alterações na solicitação. |
| Prioridade | Selecione um valor para indicar a alta prioridade da alteração. Você pode personalizar os valores disponíveis para sua empresa, conforme necessário. (Para obter mais informações, consulte [Estabelecer valores comuns para o gerenciamento de alterações de engenharia](engineering-change-management-setup.md).) |
| Categoria | Selecione um valor para descrever o tipo de alteração que você está solicitando. Você pode personalizar os valores disponíveis para sua empresa, conforme necessário. (Para obter mais informações, consulte [Estabelecer valores comuns para o gerenciamento de alterações de engenharia](engineering-change-management-setup.md).) |
| Gravidade | Selecione um valor para indicar a gravidade do problema que deve ser corrigido pela implementação da solicitação. Você pode personalizar os valores disponíveis para sua empresa, conforme necessário. (Para obter mais informações, consulte [Estabelecer valores comuns para o gerenciamento de alterações de engenharia](engineering-change-management-setup.md).) |
| Solicitado por | O nome do usuário que criou a solicitação. |
| Ativo | A data em que a solicitação foi criada. |
| Status | O status da solicitação. Quando uma solicitação é criada pela primeira vez, o status é *Criado*. Quando a solicitação for aprovada, o status será alterado para *Aprovado*. Se uma ordem de alteração relacionada tiver sido criada para a solicitação, o status será alterado para *Acompanhado*. |
| Ordem de alteração | O número da ordem de alteração, caso a solicitação de alteração tenha sido acompanhada por meio de uma ordem de alteração. |

#### <a name="information-fasttab"></a>FastTab Informações

A FastTab **Informações** permite adicionar mais informações sobre a solicitação.

Para adicionar uma linha à grade, selecione **Novo** na barra de ferramentas acima da grade e, depois, selecione uma das seguintes opções:

- **Arquivo** – carregue um arquivo.
- **Imagem** – carregue um arquivo de imagem.
- **Nota** – insira uma nota diretamente na grade.
- **URL** – insira uma URL diretamente na grade.

A tabela a seguir descreve os campos em cada linha.

| Campo | Descrição |
|---|---|
| Data e hora de criação | A data e a hora em que a linha foi criada. |
| Tipo | O tipo de informação para o qual a linha foi criada (arquivo, imagem, nota ou URL). |
| descrição | Insira uma descrição para a linha. |
| Restrição | Um valor que indica se as informações adicionadas foram obtidas de uma fonte interna ou externa. |
| Anexado | Uma caixa de seleção marcada indica que a linha inclui um anexo (arquivo ou imagem). Para baixar o anexo, selecione a linha e, depois, selecione **Abrir** na barra de ferramentas acima da grade. |

#### <a name="products-fasttab"></a>FastTab Produtos

A FastTab **Produtos** permite que você liste cada produto afetado pela solicitação de alteração. Você pode usar os botões da barra de ferramentas para adicionar produtos à grade ou para removê-los.

Esta lista é meramente informativa. Portanto, você pode adicionar quantos produtos relacionados considerar relevantes. Se você criar uma solicitação de alteração na página **Detalhes do produto** para um produto existente, esse produto deverá ser listado na FastTab **Produtos** depois que você salvar o registro da solicitação.

#### <a name="source-fasttab"></a>FastTab Fonte

A FastTab **Fonte** permite rastrear o ponto inicial da solicitação de alteração. Ela será útil se, por exemplo, você desejar saber se a solicitação de alteração foi criada a partir de uma ordem de venda, quem a criou e a empresa na qual ela foi criada.

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>Avaliar o impacto comercial de uma solicitação de alteração e enviar notificações

Ao revisar uma solicitação de alteração, você pode procurar dependências. Dessa forma, você pode avaliar o impacto da alteração solicitada nas transações abertas, como ordens de venda, ordens de produção e estoque disponível. Ao analisar as solicitações de alteração, você pode enviar notificações às pessoas que são responsáveis por cumprir os vários tipos de ordens relacionadas.

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>Revisar as transações afetadas, bloquear transações selecionadas e enviar notificações

Para revisar as transações afetadas, bloquear transações selecionadas e enviar notificações relacionadas, siga estas etapas.

1. Acesse **Gerenciamento de alterações de engenharia \> Comum \> Gerenciamento de alterações de engenharia \> Solicitações de alteração de engenharia**.
1. Abra uma solicitação de alteração existente ou selecione **Novo** no Painel de Ações para criar uma nova solicitação de alteração.
1. No Painel de Ações, na guia **Solicitação de alteração**, no grupo **Impacto comercial**, selecione um dos seguintes botões:

    - **Pesquisa** – examina todas as transações abertas e abre a caixa de diálogo **Impacto comercial para transações abertas**, que lista todas as transações que serão afetadas pela alteração.
    - **Exibir pesquisa anterior** – abra a caixa de diálogo **Impacto comercial para transações abertas**, que lista os resultados da pesquisa anterior. (Não é feita uma nova pesquisa).

1. A caixa de diálogo **Impacto comercial para transações abertas** fornece um conjunto de guias, cada uma das quais mostra uma lista de transações afetadas de um tipo específico (**Ordens de venda**, **Ordens de compra**, **Ordens de produção**, **Estoque**, etc.). Cada guia também mostra um número que indica o número de transações afetadas desse tipo. Selecione uma guia para exibir a lista relevante.
1. Para trabalhar com uma transação na lista, selecione-a e, em seguida, selecione um dos botões a seguir na barra de ferramentas:

    - **Exibir transação** – abra o registro de transação selecionado.
    - **Ordem de bloqueio** – este botão está disponível apenas na guia **Ordens de venda**. Selecione-o para bloquear a ordem de venda selecionada.
    - **Linha de bloqueio** – este botão está disponível apenas na guia **Ordens de venda**. Selecione-o para bloquear a linha da ordem de compra selecionada.
    - **Notificar responsável** – este botão só está disponível na **guia ordens de venda**. Selecione-o para enviar uma notificação de alteração para o usuário definido como responsável pela ordem de venda selecionada.
    - **Notificar responsável** – este botão só está disponível na guia **Ordens de compra**. Selecione-o para enviar uma notificação de alteração para o usuário definido como responsável pela ordem de venda selecionada.
    - **Notificar produção** – este botão está disponível apenas na guia **Ordens de produção**. Diferentemente das ordens de venda e ordens de compra, as ordens de produção não têm um único usuário definido como responsável por eles de ponta a ponta. Em vez disso, vários supervisores ou planejadores geralmente se apropriam de um site específico ou de uma parte específica da produção (por exemplo, para recursos ou grupos de recursos específicos). Portanto, quando você seleciona este botão, todos os usuários responsáveis por qualquer recurso relacionado à ordem de produção selecionada recebem uma notificação de alteração.
    - **Notificar preparador** – este botão só está disponível na guia **Requisição de compra**. Selecione-o para enviar uma notificação de alteração para o usuário definido como preparador pela requisição de compra selecionada.
    - **Notificar responsável pela venda** – este botão só está disponível na guia **Cotações**. Selecione-o para enviar uma notificação de alteração para o usuário definido como responsável pela cotação selecionada.
    - **Sucata** – este botão só está disponível na guia **Estoque**. Selecione-o para sucatear o estoque selecionado.
    - **Exibir histórico** – abre um histórico de ações que foram executadas na transação selecionada usando a caixa de diálogo **Impacto comercial para transações abertas**. (Por exemplo, o histórico mostra se as notificações foram enviadas ou as transações foram bloqueadas.) 
    - **Exibir todas as transações** – abre a lista completa de todas as transações, não apenas as transações abertas.

#### <a name="review-and-process-change-notifications-for-transactions"></a>Analisar e processar notificações de alteração para transações

Você pode ler e processar as notificações de alteração recebidas das seguintes maneiras:

- Exceto no caso de ordens de produção, altere as notificações para as transações que você é responsável por aparecer na Central de ações. O botão **Mostrar mensagens** (símbolo de sino) no lado direito da barra de navegação indica quando uma mensagem está disponível para você na Central de ações. Selecione o botão **Mostrar mensagens** para abrir a Central de ações e revisar as mensagens.
- Para exibir todas as ordens de produção para as quais uma notificação de engenharia foi enviada, Acesse **Ordens de produção \> Ordens de produção \> Todas as ordens de produção**. Em seguida, na Página de Ações na guia **Ordem de produção**, no grupo **Solicitação de alteração de engenharia**, selecione **Notificações de engenharia** para abrir a página **Notificações de engenharia**.
- Para ordens de produção, você pode optar por revisar somente as notificações de alteração que se aplicam aos recursos de produção que você gerencia. No espaço de trabalho **Gerenciamento de chão de fábrica**, no Painel de Ações, selecione **Configurar meu espaço de trabalho** para filtrar a página de forma que mostre apenas informações sobre as unidades de produção, grupos e/ou recursos que você gerencia. Na seção **Resumo**, um bloco denominado **Ordens de produção com produtos alterados** mostra uma contagem de notificações que correspondem às suas configurações de filtro. Selecione este bloco para abrir a página **Notificações de engenharia**, que mostra a lista completa de transações que atendem aos critérios do filtro.

Ao revisar as notificações de ordem de produção na página **Notificações de engenharia**, você pode seguir links para ordens de alteração relacionadas ou ordens de produção selecionando valores de coluna ou usando os comandos relacionados no Painel de Ações. Depois de concluir a avaliação de uma alteração e depois de ter cancelado ou modificado as ordens de produção, conforme necessário, você poderá marcar uma notificação como resolvida. Selecione a notificação e, no Painel de Ações, selecione **Resolver**. A notificação é removida das exibições de todos os usuários.

### <a name="create-a-change-order-from-a-change-request"></a>Criar uma ordem de alteração de uma solicitação de alteração

Um engenheiro que está revendo uma solicitação de alteração de engenharia pode criar uma ordem de alteração de engenharia diretamente na página **Solicitações de alteração de engenharia**. No Painel de Ações, na guia **Solicitação de alteração**, no grupo **Ordem de alteração de engenharia**, selecione **Copiar link e produtos**.

## <a name="engineering-change-orders"></a>Ordens de alteração de engenharia

As ordens de alterações de engenharia fornecem um processo estruturado para criar alterações em produtos de engenharia. Você propõe alterações usando uma cópia dos dados relevantes para a engenharia. Os dados mestres reais não são afetados. Para obter mais informações sobre dados relevantes de engenharia, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).

Você pode criar uma ordem de alteração de engenharia baseada em uma solicitação de alteração de engenharia aprovada. Os engenheiros também podem criar ordens de alteração de engenharia desde o início. Você pode incluir vários produtos em uma única ordem de alteração de engenharia seguindo uma destas etapas:

- Selecione produtos manualmente.
- Use a BOM (lista de materiais) para incluir produtos que são inferiores na estrutura de produtos (ou seja, filhos).
- Use uma pesquisa onde é usado para incluir produtos que são superiores na estrutura de produtos (ou seja, pais).

Depois que a proposta de alterações for concluída, o processo de revisão e aprovação será tratado por um fluxo de trabalho. É possível configurar fluxos de trabalho diferentes, com base na prioridade e na gravidade.

Para configurar um fluxo de trabalho para ordens de alteração de engenharia ou solicitações de alteração de engenharia, acesse **Gerenciamento de alterações de engenharia \> Fluxos de trabalho de engenharia**. Selecione **Novo**, selecione se o fluxo de trabalho será usado para revisar ordens de alteração de engenharia ou solicitações de alteração de engenharia e configure o fluxo de trabalho.

Para obter mais informações sobre fluxos de trabalho, consulte [Visão geral do sistema de fluxo de trabalho](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

Estas são algumas partes interessadas típicas que talvez precisem aprovar uma ordem de alteração de engenharia:

- **Proprietários de produtos** – Para obter mais informações sobre proprietários de produtos, consulte [Proprietários de produtos](product-owner.md).
- **Líder da equipe responsável** – o campo **Engenheiro** na exibição **Cabeçalho** da ordem de alteração de engenharia mostra o engenheiro que criou a ordem de alteração de engenharia. Se o engenheiro pertencer a uma equipe definida no sistema, o campo **Responsável** mostrará o líder dessa equipe.
- **Departamento financeiro** – o departamento financeiro talvez precise revisar casos em que a alteração envolva altos custos.

Você pode escolher se a ordem de alteração de engenharia deve ser processada diretamente após ser aprovada, como parte do fluxo de trabalho, ou se o processamento deve ser feito mais tarde, como uma etapa manual. Durante o processamento de uma ordem de alteração de engenharia, os dados de engenharia do produto real são atualizados.

Enquanto estiver revisando uma solicitação de alteração, no Painel de Ações, na guia **Solicitação de alteração**, no grupo **Impacto comercial**, selecione **Pesquisar** para avaliar o impacto da alteração proposta em transações abertas, como ordens de venda, ordens de produção e estoque disponível. Os resultados são mostrados na caixa de diálogo **Impacto comercial para transações abertas**, na qual você pode selecionar transações afetadas e usar comandos na barra de ferramentas para exibir mais informações, notificar o usuário responsável ou bloquear a transação.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Ordens de alteração de engenharia em empresas de engenharia ou operacionais

Como é descrito em [Empresas de engenharia e regras de propriedade de dados](engineering-org-data-ownership-rules.md), os dados de produtos que podem ser editados variam, de acordo com o tipo de entidade legal em que você está trabalhando (uma empresa de engenharia x uma empresa operacional). As regras de propriedade de dados também são aplicadas às ordens de alteração de engenharia. Portanto, dependendo da entidade legal em que você cria uma ordem de alteração de engenharia, diferentes tipos de alterações podem ser feitas. Eis alguns exemplos:

- Para ordens de alteração de engenharia em uma *empresa de engenharia*, você pode fazer alterações básicas nos dados de engenharia. Por exemplo, você pode criar novas versões de um produto, alterar a estrutura de um produto por meio da BOM e alterar os valores de atributo de engenharia. Para cada produto afetado, selecione um dos seguintes valores no campo **Impacto**:

    - **Nenhum** – atualize a versão do produto existente (atualização na versão).
    - **Nova versão** – crie uma nova versão baseada na versão do produto selecionada.
    - **Novo produto** – crie um produto totalmente novo com base na versão do produto selecionada.
    - **Nova grade** – crie uma nova grade baseada na versão do produto selecionada. As informações de BOM e de roteiro serão copiadas.

- Para ordens de alteração de engenharia em uma *empresa operacional*, você pode alterar os dados logísticos do produto. Por exemplo, você pode enriquecer a BOM existente com as configurações de origem, adicionar roteiros locais ou BOMs locais, e até enriquecer uma BOM adicionando novas linhas de BOM para o material de embalagem local, fluidos de lubrificação ou instruções no idioma local. Os aprimoramentos que os usuários fazem na empresa operacional serão preservados quando novas atualizações forem enviadas da empresa de engenharia. Para obter mais informações, consulte [Empresas de engenharia e regras de propriedade de dados](engineering-org-data-ownership-rules.md).

    Quando as ordens de alteração de engenharia são processadas na empresa de engenharia, os produtos são criados e/ou atualizados somente na empresa de engenharia. Portanto, se os dados do produto mestre também precisarem ser atualizados, você também deverá liberar os produtos para empresas operacionais.

- Você pode liberar produtos diretamente das ordens de alteração de engenharia. Abra a ordem de alteração e, no Painel de Ações, na guia **Alterar ordem**, no grupo **Liberações de produtos**, selecione **Liberar a estrutura de produtos**. O processo funciona da mesma forma que funciona quando você libera produtos na página **Produtos liberados**. Para obter mais informações, consulte [Liberar estruturas de produtos](release-product-structure.md).
- Você pode fazer com que os produtos sejam liberados automaticamente das ordens de alteração de engenharia, com base nos seguintes fatores:

    - Libera novamente para empresas em que produtos foram liberados anteriormente. Selecione **Pesquisar** para verificar todas as versões anteriores e, depois, selecione **Exibir** para exibir os resultados. A página **Exibir** mostra as versões anteriores do produto e você pode selecionar quais produtos deseja lançar novamente. Em seguida, feche a página **Exibir** e selecione **Processar** para liberar novamente os produtos selecionados.
    - Configurações de liberação automática no controle de liberação da categoria de produto de engenharia. Você pode fazer esta liberação como parte do fluxo de trabalho. Quando o bloco **coletar proposta de liberação** for usado, a proposta de liberação será preenchida com as propostas de nova liberação (consulte o item anterior da lista) e os produtos serão liberados para empresas se a caixa de seleção **Liberação automática** estiver marcada no controle de liberação da categoria de produto de engenharia. Você pode selecionar **Exibir** para exibir os resultados, conforme descrito no item da lista anterior. Os produtos também serão liberados quando o bloco **processar proposta de liberação** for usado. Se você optar por coletar somente a proposta de liberação como parte do fluxo de trabalho, poderá iniciar manualmente a liberação selecionando **Processar**, conforme descrito no item de lista anterior.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Acompanhar uma solicitação de alteração de engenharia por meio de uma ordem de alteração de engenharia

Assim que uma solicitação de alteração de engenharia aprovada, você poderá acompanhá-la por meio de uma ordem de alteração de engenharia. Você pode combinar várias solicitações de alteração de engenharia em uma única ordem de alteração de engenharia. Uma única ordem de alteração de engenharia pode, inclusive, incluir vários produtos. (Em geral, você usa essa abordagem quando a mesma alteração deve ser aplicada a vários produtos.) No entanto, não é possível criar várias ordens de alteração de engenharia a partir de uma única solicitação de alteração de engenharia.

Para acompanhar uma solicitação de alteração por meio de uma ordem de alteração, abra a solicitação de alteração e, no Painel de Ações, na guia **Alterar ordem**, no grupo **Ordem de alteração de engenharia**, selecione **Copiar link e produtos**. Em seguida, você pode selecionar uma ordem de alteração de engenharia existente para conectar a solicitação de alteração ou pode criar uma nova ordem de alteração de engenharia para essa solicitação específica.

## <a name="engineering-change-order-report"></a>Relatório de ordens de alteração de engenharia

Relatórios de ordem de alteração de engenharia descrevem as alterações feitas em uma ordem de alteração de engenharia. Eles são úteis durante e após o processo de revisão e aprovação.

Para exibir um relatório de ordem de alteração de engenharia, abra a ordem de alteração relevante e, no Painel de Ações, na guia **Alterar ordem**, no grupo **Exibir**, selecione **Relatório de ordem de alteração de engenharia**.

## <a name="fields-on-an-engineering-change-order"></a>Campos em uma ordem de alteração de engenharia

A maioria dos campos em ordens de alteração de engenharia são iguais aos campos de produtos liberados, versões de engenharia, documentos, BOMs (linhas) e roteiros (operações). No entanto, os campos na tabela a seguir são exclusivos de ordens de alteração.

| Campo | descrição |
|---|---|
| Motivos de alteração de engenharia | Selecione o motivo para alterar o produto afetado. |
| Alterar descrição | Insira uma descrição da alteração. |
| Ferramentas especiais necessárias | Especifique se as ferramentas especiais são necessárias para aplicar a alteração. |
| Disposição do material de engenharia | Selecione um código de disposição do material para qualquer desperdício gerado quando a alteração for aplicada. |
| Aprovação do cliente necessária | Especifique se a aprovação do cliente é necessária antes de aplicar a alteração. |
| Aprovação do cliente recebida | Especifique o status da aprovação do cliente. |
| Integridade e segurança ambientais | Especifique se as regras de segurança e de integridade ambientais são aplicáveis à alteração. Em caso afirmativo, você poderá selecionar as regras aplicáveis. |

Você pode usar o botão **Manter/copiar informações de alteração** para copiar informações de alteração entre os produtos afetados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
