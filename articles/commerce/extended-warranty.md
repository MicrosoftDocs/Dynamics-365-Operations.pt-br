---
title: Criar e configurar garantias estendidas
description: Este tópico abrange as garantias estendidas e descreve como criá-las e configurá-las no Microsoft Dynamics 365 Commerce.
author: sijoshi
manager: annbe
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: sijoshi
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 411895763cc282766b5a668208f20c72496059cd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965104"
---
# <a name="create-and-configure-extended-warranties"></a>Criar e configurar garantias estendidas

[!include [banner](includes/banner.md)]

Este tópico abrange as garantias estendidas e descreve como criá-las e configurá-las no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Os clientes estão escolhendo cada vez mais o suporte e os serviços estendidos ao comprarem produtos, especialmente os produtos para consumidores que são vendidos a uma faixa de preço premium, como telefones e computadores. Ao fornecer garantias estendidas para compras, os varejistas podem ajudar a estabelecer a fidelidade do cliente. As garantias estendidas permitem que os clientes saibam a quem recorrer para obter serviço e suporte. Portanto, eles podem ter a certeza de que seus problemas serão tratados de forma eficiente.

As garantias estendidas podem ser vendidas os para clientes em um canal de varejo durante a compra inicial do produto. Elas também podem ser vendidas por um tempo limitado após a compra inicial.

### <a name="warranty-item-setup"></a>Configuração de itens de garantia

O Dynamics 365 Commerce oferece uma funcionalidade que permite criar um item de garantia e definir atributos para ele. Esses atributos incluem a associação entre um produto e um item de garantia, o preço da garantia e a duração da garantia. Depois que um item de garantia é configurado e liberado para a unidade organizacional, um varejista pode vender as garantias pelo Modern POS (MPOS), pelas lojas online e por outros canais de varejo.

### <a name="warranty-item-sales"></a>Vendas de itens de garantia

As garantias estendidas são vendidas em um canal de varejo durante a compra inicial do produto. Elas também podem ser vendidas por um tempo limitado após a compra inicial.

No ponto de venda (PDV), os representantes de vendas são avisados para adicionar uma garantia estendida quando um produto relacionado é adicionado ao carrinho de um cliente. Portanto, uma oportunidade de venda adicional ou de venda cruzada é apresentada aos representantes de vendas como parte do fluxo de vendas.

Os clientes também podem retornar depois e comprar uma garantia estendida para um produto comprado anteriormente. Nesses casos, um representante de vendas pode pesquisar a transação original e vender ao cliente o item de garantia estendida relacionado.

### <a name="warranty-terminology"></a>Terminologia da garantia

A tabela a seguir define alguns termos relacionados à garantia.

| Termo | descrição |
|------------------------------|--------------|
| Garantia estendida/garantia | Uma *garantia estendida* refere-se a um contrato de serviço ou um contrato que fornece uma garantia prolongada aos clientes. A garantia estendida inclui o serviço adicional de substituição ou reparo de produtos durante o período de cobertura da garantia estendida. |
| Garantia do fabricante | Uma *garantia do fabricante* (geralmente chamada de *garantia limitada*) é a garantia que os clientes recebem ao comprar um produto. Veja algumas características da garantia de um fabricante:<ul><li>O custo da garantia está incluído no custo do produto. Os clientes não têm que pagar nenhum valor adicional para a garantia do fabricante.</li><li>Dependendo da categoria do produto, a garantia do fabricante geralmente dura 30 dias, seis meses ou um ano. (Para a maioria dos aparelhos eletrônicos, a garantia é de um ano).</li><li>A garantia cobre quaisquer defeitos causados por falhas mecânicas ou elétricas. A cobertura é limitada e não inclui nenhum dano acidental ao produto comprado. Os clientes que desejam proteger os produtos que compram contra danos do uso cotidiano devem investir em uma garantia estendida. As garantias estendidas duram de dois a dez anos, dependendo da categoria do produto. Elas também têm cobertura maior e cobrem incidentes diários como quedas, derramamentos e manchas.</li></ul> |
| Item de garantia | Um *item de garantia* é um item da garantia estendida vendido para um item com garantia. Um exemplo é um plano de proteção contra acidentes de dois anos para laptops. |
| Item com garantia | Um *item com garantia* é um produto serializado para o qual a garantia é vendida. Por exemplo, um laptop é um item com garantia para o qual as garantias estendidas de dois e de três anos são vendidas. |
| Grupo de garantias | Um *grupo de garantias* é uma relação entre itens de garantia e itens com garantia. O PDV usa grupos de garantia para determinar quais itens de garantia os representantes de vendas devem receber avisos para adicionar quando um item com garantia é adicionado ao carrinho do cliente. |
| Política de garantia | Uma *política de garantia* é uma entidade criada no Commerce quando uma política de garantia é vendida. Uma política de garantia inclui informações como as datas de início e de término do item de garantia comprado, termos e condições, e o número de série do produto garantido. Os números da política de garantia podem ser compartilhados com clientes para que eles tenham uma referência para o item de garantia estendida que compraram. |

