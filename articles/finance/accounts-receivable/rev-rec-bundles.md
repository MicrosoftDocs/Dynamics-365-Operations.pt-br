---
title: Pacotes de reconhecimento de receita
description: Este tópico descreve a funcionalidade de pacote incluída no recurso de reconhecimento de receita em contas a receber. Um pacote inclui um item pai e vários itens de componente.
author: kweekley
ms.date: 01/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 62a4d7f36ad0b36edeaec75e9b670e2aad143703
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725809"
---
# <a name="revenue-recognition-bundles"></a>Pacotes de reconhecimento de receita

[!include [banner](../includes/banner.md)]

Este tópico descreve a funcionalidade de pacote incluída no recurso de reconhecimento de receita em contas a receber. Um pacote inclui um item pai e vários itens de componente. O item pai é inserido em uma ordem de venda para que a entrada de ordem seja mais eficiente. No entanto, ele depois é detalhado em itens de componente. Os documentos internos, como a guia de remessa, listarão os itens de componente. No entanto, os documentos externos mostrarão somente o item pai.

> [!NOTE]
> Os canais do Microsoft Dynamics 365 Commerce, como online, PDV (ponto de venda) e call centers, não oferecem suporte ao reconhecimento de receita (incluindo o funcionalidade de pacote). Isso também inclui a solução Prospect to cash para Dynamics 365 Supply Chain Management e Dynamics 365 Sales. Os itens configurados para usar o reconhecimento de receita não devem ser adicionados a ordens ou transações criadas em canais do Commerce ou na solução Prospect to cash.

Para configurar pacotes, insira as chaves de configuração para o reconhecimento de receita. No entanto, você poderá usar os pacotes mesmo se o reconhecimento de receita não estiver configurado. Da mesma maneira, você poderá usar o reconhecimento de receita se os pacotes não estiverem configurados. Se o reconhecimento de receita estiver configurado, os itens de componente determinarão o preço e a agenda de receita usados para o reconhecimento ou o deferimento da receita quando uma ordem de venda for faturada.

A configuração de pacotes usa a funcionalidade de lista de materiais (BOM). Para obter informações sobre como configurar um item de pacote, consulte [Configuração de reconhecimento de receita](revenue-recognition-setup.md). Se o item pai for sinalizado como um pacote, ele será tratado de forma diferente de outros itens da BOM. Veja esta lista das diferenças:

- Os pacotes devem ser detalhados pela confirmação da ordem de venda, selecionando **Confirmar ordem de venda** na guia **Venda** do Painel de Ações na página da ordem de venda. Os itens do pacote nunca devem ser detalhados selecionando **Linha da BOM** em **Detalhar** no menu **Linha da ordem de venda** na FastTab **Linhas da ordem de venda**. Caso contrário, o item será tratado como uma BOM, não como um pacote.
- Uma ordem de venda que contém um item de pacote precisa ser confirmada antes da criação da guia de remessa ou da fatura.
- Quando um pacote é detalhado pela confirmação da ordem de venda, o item pai é cancelado e o preço unitário e os descontos são alocados para os itens de componente do pacote.
- A soma dos itens de componente precisa ser sempre igual ao preço do item pai. Portanto, há limitações nos campos que podem ser atualizados ou alterados para itens de componente. Por exemplo, não é possível alterar manualmente o preço unitário. Também não é possível alterá-lo indiretamente com a implementação de um novo contrato de preço. Para evitar um novo contrato de preço, não é possível alterar as dimensões de estoque nos itens de componente.
- Quando é impresso um documento externo, como a confirmação ou a fatura da ordem de venda, é impresso o item pai, e não os itens de componente.

## <a name="bundles-on-sales-orders"></a>Pacotes em ordens de venda

A empresa de demonstração USMF inclui a configuração de pacote a seguir. Observe que toda a configuração para reconhecimento de receita, como a configuração de agenda de receita, foi removida dos itens incluídos neste cenário.

**Item pai:** pacote de laptop

- **Item de componente:** uma quantidade de 1 unidade do item 1000
- **Item de componente:** uma quantidade de 1 unidade do item S0021
- **Item de componente:** uma quantidade de 1 unidade do item Suporte

O *preço base de venda* dos itens de componente é uma parte essencial da configuração dos componentes. O preço base de venda é definido na FastTab **Venda** de um item. Ele é usado para calcular o fator de alocação quando o preço unitário do item pai é alocado aos itens de componente. Os preços de venda do contrato comercial nunca são usados para essa finalidade.

Os preços base de venda a seguir são definidos para os itens de componente:

- **1000:** US$ 1.900
- **S0021:** US$ 150
- **Suporte:** US$ 500

Uma ordem de venda é inserida para o cliente US-004, Cave Wholesales. A única linha inserida é para o item Pacote de laptop. O preço unitário padrão da linha pai pode ser obtido de vários locais, como o contrato comercial ou o preço base de venda. Neste exemplo, o valor US$ 2.300 foi inserido manualmente como o preço unitário.

