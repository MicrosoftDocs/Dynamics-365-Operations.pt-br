---
title: Alocação automática de encargos
description: O recurso de encargos no Microsoft Dynamics 365 Supply Chain Management ajuda você a alocar automaticamente encargos a ordens de compra ou ordens de venda.
author: GalynaFedorova
ms.date: 09/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c6729e9a485205a6beb53441798952fac2b93ef7
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673036"
---
# <a name="automatic-allocation-of-charges"></a>Alocação automática de encargos

[!include [banner](../includes/banner.md)]

Com base no cliente com o qual você está trabalhando ou no item que você está vendendo, talvez seja necessário aplicar encargos adicionais específicos. O recurso *encargos* no Microsoft Dynamics 365 Supply Chain Management ajuda você a alocar automaticamente encargos a ordens de compra ou ordens de venda.

Os encargos automáticos, são aplicados automaticamente quando você criar uma ordem de venda ou uma ordem de compra. É possível definir encargos automáticos para fornecedores, clientes, grupos de fornecedores ou itens específicos. Você também pode definir os encargos automáticos que se aplicam a todos os fornecedores, clientes ou itens.

## <a name="set-up-parameters"></a>Configurar parâmetros

A página **Parâmetros de compras e fornecimento** terá algumas configurações especialmente relevantes quando você quiser alocar encargos de forma automática. Para concluir essa configuração, siga essas etapas.

1. Acesse **Compras e fornecimento \> Configuração \> Parâmetros de compras**.
1. Abra a guia **Preços**.
1. Na Guia Rápida **Preços**, faça as seguintes configurações:
    - **Localizar encargos automáticos para cabeçalho** – especifica se os encargos devem ser alocados automaticamente para os cabeçalhos da ordem de compra. Defina como *Sim* para usar a alocação automática de encargos.
    - **Localizar encargos automáticos para linha** – especifica se os encargos devem ser alocados automaticamente para as linhas da ordem de compra. Defina como *Sim* para usar a alocação automática de encargos.

## <a name="set-up-charges-codes"></a>Configurar códigos de encargos

Para alocar encargos, você deve primeiro definir os códigos de encargos.

1. Siga uma destas etapas:

    - Para ordens de compra: acesse **Contas a pagar \> Configuração de encargos \> Código de encargos**.
    - Para ordens de venda: acesse **Contas a receber \> Configuração de encargos \> Código de encargos**.

1. No Painel de Ações, selecione **Novo** para criar um código de encargos.
1. No cabeçalho do novo registro, defina os seguintes campos:

    - **Código de encargos** — insira um código para os encargos.
    - **Descrição** — insira uma descrição dos encargos.
    - **Grupo de impostos do item** — selecione um grupo de impostos do item, se aplicável.
    - **Ratear** — defina esta opção como *Sim* se você deseja ratear os encargos. Essa opção está disponível somente para ordens de venda.
    - **Valor máximo** — insira o valor máximo permitido para o código de encargos. Esse campo é usado para validar encargos para faturas de fornecedor. Ele está disponível somente para ordens de compra.

        > [!NOTE]
        > Para ativar a funcionalidade de validação de encargos para ordens de compra, acesse **Contas a pagar \> Configurar \> Parâmetros de contas a pagar**. Na FastTab **Validação de fatura**, na seção **Validação de fatura**, defina a opção **Habilitar validação da conciliação de faturas** como *Sim*.

1. A FastTab **Lançamento** inclui as seções **Débito** e **Crédito**. Defina os campos a seguir, dependendo do razão no qual você deseja lançar os encargos:

    - **Tipo** – selecione o tipo de conta na qual você está fazendo o lançamento (*Razão*, *Cliente* ou *Item*).
    - **Lançamento** — selecione o tipo de lançamento a ser criado (como *Taxa do agente* ou *Liquidações de cliente*).
    - **Conta** — selecione a conta na qual lançar o encargo.

1. No Painel de ações, selecione **Salvar**.

## <a name="create-charge-groups"></a>Criar grupos de encargos

Os grupos de encargos automaticamente alocam encargos específicos a um grupo de clientes ou fornecedores. As subseções a seguir descrevem como criar e atribuir esses grupos de encargos.

### <a name="charge-groups-for-purchase-orders"></a>Grupos de encargos para a ordens de compra

Para criar grupos de encargos para ordens de compra, siga estas etapas:

1. Acesse **Contas a pagar \> Configuração de encargos \> Grupo de encargos de fornecedor**.
1. No Painel de Ações, selecione **Novo** para adicionar uma linha à grade e, em seguida, defina os seguintes campos:

    - **Grupo de encargos** — insira o nome do grupo de encargos.
    - **Descrição** — insira uma descrição do grupo encargos.