## <a name="create-a-warranty-item"></a>Criar um item de garantia

Para criar um item de garantia no Commerce, siga estas etapas:

1. Acesse **Varejo e comércio \> Produtos e categorias \> Produtos**.
1. Selecione **Criar** para criar um item de garantia.
1. Na caixa de diálogo **Novo produto**, no campo **Tipo de produto**, selecione **Serviço**.
1. No campo **Subtipo do produto**, selecione **Produto**.
1. No campo **Tipo de serviço do produto**, selecione **Serviço**.
1. No campo **Nome do produto**, insira o nome do produto.
1. No campo **Categoria de varejo**, selecione um valor na caixa de diálogo suspensa e selecione **OK**.
1. No campo **Número do produto**, insira o número do produto.
1. Selecione **OK**.
1. Na página **Detalhes do produto**, na FastTab **Garantia**, defina os campos **Unidade de tempo** e **Duração**.

    | Nome do campo | Alíquota | descrição |
    |------------|-------|-------------|
    | Unidade de tempo | **Dia(s)**, **Semana(s)**, **Mês(e)s** ou **Ano(s)** | Esse campo especifica a unidade de tempo usada para a garantia. |
    | Período | Um valor inteiro positivo | Este campo especifica a duração da garantia na unidade de tempo selecionada. |

    Por exemplo, para uma garantia de dois anos, defina o campo **Unidade de tempo** como **Ano(s)** e o campo **Duração** como **2**. Como alternativa, defina o campo **Unidade de tempo** como **Mês(es)** e o campo **Duração** como **24**, conforme mostrado na ilustração a seguir.

    ![Página de detalhes do produto de um item de garantia](./media/ew-time-properties.png)

