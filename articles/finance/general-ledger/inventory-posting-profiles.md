---
title: Perfis de lançamento de estoque
description: Este artigo oferece uma visão geral dos perfis de lançamento de estoque.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cae5b39ef8e6e153fe522dee1874deae2a2cb86e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901332"
---
# <a name="inventory-posting-profiles"></a>Perfis de lançamento de estoque

[!include [banner](../includes/banner.md)]

Os perfis de lançamento de estoque controlam o lançamento de transações de estoque do razão auxiliar na contabilidade. As transações de estoque do razão auxiliar podem ser geradas a partir de vários módulos, incluindo **Vendas e marketing**, **Aquisição e fornecimento**, **Controle de produção** e muito mais. As transações de estoque do razão auxiliar podem ser lançadas sempre que um item seja usado em uma ordem de venda ou de compra. 

Transações de estoque do razão auxiliar adicionais podem ser lançadas:
- Toda vez que um documento for atualizado.
- Quando uma guia de remessa de ordem de venda ou fatura for lançada.
- Quando um recebimento de produto da ordem de compra ou fatura for gerado.

Para obter mais informações, acesse Transações de estoque do razão auxiliar.

## <a name="inventory-transaction-overview"></a>Visão geral de transação de estoque

Cada transação de estoque do razão auxiliar contém:
 - Quantidade 
 - Preço 
 - Site 
 - Depósito 
 - Localização 

As transações de estoque do razão auxiliar criam duas entradas na contabilidade por meio do lançamento físico e financeiro. Para obter mais informações, acesse [Atualizações físicas e financeiras](/supply-chain/cost-management/physical-financial-updates.md).
Veja a seguir um exemplo de uma ordem de compra com três linhas. Para esse exemplo, presuma que a ordem de compra inteira é para um único local e depósito. Cada ordem de compra tem um registro InventTrans único relacionado, também conhecido como uma transação de estoque, e cada linha é para uma quantidade de 10. O diagrama a seguir mostra o relacionamento de um cabeçalho de ordem de compra com três linhas da ordem de compra, cada uma com um registro InventTrans.

![Diagrama do relacionamento para uma ordem de compra com três linhas, cada uma com um registro InventTrans.](./media/InventTransRelationship.PNG)

Uma quantidade de cinco é recebida na primeira linha da ordem de compra. A quantidade total para a segunda linha e nenhuma quantidade recebida na terceira linha da ordem de compra. Agora há uma segunda transação de estoque relacionada à primeira linha da ordem de compra. A transação para a segunda linha da ordem de compra será atualizada para **Recebido** e terceira transação permanecerá a mesma. O diagrama a seguir mostra o relacionamento como registro InventTrans adicional para a linha 1 da ordem de compra.

![Diagrama do relacionamento para uma ordem de compra com três linhas. Uma linha é recebida parcialmente e mostra dois registros InventTrans.](./media/InventTransRelationshipPartialReceipt.PNG)

Nesse exemplo, um comprovante será lançado na contabilidade. Ele é o comprovante físico. O grupo de modelos de item é configurado para lançar estoque físico e todos os itens usam o mesmo grupo de modelos de item. O perfil de lançamento de estoque está usando um único conjunto de contas principais. Um único comprovante será criado, e o registro InventTrans vinculará InventTrans 1 e InventTrans 2 ao mesmo comprovante.

Em seguida, uma fatura é recebida da quantidade que foi recebida nas linhas 1 e 2. Outro comprovante será criado na contabilidade. Ele é o comprovante final. O grupo de modelos de item é configurado para lançar estoque financeiro. O novo segundo comprovante está relacionado a InventTrans 1 e InventTrans 2.

Dependendo do modelo de custos, pode haver um terceiro lançamento na contabilidade para suas transações de estoque do razão auxiliar relacionadas ao fechamento e liquidação do estoque. Para obter mais informações, acesse [Fechamento de estoque](/supply-chain/cost-management/inventory-close.md). É possível exibir os detalhes de todas as transações de estoque acessando **Gerenciamento de estoque** > **Consultas e relatório** > **Transações**.

>[!Important]
> As transações de estoque serão divididas para cada combinação de dimensões de estoque e para cada atualização parcial. Isso foi mostrado no exemplo anterior de atualizações parciais.

### <a name="split-inventory-based-on-inventory-dimension-example"></a>Exemplo de estoque dividido com base na dimensão do estoque

A linha 3 da ordem de compra no exemplo é um item serializado. Dez números de série são registrados para a ordem de compra durante o processo de recebimento. A transação de estoque será dividida em 10 transações de estoque. O diagrama a seguir mostra o relacionamento e as transações de estoque adicionais, cada uma com seu próprio número de série relacionado à linha 3 da ordem de compra.

![Diagrama do relacionamento para uma ordem de compra com três linhas. Uma linha é serializada e mostra registros InventTrans adicionais](./media/InventTransRelationshipSerialNumber.PNG)