[![Item Pacote de laptop em uma ordem de venda.](./media/bundle-01.png)](./media/bundle-01.png)

Como a ordem de venda contém um pacote, ela deverá ser confirmada. A caixa de diálogo de confirmação mostra os componentes do pacote.

[![Caixa de diálogo Confirmar ordem de venda que mostra os itens de componente.](./media/bundle-02.png)](./media/bundle-02.png)

No entanto, o relatório de confirmação impressa mostrará somente o item pai do pacote, pois esse relatório é o documento externo para o cliente.

[![Relatório de confirmação que mostra somente o item pai.](./media/bundle-03.png)](./media/bundle-03.png)

Depois que a ordem de venda for confirmada, o item pai ainda será mostrado nela, mas com o status alterado para **Cancelado**. Além disso, o valor líquido é acompanhado no campo **Valor líquido do pacote**. Esse valor é obrigatório para imprimir a fatura, porque ela mostra o item pai, não os itens de componente.

A soma dos itens de componente deve ser igual ao **Valor líquido do pacote** do item pai, pois esse é o valor apresentado ao cliente na fatura impressa. Para garantir que a fatura corresponda aos valores lançados na contabilidade, as edições nos itens de componente são limitadas. Por exemplo, não é possível alterar o local e o depósito, pois essas alterações podem desencadear uma alteração de preço com base em um contrato comercial.

O preço unitário da linha do item pai é alocado aos componentes da seguinte maneira:

**Total dos preços base de venda dos componentes:** US$ 1.900 + US$ 500 + US$ 150 = US$ 2.550

- **Componente 1:** US$ 2.300 × (1.900 ÷ 2.550) = US$ 1.713,73
- **Componente 2:** US$ 2.300 × (500 ÷ 2.550) = US$ 450,98
- **Componente 3:** US$ 2.300 × (150 ÷ 2.550) = US$ 135,29

A soma dos componentes precisa ser igual a US$ 2.300, e é (US$ 1.713,73 + US$ 450,98 + US$ 135,29 = US$ 2.300).

Se forem necessárias alterações para todos os itens de componente, o item pai poderá ser removido. Nesse caso, os itens de componente também serão removidos. Então, será possível adicionar o item pai novamente e concluir as edições necessárias antes da confirmação da ordem de venda.

[![Item do pacote que inclui alterações nos itens de componente.](./media/bundle-04.png)](./media/bundle-04.png)

Quando a ordem de venda for separada e embalada, os documentos incluirão somente os componentes do pacote. A guia de remessa e a fatura devem incluir um pacote completo. Caso contrário, elas não poderão ser lançadas. Por exemplo, a caixa de diálogo mostra três itens de componente. Se tentar excluir um deles, você receberá uma mensagem de erro informando que todos os produtos do pacote devem ser enviados antes do faturamento.

Um pacote deve ser enviado e faturado como um pacote completo. Por exemplo, se você alterar a quantidade do item 1000 para 4, mas deixar a quantidade dos outros itens de componente como 5, a guia de remessa e a fatura não poderão ser lançadas.

Um valor parcial poderá ser enviado e faturado somente se a quantidade for reduzida para todos os componentes do pacote. Por exemplo, é inserida a quantidade de 5 unidades do item Pacote de laptop em uma ordem de venda. Depois que a ordem de venda é confirmada, os três itens de componente são mostrados na ordem de venda, cada um com a quantidade de 5 unidades. Por padrão, durante o envio e o faturamento, será definida a quantidade de 5 unidades para cada componente. No entanto, você poderá reduzir a quantidade para 3 unidades para os três itens de componente. Nesse caso, três pacotes completos serão enviados e faturados. Os dois itens de pacote restantes (2 unidades de cada um dos três itens de componente) poderão ser enviados e faturados posteriormente.

A etapa final é faturar a ordem de venda. Durante o faturamento, a caixa de diálogo Fatura mostrará os itens de componente.

[![Caixa de diálogo Fatura que mostra os itens de componente.](./media/bundle-06.png)](./media/bundle-06.png)

No entanto, a fatura impressa mostrará apenas o item pai.
 
[![Fatura impressa que mostra somente o item pai.](./media/bundle-07.png)](./media/bundle-07.png)

O diário de faturas criado após o lançamento não inclui o item pai do pacote, pois esse item tem o status de **Cancelado**.

[![Diário de faturas que não inclui o item pai.](./media/bundle-08.png)](./media/bundle-08.png)

É importante que o diário de faturas não inclua o item pai do pacote, pois todos os processos executados após o lançamento da fatura baseiam-se nesse diário de faturas. Por exemplo, se você criar uma nota de crédito na guia **Venda** no Painel de Ações, ela incluirá os itens de componente, mas não o item pai.

[![Nota de crédito que mostra os itens de componente, mas não o item pai.](./media/bundle-09.png)](./media/bundle-09.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
