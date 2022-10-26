---
title: Planos com base em cotações e RFQs
description: Este artigo descreve como configurar o planejamento mestre para considerar cotações e solicitações de cotação (RFQs) quando ele gera ordens planejadas.
author: t-benebo
ms.date: 09/20/2022
ms.topic: article
ms.search.form: SalesQuotationListPage, ReqPlanSched, SalesQuotationTable, smmOpportunityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-20
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: eaeb3c26a562c1daebe8296b26077ee5a3223e4d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690073"
---
# <a name="plan-based-on-quotations-and-rfqs"></a>Plano com base em cotações e RFQs

[!include [banner](../../includes/banner.md)]

As cotações e solicitações de cotação (RFQs) representam ordens possíveis ou prováveis no futuro. Portanto, faz sentido considerá-las durante o planejamento mestre, de forma que o fornecimento extra possa ser planejado com base em RFQs existentes e na probabilidade de cada cotação se tornar uma ordem real. Este artigo descreve como configurar o planejamento mestre para considerar cotações e RFQs quando ele gera ordens planejadas.

## <a name="set-up-master-planning-to-consider-sales-quotations-andor-rfqs"></a>Configurar planejamento mestre para considerar cotações de venda e/ou RFQs

Use o procedimento a seguir para configurar o planejamento mestre a fim de considerar cotações de venda e/ou RFQs.

1. Acesse **Planejamento Mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano existente no painel de lista ou selecione **Novo** no Painel de Ações para criar um novo.
1. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Incluir cotações de venda** – defina esta opção como *Sim* para considerar cotações de venda quando o plano atual for executado. Defina-o como *Não* para ignorá-los.
    - **Probabilidade %** – defina o nível mínimo de confiança necessário para que uma cotação seja incluída no planejamento mestre. O cálculo do planejamento mestre incluirá todas as cotações criadas a partir de oportunidades com essa porcentagem de probabilidade ou superior. Para incluir todas as cotações, inclusive as cotações sem probabilidade ou oportunidade atribuída a elas, defina este campo como *0* (zero). Para obter mais informações sobre probabilidades para cotações, consulte a próxima seção.
    - **Incluir solicitações de cotação** – defina esta opção como *Sim* para considerar RFQs quando o plano atual for executado. Defina-o como *Não* para ignorá-los. Se você optar por considerar RFQs, o sistema criará ordens de compra planejadas para elas, mas não especificará o fornecedor até que a RFQ seja resolvida. As ordens de compra planejadas criadas para as RFQs podem afetar as quantidades de outras ordens planejadas.

1. Continue a configurar o planejamento mestre da maneira usual.

## <a name="assign-and-view-probabilities-for-quotations"></a>Atribuir e exibir probabilidades de cotação

Como foi mencionado na seção anterior, um plano mestre considerará somente as cotações que atendem ou ultrapassem o limite de probabilidade definido para o plano (se um limite for definido). No entanto, a probabilidade não é definida diretamente em cada cotação. Em vez disso, ela é herdada da oportunidade usada para gerar a cotação. Portanto, as cotações criadas diretamente na página **Todas as cotações** não terão uma probabilidade atribuída a elas ou uma oportunidade associada a elas e nunca serão consideradas pelo planejamento mestre (a menos que o campo **Probabilidade %** seja definido como *0* \[zero\]). Para ter a probabilidade atribuída, deve-se gerar uma cotação a partir de uma oportunidade.

### <a name="create-a-quotation-from-an-opportunity"></a>Criar uma cotação a partir de uma oportunidade

Use o procedimento a seguir para atribuir uma probabilidade a uma oportunidade e, depois, criar uma cotação a partir dessa oportunidade.

1. Vá para **Vendas e marketing \> Relacionamentos \> Oportunidades \> Todas as oportunidades**.
1. Selecione uma oportunidade existente, ou **Nova** no Painel de Ações para criar uma nova.
1. Preencha a página de oportunidade para identificar a oportunidade como desejar. Definir o campo **Probabilidade** com um valor apropriado. Somente os planos mestres configurados para procurar probabilidades deste valor ou superior considerarão as cotações geradas a partir dessa oportunidade.
1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ações, na guia **Oportunidade**, no grupo **Novo**, selecione **Cotação de venda** ou **Cotação de projeto**, dependendo do tipo de cotação que você deseja criar.
1. Na caixa de diálogo **Criar cotação**, defina os campos conforme necessário e selecione **OK**.
1. Uma nova cotação é criada e aberta. Na FastTab **Linhas**, use a barra de ferramentas para adicionar linhas de venda ou linhas de projeto conforme necessário para definir o conteúdo da cotação.
1. No Painel de ações, selecione **Salvar**. Depois feche a cotação.

### <a name="view-the-probability-that-is-assigned-to-a-quotation"></a>Exibir a probabilidade atribuída a uma cotação

A única maneira de exibir a probabilidade atribuída a uma cotação é abrir a oportunidade usada para criar essa cotação, conforme descrito no procedimento a seguir.

1. Acesse **Vendas e marketing \> Cotações de venda \> Todas as cotações**.
1. Se a coluna **ID da oportunidade** não for mostrada (está oculta em uma instalação padrão), siga estas etapas para mostrá-la temporariamente. (Como alternativa, para manter a **ID da oportunidade** disponível, crie uma [exibição salva](../../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json) que a inclua.)

    1. Selecione e segure (ou clique com o botão direito do mouse) na grade e, depois, selecione **Inserir colunas**.
    1. Na caixa de diálogo **Inserir colunas**, localize a linha em que o campo **Campo** está definido como *Oportunidade* e marque a caixa de seleção **Selecionar** dessa linha.
    1. Selecione **Atualizar** para adicionar a coluna selecionada na página **Todas as cotações**.

1. Na grade, localize a linha da cotação relevante. Depois, na coluna **ID da oportunidade**, selecione o valor dessa linha.

    > [!NOTE]
    > Se estiver procurando uma cotação de projeto, talvez precise selecionar o cabeçalho da coluna **Tipo de cotação** e limpar seu filtro. Em uma instalação padrão, esse filtro é definido para que apenas cotações de venda sejam mostradas.

1. A oportunidade relacionada será aberta. Agora você pode exibir e editar o valor da **Probabilidade** conforme necessário.