1. Selecione **Salvar** para salvar o item de garantia.
1. Libere o produto com garantia para a empresa para que ele possa ser vendido. Para obter mais informações, consulte [Configurar produtos de varejo](set-up-retail-products.md).
1. Na página **Detalhes do produto liberado**, na FastTab **Garantia**, defina os campos **Base da faixa de preço**, **Limite inferior** e **Limite superior**.

    | Nome do campo | Alíquota | descrição |
    |------------|-------|-------------|
    | Base do intervalo de preços | **Nenhum**, **Preço base** ou **Preço de venda** | <ul><li>**Nenhum** — os valores de **Limite inferior** e **Limite superior** das faixas de preço não são aplicáveis.</li><li>**Preço base** — uma determinada garantia será aplicável se o preço base (ou seja, o preço sem descontos) do item garantido estiver entre os valores de **Limite inferior** e de **Limite superior** especificados aqui, com base no preço do item com garantia.</li><li>**Preço de venda** — esse valor está reservado para uso futuro.</li></ul> |
    | Limite inferior, limite superior | Um valor inteiro positivo | Esses campos definem os limites de preço superior e inferior do item de garantia e como o item de garantia atual é aplicável ao item com garantia. Esses limites podem estar baseados no preço base do item de garantia, também conhecido como \[MSRP\] (manufacturer's suggested retail price — preço de varejo sugerido do fabricante). Se o campo **Base da faixa de preço** for definido como **Preço base**, somente um item com garantia (produto) com um preço base entre os valores de **Limite inferior** e **Limite superior** disparará um aviso no PDV para adicionar o item de garantia. |

    Por exemplo, a ilustração a seguir mostra o campo **Base da faixa de preço** definido como **Preço base**, o campo **Limite inferior** definido como US$ 500 e o campo **Limite superior** definido como US$ 1.000.
    
    ![Página de detalhes do produto liberado de um item de garantia](./media/ew-release-product-details.png)

1. Classifique o item de garantia para o canal em que ele será vendido. Para saber mais, consulte [Configurar classificações](set-up-assortments.md).

### <a name="example"></a>Exemplo

Um item com garantia de laptop (produto) tem um preço base de US$ 999 e há dois itens de garantia de laptop:

- Garantia\_1 tem um limite inferior de US$ 500 e um limite superior de US$ 1.000, e o campo **Base da faixa de preço** é definido como **Preço base**.
- Garantia\_2 tem um limite inferior de US$ 1.001 e um limite superior de US$ 2.000, e o campo **Base da faixa de preço** é definido como **Preço base**.

Nesse caso, quando o item com garantia de laptop é adicionado ao carrinho de um cliente, um aviso para adicionar a Garantia\_1 será mostrado no PDV, porque o preço do laptop está entre os limites inferior e superior da Garantia\_1.

> [!NOTE]
> Neste exemplo, se você quiser que os avisos sejam mostrados para a Garantia\_1 e a Garantia\_2, independentemente do preço do item que pode ser garantido, defina o campo **Base da faixa de preço** como **Nenhum**.

## <a name="configure-channel-specific-settings"></a>Definir configurações específicas do canal

As configurações específicas do canal permitem que você especifique se um aviso para adicionar um item de garantia deve ser mostrada no PDV quando um item com garantia é adicionado ao carrinho do cliente.

Para definir configurações específicas do canal no Commerce, siga estas etapas:

1. Acesse **Varejo e Comércio \> Produtos e categorias \> Garantia \> Configurações de garantias**.
1. Na guia **Canal específico**, na coluna **Aviso para garantia** de seu canal, siga uma destas etapas:

    - Marque a caixa de seleção se um aviso para item de garantia deverá ser exibido no PDV quando o item com garantia for adicionado ao carrinho.
    - Desmarque a caixa de seleção se nenhum aviso para item de garantia deve ser exibido no PDV quando o item com garantia for adicionado ao carrinho.

1. Execute o trabalho **1070** para sincronizar os dados no canal.

## <a name="configure-a-number-sequence-for-warranty-policies"></a>Configurar uma sequência numérica para as políticas de garantia

Cada política de garantia é identificada de forma exclusiva por um número de política de garantia gerado por uma sequência numérica. Para obter mais informações sobre sequências numéricas, consulte [Visão geral de sequências numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Para configurar uma sequência numérica para as políticas de garantia no Commerce, siga estas etapas:

1. Acesse **Varejo e Comércio \> Produtos e categorias \> Garantia \> Configurações de garantias**.
1. Na guia **Sequências numéricas**, na linha da referência da **Política de garantia**, insira ou selecione um valor no campo **Código da sequência numérica**.

## <a name="set-up-a-warranty-group"></a>Configurar um grupo de garantias

Um grupo de garantias é uma relação entre itens de garantia e itens com garantia. O PDV usa grupos de garantia para determinar quais itens de garantia os representantes de vendas devem receber avisos para adicionar quando um item com garantia é adicionado ao carrinho do cliente.

Para configurar um grupo de garantias no Commerce, siga estas etapas:

1. Acesse **Retail e Commerce \> Produtos e categorias \> Garantia \> Grupos de garantias**.
1. Selecione **Criar** para criar um grupo de garantias.
1. No campo **Nome**, insira um nome para o novo grupo.
1. Na FastTab **Geral**, no campo **Descrição**, insira uma descrição do grupo.
1. Na FastTab **Produtos da garantia**, selecione **Adicionar linha** para adicionar um item de garantia.
1. No campo **Ordem de exibição**, insira um número para classificar o grupo de garantias no PDV. O PDV mostrará os itens de garantia na ordem de classificação crescente no aviso de garantia.
1. Na FastTab **Produtos com garantia**, selecione **Adicionar linha** para adicionar produtos com garantia.
1. Se o item de garantia for aplicável a uma categoria inteira de itens com garantia (produtos), selecione a categoria no campo **Categoria**. Se o item de garantia for aplicável a um item com garantia (produto) específico, selecione o produto no campo **Produto**.
1. Na FastTab **Canais aplicáveis**, selecione **Adicionar linha** para adicionar o canal em que você deseja vender o item de garantia.
1. Selecione **Salvar** para salvar a configuração.
1. Selecione **Publicar** para publicar o grupo de garantias.
1. Execute o trabalho **1040** para sincronizar os dados no canal.

## <a name="sell-warranty-items-at-the-pos"></a>Vender itens de garantia no PDV

Duas operações de PDV permitem que representantes de vendas vendam itens de garantia durante o fluxo de trabalho para compras de clientes:

- **Adicionar garantia** — essa operação dispara um aviso que mostra as garantias aplicáveis a um item com garantia selecionado no carrinho.
- **Adicionar garantia à transação existente** — essa operação permite que os representantes de vendas vendam as garantias de itens com garantia que foram vendidos anteriormente. Os associados de vendas podem encontrar a transação original de um item com garantia inserindo o número do recibo da transação.

A ilustração a seguir mostra um exemplo de uma página de terminal de PDV com um aviso para adicionar um item de garantia para a compra atual de um item com garantia.

![Exemplo de um aviso para adicionar um item de garantia para a compra atual](./media/ew-sell-warranty.png)

A ilustração a seguir mostra um exemplo do recurso para adicionar um item de garantia para um item com garantia que foi vendido anteriormente.

![Exemplo do recurso para adicionar um item de garantia para um item com garantia vendido anteriormente](./media/ew-add-warranty-existing.png)

## <a name="process-warranty-transactions"></a>Processar transações de garantia

Quando as garantias são vendidas em transações cash and carry, depois que as transações são lançadas na sede do Commerce, os usuários comerciais podem executar o trabalho **Processar transações de garantia** para processar as transações de garantia e criar políticas de garantia.

Para processar as transações de garantia na sede do Commerce, siga estas etapas:

1. Acesse **Varejo e Comércio \> Produtos e categorias \> Garantia \> Processar transações de garantia**.
1. Na caixa de diálogo **Escolher nós da organização**, no campo **Hierarquia organizacional**, selecione um valor.
1. Na lista **Nós da organização disponíveis**, selecione uma loja individual ou, se desejar criar o trabalho em lotes para um grupo de armazenamentos, selecione um nó.
1. Selecione o botão de seta para a direita para adicionar sua seleção à lista **Nós da organização selecionados**.
1. Selecione a guia **Executar em segundo plano**.
1. Defina a opção **Processamento em lotes** como **Sim** e selecione **Recorrência**.
1. Na caixa de diálogo **Definir recorrência**, no campo **Data de início**, selecione ou insira uma data de início para a recorrência.
1. No campo **Hora de início**, selecione ou insira uma hora de início para a recorrência.
1. Siga uma destas etapas:

    - Selecione a opção **Sem data de término** caso a recorrência nunca deva terminar.
    - Selecione a opção **Terminar após** se a recorrência terminar após um número específico de execuções. Se você selecionar esta opção, insira o número de execuções.
    - Selecione a opção **Terminar em** caso a recorrência deva terminar em uma data específica. Se você selecionar essa opção, selecione ou insira a data.

1. Selecione **OK**.
1. Selecione **OK**.

## <a name="warranty-policies"></a>Políticas de garantia

Quando uma garantia estendida é vendida, uma entidade de política de garantia é criada automaticamente. Os números da política de garantia podem ser compartilhados com os clientes para que eles tenham uma referência para o item de garantia que compraram. As propriedades das políticas de garantia incluem a data de início e a data de vencimento efetivas da garantia, os termos e condições e o número de série do item com garantia para o qual a garantia foi vendida.

> [!NOTE]
> As propriedades da política de garantia são geradas automaticamente quando as entidades da política de garantia são criadas. No momento, elas não podem ser configuradas ou editadas manualmente.

A tabela a seguir descreve as propriedades da política de garantia e seus valores. Na sede do Commerce, a tabela do banco de dados é chamada WARRANTYPOLICY.

| Nome da propriedade | Alíquota | descrição |
|---------------|-------|-------------|
| PolicyNumber | Uma cadeia de caracteres (máximo de 20 caracteres) | O número da política de garantia |
| WarrantiedItemId | Uma cadeia de caracteres (máximo de 20 caracteres) | A ID do item com garantia |
| WarrantiedInventoryLotId | Uma cadeia de caracteres (máximo de 20 caracteres) | A ID do lote de estoque do item com garantia |
| WarrantiedSerialNumber | Uma cadeia de caracteres (máximo de 20 caracteres) | O número de série do item com garantia |
| WarrantiedFulfilledDate | Uma data | A data de atendimento do item com garantia |
| WarrantyItemId | Uma cadeia de caracteres (máximo de 20 caracteres) | A ID do item de garantia |
| WarrantyInventoryLotId | Uma cadeia de caracteres (máximo de 20 caracteres) | A ID do lote de estoque do item de garantia |
| WarrantySalesDate | Uma data | A data de venda do item de garantia |
| WarrantyEffectiveDate | Uma data | A data de início efetiva da política de garantia |
| WarrantyExpirationDate | Uma data | A data de vencimento da política de garantia |
| CustAccount | Uma cadeia de caracteres (máximo de 20 caracteres) | O número da conta do cliente |
| Status | **Criado**, **Anulado**, **Em vigor** ou **Expirado** | O status da política de garantia |
| Anotações | Uma cadeia de caracteres (um máximo de 255 caracteres) | Observações sobre a política de garantia, como termos e condições |

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes

**Por que não vejo um aviso de garantia no PDV?**

Verifique se o item de garantia está classificado para o canal. Verifique também se o grupo de garantias está configurado para incluir o canal relevante.

**Quando tento adicionar uma garantia a uma transação existente e inserir o número do recibo da ordem do cliente, por que não vejo nenhum item de linha de transação?**

Os recibos só poderão ser encontrados se um trabalho pull (trabalho P) for executado para carregar os recibos na sede do Commerce. Para executar o trabalho P, acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**, selecione o trabalho **P-0001** e selecione **Executar agora**.

**Por que o recurso de garantia é aplicável somente a produtos serializados?**

Uma garantia é um serviço que é fornecido para um produto exclusivo específico. No Dynamics 365, um produto pode ser identificado exclusivamente por um número de série.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar produtos de varejo](set-up-retail-products.md)

[Configurar sortimentos](set-up-assortments.md)

[Visão geral de sequências numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)