No exemplo acima, se cada número de série for recebido em um único recebimento de produto, um comprovante adicional será criado. O campo do comprovante físico será vinculado a cada número de série. O mesmo vale para a atualização financeira quando você emite a fatura da ordem de compra.

## <a name="inventory-transactions"></a>Transações de estoque

É possível exibir as transações de estoque na página **Transações de estoque**, em **Gerenciamento de estoque e depósito** ou **Gerenciamento de custos**. Também é possível exibir as transações de estoque relacionadas a uma linha específica do documento de origem, como uma linha da ordem de compra ou linha da ordem de venda, selecionando **Estoque**, e em seguida, **Transações**. 

A página **Transações de estoque** contém os seguintes campos:

| Campo            | Descrição                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Número do item      | O número do item relacionado à transação.                                                                  |
| Data física    | A data em que o estoque chega ao depósito, sai do depósito, é consumido na produção ou é produzido. Por exemplo, a data de lançamento
no lançamento da guia de remessa de uma ordem de venda ou no lançamento do recebimento de produtos de uma ordem de compra.                             |
| Data financeira   | A data em que a transação de estoque é fechada e o custo é registrado na contabilidade. Por exemplo, a data de lançamento na geração da fatura 
de uma ordem de compra de uma ordem de venda. Atualizações ao documento de referência não são permitidas depois que a data financeira for preenchida. |
| Demonstrativo        | Indica a origem da transação e o tipo de documento que é exibido no campo **Número**. Por exemplo, o recebimento de uma ordem de venda, ordem de compra ou ordem de transferência.                                                 |
| Número           | Indica a ID da referência de uma transação. Por exemplo, se o campo **Referência** indica a ordem de venda, o campo **Número** indica o número da ordem de venda.                                                       |
| Recebimento (status) | Para transações de estoque que são recebimentos, esse campo indica o status do recebimento. Por exemplo, uma ordem de compra é um recebimento, e o status pode ser **Encomendado** ou **Comprado**.                                                            |
| Saída (status)   | Para transações de estoque que são saídas, esse campo indica o status da saída. Por exemplo, uma ordem de venda é uma saída, e o status pode ser **Na ordem** ou **Vendido**.                         |
| Quantidade         | A quantidade da transação de estoque. Números positivos são usados para recebimentos de estoque, enquanto números negativos são usados para saídas de estoque.                                                                                                                          |
| Unidade             | A unidade de medida na qual a quantidade é expressa.                                                                                   |
| Quantidade em PV      | A quantidade de peso variável da transação. Para obter mais informações, acesse [Sobre itens de peso variável](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.).       |
| Unidade de PV          | A unidade de medida do peso variável na qual a quantidade de peso variável é expressa.                                                         |
| Valor de custo      | O custo final da transação de estoque. Esse campo é preenchido quando uma transação é atualizada financeiramente. Dependendo da metodologia de custos, o processo de fechamento e ajuste de estoque pode atualizar esse campo.                            |

## <a name="inventory-status"></a>Status do estoque

Cada transação de estoque tem um status que é exibido no campo **Recebimento** ou **Saída**. O campo usado depende do tipo das transações de estoque. Recebimentos são transações que aumentam o estoque. Por exemplo, uma ordem de compra com uma quantidade positiva ou uma devolução de ordem de venda com uma quantidade negativa. Saídas são transações que diminuem o estoque. Por exemplo, uma ordem de venda com uma quantidade positiva ou uma devolução de ordem de compra com uma quantidade negativa.

### <a name="receipt-status"></a>Status do recebimento

A tabela a seguir descreve os status de **Recebimento**.

| **Status do recebimento** | **Descrição**       |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Encomenda feita            | O status inicial de qualquer transação de estoque que representa um recebimento. Isso inclui as ordens de compra com uma quantidade positiva, ordens de produção ou devoluções de ordem de venda com uma quantidade negativa.                                                   |
| Registrado         | Esse status é usado quando um processo de recebimento em duas etapas está em vigor ou quando a entrada do item é usada para indicar que o produto chegou. Ele é usado quando um lote ou números de série são "alocados" ou registrados na ordem. Para obter mais informações sobre a entrada de itens, acesse [Visão geral de entrada](/supply-chain/inventory/arrival-overview.md). |
| Recebimento           | Esse status é usado quando uma transação é atualizada fisicamente. Para uma ordem de compra, isso é quando o recebimento do produto é lançado. Para uma devolução de ordem de venda, isso é quando a guia de remessa é lançada.                                                                            |
| Comprado          | Esse status é usado quando uma transação é atualizada financeiramente. Para uma ordem de compra ou devolução de ordem de venda, isso é quando a fatura é gerada.                                                                                             |

### <a name="issue-status"></a>Status da saída