1. No Painel de ações, selecione **Salvar**.
1. Acesse **Contas a pagar \> Fornecedores \> Todos os fornecedores** e abra um fornecedor existente ou crie um fornecedor.
1. Na FastTab **Padrões da ordem de compra**, na seção **Ordem de compra**, defina o campo **Grupo de encargos** como o grupo de encargos que você acabou de criar.

### <a name="charge-groups-for-sales-orders"></a>Grupos de encargos para a ordens de venda

Para criar grupos de encargos para ordens de venda, siga estas etapas:

1. Acesse **Contas a receber \> Configuração de encargos \> Grupos de encargos de cliente**.
1. No Painel de Ações, selecione **Novo** para adicionar uma linha à grade e, em seguida, defina os seguintes campos:

    - **Grupo de encargos** — insira o nome do grupo de encargos.
    - **Descrição** — insira uma descrição do grupo encargos.

1. No Painel de ações, selecione **Salvar**.
1. Acesse **Contas a receber \> Clientes \> Todos os clientes** e abra um cliente existente ou crie um cliente.
1. Na FastTab **Padrões da ordem de compra**, na seção **Ordem de venda**, defina o campo **Grupo de encargos** como o grupo de encargos que você acabou de criar.

## <a name="define-auto-charges"></a>Definir encargos automáticos

Depois que os códigos de encargos forem configurados, siga estas etapas para definir os encargos automáticos:

1. Siga uma destas etapas:

    - Para ordens de compra: acesse **Compras e fornecimento \> Configurar \> Encargos \> Encargos automáticos**.
    - Para ordens de venda: acesse **Contas a receber \> Configurar \> Configuração de encargos \> Encargos automáticos**.

1. No painel de lista, no campo **Nível**, selecione o nível ao qual o encargo automático se aplica:

    - *Principal* — aplique encargos ao cabeçalho da ordem.
    - *Linha* — aplique encargos às linhas da ordem.

1. Selecione um encargo automático existente para editá-lo ou selecione **Novo** para definir um novo encargo automático.
1. Na lista **Código da conta**, selecione um dos seguintes valores para especificar o escopo das contas que serão afetadas:

    - *Tabela* — atribui encargos a um cliente ou fornecedor específico.
    - *Grupo* — atribui encargos a um grupo de encargos diversos.
    - *Todos* — atribui encargos a todos os clientes ou fornecedores.

1. No campo **Relação de cliente** ou **Relação de fornecedor**, selecione um cliente ou fornecedor específico que você definiu no campo **Código da conta** como *Tabela*. Se você definiu o **Código da conta** como *Grupo*, selecione um grupo de encargos de cliente ou de fornecedor.
1. No campo **Código do item**, selecione um dos seguintes valores para especificar o escopo dos itens que serão afetados: Você só poderá selecionar um código de item ao definir encargos automáticos no nível de linha.

    - *Tabela* — atribua encargos a um item específico.
    - *Grupo* — atribua encargos a um grupo de encargos de item.
    - *Todos* – atribua encargos a todos os itens.

1. No campo **Relação de itens**, selecione um item específico se você definiu o campo **Código do item** como *Tabela*. Se você definiu o campo **Código do item** como *Grupo*, selecione um grupo de encargos de item.
1. **Somente para ordens de venda:** no campo **Código do modo de entrega**, selecione um dos seguintes valores para especificar o escopo dos modos de entrega que serão afetados:

    - *Tabela* — atribui encargos a um modo de entrega específico.
    - *Grupo* — atribui encargos a um modo de grupo de entregas.
    - *Todos* — atribui encargos a todos os modos de entrega.