A tabela a seguir descreve os status de **Saída**.

| **Status da saída**  | **Descrição**            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| Em ordem          | O status inicial de qualquer transação de estoque que representa uma saída. Isso inclui as ordens de venda com uma quantidade positiva, ordens de produção, linhas da BOM ou da fórmula ou devoluções de ordem de compra com uma quantidade negativa.                                             |
| Qtd. encomendada  | O status do estoque indica se o estoque foi reservado em relação a uma ordem que foi criada, mas que ainda não foi recebida fisicamente no estoque. Quando estoque é recebido, o status será atualizado automaticamente para **Reserva física**. Para obter mais informações sobre reservas, consulte [Reservar quantidades em estoque](/supply-chain/inventory/reserve-inventory-quantities.md). |
| Qtd. reservada | O status indica que o estoque foi alocado ou reservado em relação a uma ordem específica. Quando o estoque é reservado, ele não fica fisicamente disponível para outras ordens.                                 |
| Separada         | Isso indica que o estoque foi separado no depósito. O estoque anda está fisicamente no depósito, ele não foi removido, mas não está disponível para outras ordens.  |
| Deduzido          | Esse status é usado quando uma transação é atualizada fisicamente. Para uma ordem de venda, isso é quando a guia de remessa é lançada. para uma ordem de compra, isso é quando o recebimento dos produtos é lançado.                                                                      |
| Vendido              | Esse é o status usado quando uma transação é atualizada financeiramente. Para uma ordem de compra ou de ordem de venda, isso é quando a fatura é gerada.|

Para obter mais informações sobre as transações de estoque, consulte [Detalhes das transações de estoque](/supply-chain/inventory/inventory-transactions-details.md).

## <a name="configure-an-inventory-posting-profile"></a>Configurar um perfil de lançamento de estoque

Para configurar um perfil de lançamento de estoque, siga estas etapas:

1.  Abra **Gerenciamento de estoque** > **Configuração** > **Lançamento** > **Lançamento**.
2.  Selecione a guia para o tipo de transação. Por exemplo: selecione **Ordem de compra**.
3.  Selecione o botão de opção para o tipo de lançamento. Por exemplo: selecione **Despesas de compra para despesa**.
4.  Selecione **Novo**.
5.  No campo **Código do item**, selecione uma opção para **Tabela**, **Grupo**, **Todos** ou **Categoria**. Por exemplo, para configurar um perfil de lançamento para um grupo de itens específico, selecione **Grupo**.
     - Se você tiver selecionado **Tabela** na etapa 5, selecione o Número de item específico para o perfil de lançamento no campo **Relação de item**.
     - Se você tiver selecionado **Grupo** na etapa 5, selecione o **Grupo de itens** para o perfil de lançamento no campo **Relação de item** .
     - Se você tiver selecionado **Todos** na etapa 5, o campo **Relação de item** ficará em branco.
     - Se você tiver selecionado **Categoria** na etapa 5, o campo **Relação de item** ficará em branco. Use o campo **Relação de categoria** para selecionar a categoria à qual o perfil de lançamento se aplica.

6.  No campo **Código de conta**, selecione uma opção para **Tabela**, **Grupo** ou **Todos**. Por exemplo, para aplicar o perfil de lançamento a todos os fornecedores, selecione **Todos**.
     - Se você tiver selecionado **Tabela** na etapa 5, selecione o número de fornecedor específico para o perfil de lançamento no campo **Relação de conta**.
     - Se você tiver selecionado **Grupo** na etapa 5, selecione o grupo de fornecedores para o perfil de lançamento no campo **Relação de conta**.
     - Se você tiver selecionado **Todos** na etapa 5, o campo **Relação de conta** ficará em branco.

7.  Para associar um determinado grupo de impostos que tenha o tipo de lançamento selecionado, escolha um **Grupo de impostos**. Se este campo ficar em branco, o tipo de lançamento se aplicará a todos os grupos de impostos existentes. O lançamento especificado para grupos de impostos aplica-se somente a transações feitas para vendas e compras.
8.  Especifique o número da conta para lançar o tipo de conta no campo **Conta principal**. Se ainda não tiver criado um número de conta para ser usado como o tipo contabilidade, você poderá criar uma conta. Você cria uma conta da página **Detalhes da conta principal** na Contabilidade.

## <a name="additional-resources"></a>Recursos adicionais

Cada guia na página **Perfil de lançamento de estoque** está relacionada a um razão auxiliar no Dynamics 365 Supply Chain Management. Para obter mais informações, acesse:
-   [Lançando de ordem de venda](sales-order-posting.md)
-   [Lançamento de ordem de compra](purchase-order-posting.md)
-   [Lançamento de estoque](inventory-posting.md)
-   [Lançamento de controle de produção](production-posting.md)
-   [Lançamento de variação de custo padrão](standard-cost-variance-posting.md)