1. **Somente para ordens de venda:** no campo **Relação de modo de entrega**, selecione um modo de entrega específico se você definiu o campo **Código do modo de entrega** como *Tabela*. Se você definiu o campo **Código do modo de entrega** como *Grupo*, selecione um modo de grupo de entregas.
1. Na FastTab **Linhas**, defina os encargos e as taxas de encargos que serão usados quando o encargo automático atual for aplicado. Você pode usar a barra de ferramentas nessa FastTab para adicionar quantas linhas forem necessárias. Em cada linha, defina os seguintes campos:

    - **Moeda** — selecione a moeda que deve ser usada para calcular o encargo.
    - **Código de encargos** — selecione o código do encargo.
    - **Categoria** — selecione um dos seguintes valores:

        - *Fixo* — o encargo é inserido como um valor fixo na linha. Os encargos fixos podem ser usados no cabeçalho da ordem e nas linhas da ordem.
        - *Pçs* — o encargo se baseia na unidade. Esses encargos podem ser usados somente em linhas da ordem. Eles serão exibidos quando você calcular o total da ordem.
        - *Porcentagem* — o encargo é inserido como uma porcentagem na linha. A porcentagem dos encargos pode ser usada no cabeçalho da ordem e nas linhas da ordem.
        - *Porcentagem intercompanhia* — o encargo é inserido como uma porcentagem na linha para ordens intercompanhia. A porcentagem intercompanhia dos encargos pode ser usada somente em linhas da ordem.
        - *Externo* — o encargo é calculado por um serviço terceirizado associado a uma ou mais transportadoras.

    - **Valor dos encargos** — insira o valor do encargo, com base na categoria selecionada.
    - **Código da moeda dos encargos** — especifique uma moeda para o encargo se desejar usar uma moeda diferente da moeda especificada no campo **Moeda**. Você poderá inserir uma moeda diferente somente se o campo **Tipo de débito** ou **Tipo de crédito** estiver definido como *Conta contábil* ou *Item* no código de encargos selecionado.
    - **Valor de origem** — especifique um valor inicial ao qual aplicar o encargo automático. Nesse contexto, o valor se refere ao total da ordem.
    - **Valor de destino** — especifique um valor final ao qual aplicar o encargo automático. Nesse contexto, o valor se refere ao total da ordem.
    - **Grupo de impostos** — especifique um grupo de impostos.
    - **Local** e **Depósito** — especifique um local e um depósito se os encargos devem ser aplicados somente a um local e a um depósito específicos.
    - **Manter** — marque essa caixa de seleção para manter as transações de encargos depois que o faturamento for concluído, para que o encargo seja aplicado sempre que você criar uma nova fatura para a conta de cliente selecionada.

1. **Somente para ordens de venda:** se quiser calcular encargos diferenciados, consulte [Encargos diferenciados em ordens de venda](/dynamicsax-2012/appuser-itpro/about-tiered-charges-on-sales-orders) para obter informações.

## <a name="allocate-charges-from-the-header-to-a-line"></a>Alocar encargos do cabeçalho a uma linha

O procedimento a seguir mostra como alocar encargos no nível de cabeçalho a uma linha. Antes de iniciar este procedimento, você já deve ter um encargo de nível de cabeçalho do tipo *valor fixo* e uma ordem em que esse encargo esteja aplicado. Além disso, a ordem já deve incluir pelo menos um item de linha.

1. Abra a ordem de compra ou a ordem de encargos.
1. No Painel de Ações, siga uma destas etapas:

    - Para ordens de compra: na guia **Compra**, no grupo **Encargos**, selecione **Alocar encargos**.
    - Para ordens de venda: na guia **Venda**, no grupo **Encargos**, selecione **Alocar encargos**.

1. Na caixa de diálogo **Alocar encargos às linhas da ordem**, defina os seguintes campos:

    - **Alocação de encargos** — selecione um dos valores a seguir para especificar como os encargos devem ser alocados:

        - *Valor líquido* — aloque os encargos de acordo com cada valor de linha em relação ao valor líquido total.
        - *Quantidade* — aloque encargos de acordo com o número de unidades para cada linha em relação ao número total de unidades.
        - *Por linha* — aloque os encargos igualmente entre o número total de linhas.

    - **Alocar encargos às linhas** — selecione um valor para especificar se os encargos devem ser alocados para todas as linhas, somente para linhas positivas ou somente para linhas negativas.
    - **Alocar tudo** — marque essa caixa de seleção para alocar os encargos às linhas da ordem, mesmo que o código de encargos tenha um tipo de débito diferente de *Item*.
    - **Recebido** — marque essa caixa de seleção para alocar encargos somente às linhas da ordem recebidas.
    - **Em estoque** — marque essa caixa de seleção para alocar encargos somente para as linhas da ordem armazenadas em estoque.
    - **Mostrar seleções e limpar linhas específicas** — marque essa caixa de seleção para excluir linhas específicas dessa alocação. Quando você marca essa caixa de seleção, a grade **Escolher as linhas que serão excluídas da alocação** será aberta. Essa grade inclui somente as linhas que correspondem aos critérios definidos pelas configurações de **Alocar encargos às linhas** e **Em estoque**. Por exemplo, se você definir o campo **Alocar encargos às linhas** como *Linhas positivas* e marcar a caixa de seleção **Em estoque**, somente as linhas positivas e em estoque serão exibidas na grade. Além disso, a grade filtrará automaticamente as linhas nas quais a quantidade total já foi recebida. Enquanto a grade estiver aberta, desmarque a caixa de seleção **Incluir** para cada linha que deva ser excluída da alocação. 

        > [!IMPORTANT]
        > Ao trabalhar com a grade **Escolher as linhas que serão excluídas da alocação**, certifique-se de deixar a grade aberta até selecionar **Alocar**. Se você fechar a grade antes de selecionar **Alocar**, as configurações na grade serão perdidas. Portanto, os encargos serão alocados com base nos critérios definidos anteriormente.

1. Selecione **Alocar** para aplicar suas configurações e fechar a caixa de diálogo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
