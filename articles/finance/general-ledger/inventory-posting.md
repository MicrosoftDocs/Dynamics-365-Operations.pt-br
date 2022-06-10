---
title: Lançamento de estoque
description: Este tópico explica a guia Lançamento de estoque na página Perfil de lançamento de estoque.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 464ffccd658003271b517038f430914fd5d8d50e
ms.sourcegitcommit: 6744cc2971047e3e568100eae338885104c38294
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2022
ms.locfileid: "8783361"
---
# <a name="inventory-posting"></a>Lançamento de estoque

A guia **Estoque** na página **Perfis de lançamento de estoque** é usada para controlar como as transações de estoque são lançadas na contabilidade. Transações de estoque são transações que não são criadas a partir de ordens de compra, ordens de venda ou ordens de produção. Elas lançam automaticamente atualizações físicas e financeiras no estoque simultaneamente. Uma exceção são as ordens de transferência que separam atualizações físicas e financeiras quando você envia e recebe o estoque.

A tabela a seguir mostra alguns exemplos de transações de estoque.

| Tipo de transação | Recebimento ou saída | Lançamento físico, lançamento financeiro ou ambos | Descrição |
|---|---|---|---|
| Movimentação | Ambos | Ambos | <p>Um diário de movimento é uma diário de estoque que pode ser usado para adicionar ou remover estoque. Ele funciona como um diário de ajuste do estoque. No entanto, uma diferença importante é que a conta principal que faz a contrapartida da entrada é especificada.</p><p>O diário de movimento insere saldos iniciais e ajustes pontuais que devem ser contabilizados. Por exemplo, ele é usado quando estoque é removido para um exemplo de vendas.</p><p>Quando o diário é lançado, as atualizações físicas e financeiras ocorrem simultaneamente.</p><p>As quantidades positivas nas linhas do diário representam os recebimentos, e as quantidades negativas representam as saídas.</p> |
| Ajuste de estoque | Ambos | Ambos | Um diário de ajuste de estoque é usado para adicionar ou remover estoque. Ele não permite que você selecione uma contrapartida. Somente as contas especificadas na página **Perfil de lançamento de estoque** são usadas para atualizar a entrada da contabilidade. |
| Transferência (diário) | Ambos | Ambos | <p>Um diário de transferência é usado para mover estoque de um local para outro (usando dimensões de armazenamento). Ele atualiza as informações dos produtos em uma transação de estoque com novas dimensões de produto ou de rastreamento.</p><p>Um diário de transferência cria uma linha para a movimentação de um item. Essa linha tem campos "de" e "para" para as dimensões de estoque. Cada linha em um diário de transferência cria duas transações de estoque. Uma transação é criada para as dimensões de estoque "de". Ela representa a saída e tem uma quantidade negativa. A outra transação é criada para as dimensões de estoque "para". Ela representa o recebimento e tem uma quantidade positiva.</p><p>Os diários de transferência podem não criar um comprovante se a movimentação do estoque for considerada uma transferência não financeira. As dimensões de estoque diferentes dos valores de "de" e "para" não são marcadas com a opção **Estoque financeiro** na página **Grupo de dimensões de armazenamento** ou **Grupo de dimensões de rastreamento**. Por exemplo, se a opção **Estoque financeiro** não estiver marcada na dimensão **Localização**, e você mover estoque de uma localização para outra no mesmo local e depósito, nenhum comprovante será criado.</p><p>Os diários de transferência são diferentes das ordens de transferência, nos quais não há nenhum documento para a movimentação. A atualização é feita em uma transação ao lançar o diário. Por outro lado, uma ordem de transferência pode gerar documentos de separação e remessa e requer duas atualizações para o processamento da transação.</p> |
| Remessa da ordem de transferência | Problema | Ambos | <p>Quando você cria uma ordem de transferência, cada combinação de uma linha e uma dimensão de estoque tem duas transações de estoque: uma para a remessa da ordem de transferência e uma para o recebimento da ordem de transferência. Quando você envia uma ordem de transferência, duas novas transações de estoque são atualizadas e duas transações de estoque adicionais são criadas para os produtos em trânsito, totalizando quatro transações.</p><ol><li>A primeira transação de estoque é usada para remover o item da localização e do depósito de origem. O status dessa transação de saída é **Vendido**, para indicar que o item não está mais disponível no depósito.</li><li>A segunda transação de estoque é usada para adicionar o item ao depósito de trânsito selecionado como o depósito de onde o item está sendo transferido. O status de recebimento dessa transação é atualizado **Comprado**.</li><li>A terceira transação de estoque é para a transferência do depósito de trânsito para o depósito de destino. O status de saída dessa transação é atualizado **Reserva física**. Esses status garante que o item não possa ser consumido por outro processo enquanto ainda estiver em trânsito.</li><li>A quarta transação de estoque é para o recebimento dos produtos no depósito de destino. O status de recebimento dessa transação é atualizado **Encomendado**.</li></ol> |
| Recebimento da ordem de transferência | Recebimento | Ambos | Quando uma ordem de transferência é recebida no depósito de destino, o status do estoque da transação de estoque que está no depósito de trânsito (número 3 no exemplo anterior) é atualizado para **Vendido**, e o status do estoque da transação de estoque para o depósito de destino é atualizado para **Comprado**. |
| Listas de Materiais | Ambos | Ambos | É possível usar um diário de lista de materiais (BOM) para relatar um produto como concluído e consumir novas matérias-primas que foram consumidas durante o processo sem usar uma ordem de produção. Um diário de BOM geralmente inclui, pelo menos, uma linha positiva para o produto concluído e uma ou mais linhas negativas para as matérias-primas que estão sendo consumidas. A linha de produto concluído é um recebimento no estoque, enquanto as linhas negativas são saídas do estoque de matérias-primas. Ao criar um diário de BOM, a primeira linha é o cabeçalho da BOM e as linhas subsequentes que são adicionadas são as linhas da BOM. |
| Alteração de propriedade de estoque | Ambos | Ambos | Um diário da alteração de propriedade de estoque é usado para alterar a propriedade de estoque em consignação do fornecedor para sua organização. Os diários da alteração de propriedade de estoque se parecem com diários de transferência de estoque, pois duas transações de estoque estão relacionadas a cada combinação de uma linha e uma dimensão de estoque. Uma transação de estoque remove o estoque do fornecedor na dimensão **Propriedade** e a outra adiciona o item à entidade legal na dimensão **Propriedade**. |
| Entrada de item | Recebimento | Físico | Um diário de entrada de itens é usado para atualizar o status do recebimento do estoque para **Registrado**. Ele é geralmente usado para o recebimento de produtos de uma ordem de compra e devoluções de ordem de venda. |
| Entrada de produção | Recebimento | Físico | Um diário de entrada de produção se parece com um diário de entrada de itens. A entrada de produção é usada para receber produtos concluídos de uma ordem de produção no depósito. Quando o diário é lançado, o status da transação de estoque é atualizada para **Registrado**. |
| Contagem | Ambos | Ambos | Um diário de contagem é uado para registrar a quantidade de itens que foram contados para uma combinação específica de dimensões de estoque. Transações de estoque são criadas quando a linha do diário tem uma diferença na contagem. Uma linha que tenha uma quantidade contada mais alta causa um recebimento no estoque. Uma linha que tenha uma quantidade contada mais baixa causa uma saída no estoque. As linhas em que a quantidade contada corresponde com a quantidade esperada não geram transações de estoque. |
| Contagem de etiquetas | Não aplicável | Não aplicável | Um diário de contagem de etiquetas é usado para rastrear etiquetas de estoque que são atribuídas e usadas em uma contagem completa de estoque. É possível usar o diário para atribuir um número de etiqueta a uma combinação específica de um item e uma dimensão de estoque e para rastrear o status dessa etiqueta durante um estoque completo. Os diários de contagem de etiquetas não criam transações de estoque. |
| Ordens de qualidade | Problema | Físico | <p>Uma ordem de qualidade é usada para registrar os resultados do teste em um determinado lote no estoque. Cada ordem de qualidade está relacionada a uma transação de estoque existente ou a uma parte de uma transações de estoque.</p><p>A ordem de qualidade gerará uma nova transação de estoque em duas situações:</p><ul><li>Quando a ordem de qualidade é marcada como **Teste destrutivo** na guia **Geral**.</li><li>Quando a ordem de qualidade é marcada como **Quarentena após da falha de validação** na guia **Geral** e há falha de validação do teste. Nesse caso, duas transações de estoque serão criadas. Uma transação de estoque remove o item da combinação original de dimensão de estoque e localização e a outra adiciona o item ao depósito de quarentena.</li></ul> |
| Ordens de quarentena | Ambos | Ambos | <p>As transações de estoque de ordens de quarentena são como uma ordem de transferência. Um depósito de quarentena é usado para rastrear o estoque. Há duas transações de recebimento e duas transações de saída.</p><p>Quando a ordem é criada inicialmente, duas transações são criadas. A transação de recebimento tem um status de **Encomendado** para o depósito de quarentena que está vinculado ao depósito em que o item está localizado. A transação de saída tem um status de **Na ordem** para o depósito em que o item está armazenado.</p><p>Ao iniciar a ordem de quarentena, duas transações adicionais são criadas, e as transações existentes são atualizadas. O status da transação de recebimento para o depósito de quarentena é atualizado para **Recebido** e o status da transação de saída para o depósito de armazenamento é atualizado para **Deduzido**.</p><p>As duas novas transações são usadas para indicar a eventual movimentação de volta para o depósito de armazenamento. A transação de recebimento tem um status de **Encomendado** para o depósito de armazenamento, e essa transação de saída tem um status de **Reserva física** para o depósito de quarentena.</p><p>Ao relatar uma ordem de quarentena como concluída, essa operação representa a atualização física da ordem de quarentena. O status de recebimento no depósito de armazenamento é atualizado para **Recebido**.</p><p>Ao encerrar a ordem de quarentena, essa operação representa a atualização financeira da ordem de quarentena. O status das transações de saída é atualizado para **Vendido** e o status das transações de recebimento é atualizado para **Comprado**.</p><p>Como alternativa, você pode descartar a ordem de quarentena. Essa operação remove o item do estoque. Ao descartar uma ordem de quarentena, restarão somente três transações. A transação de recebimento para o depósito de armazenamento é removida e o status da transação de recebimento restante é atualizado para **Comprado**. O status das duas transações de saída é atualizado para **Vendido**. Essa operação é uma atualização física e financeira da ordem.</p> |

## <a name="fixed-receipt-price-posting"></a>Lançamento de preço de recebimento fixo

O preço de recebimento fixo permite que você use um custo padrão para um produto. Ele é uma alternativa para selecionar a opção **Custo padrão** na página **Grupos de modelos de item** de um item. A principal diferença é que, quando um preço de recebimento fixo é usado, o preço de custo que está configurado no momento será usado para o item quando o recebimento no estoque for lançado. Não há nenhum processo de reavaliação de custos para um preço de recebimento fixo. Quando uma atualização financeira é lançada, o preço de custo atual é usado no momento do lançamento Se o preço de custo usado no recebimento e na fatura for diferente, a variação será lançada nas contas de lucros e perdas do preço de recebimento fixo.

Para usar um preço de recebimento fixo opcionalmente para um produto, você deve concluir a seguinte configuração:

- Marque a caixa de seleção **Lançar estoque físico** na página **Grupo de modelos de item** para o item selecionado na linha da transação de estoque.
- Marque a caixa de seleção **Preço de recebimento fixo** na página **Grupo de modelos do item**.
- Especifique as contas principais para os seguintes tipos de lançamento na página **Perfil de lançamento de estoque**:

    - Lucro sobre preço de recebimento fixo
    - Perda sobre preço de recebimento fixo

Para obter mais informações, consulte [Preço de recebimento fixo](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="catch-weight-posting"></a>Lançamento de peso variável

Os produtos de peso variável geralmente são usados em setores como o de alimentos, em que os produtos podem variar levemente em peso, tamanho ou ambos. Os produtos de peso variável usam duas unidades de medida: uma unidade de estoque e uma unidade de peso variável. O peso do estoque quando ele vem para um depósito pode ser diferente do peso quando o estoque sai do depósito. Processamento de produtos de peso variável ajusta o estoque.

Se houver uma variação no peso variável, as diferenças serão lançadas nas contas especificadas nos campos **Perda de peso variável** e **Lucro de peso variável** na página **Perfil de lançamento de estoque**. Normalmente, a mesma conta é especificada nos dois campos.

A tabela a seguir mostra exemplos dos tipos de lançamento padrão e inclui exemplos e descrições de contas principais.

- A coluna "Débito/Crédito?" indica se a transação é normalmente um débito ou um crédito. Em alguns casos, a transação pode lançar débitos ou créditos.
- A coluna "Conta de compensação" indica que o tipo de lançamento é uma conta de compensação. Em outras palavras, o valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada.
- A coluna "P/F" indica o tipo de lançamento. "P" representa lançamento físico e "F" representa lançamento financeiro.
- A coluna "Seguir" indica se a conta principal para o tipo de lançamento é normalmente a mesma que a conta principal para outro tipo de lançamento. Especificamente, ela indica o tipo de lançamento que geralmente é usado para o lançamento.

> [!NOTE]
> As contas principais e os nomes das contas principais na tabela são sugestões. Recomendamos que você trabalhe com o seu contador para determinar a melhor configuração para as necessidades de sua empresa.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | P/F | Seguir | Descrição |
|---|---|---|---|---|---|---|---|---|
| Conta de perda de peso variável | 510520 | Ajuste de estoque | Despesa | | Número | Ambos | Conta de lucro de peso variável | Essa conta é usada quando você lança uma transação de estoque em que a quantidade de peso variável é mais baixa. |
| Conta de lucro de peso variável | 510520 | Ajuste de estoque | Despesa | | Número | Ambos | Conta de perda de peso variável | Essa conta é usada quando você lança uma transação de estoque em que a quantidade de peso variável é mais alta. |

Para obter mais informações sobre produtos de peso variável, consulte [Sobre itens de peso variável](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.md) e [Processamento de produtos de peso variável com gerenciamento de depósito](/supply-chain/warehousing/catch-weight-processing.md).

## <a name="inventory-to-fixed-asset-transfer-posting"></a>Lançamento de transferência de estoque para um ativo fixo

O diário de transferência de estoque para ativos fixos (**Ativos fixos** \> **Diários** \> **Diário de transferência de estoque para ativos fixos**) Para obter mais informações, consulte [Integração de ativos fixos](/fixed-assets/fixed-asset-integration.md).

A tabela a seguir mostra exemplos dos tipos de lançamento padrão e inclui exemplos e descrições de contas principais.

- A coluna "Débito/Crédito?" indica se a transação é normalmente um débito ou um crédito. Em alguns casos, a transação pode lançar débitos ou créditos.
- A coluna "Conta de compensação" indica que o tipo de lançamento é uma conta de compensação. Em outras palavras, o valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada.
- A coluna "P/F" indica o tipo de lançamento. "P" representa lançamento físico e "F" representa lançamento financeiro.
- A coluna "Seguir" indica se a conta principal para o tipo de lançamento é normalmente a mesma que a conta principal para outro tipo de lançamento. Especificamente, ela indica o tipo de lançamento que geralmente é usado para o lançamento.

> [!NOTE]
> As contas principais e os nomes das contas principais na tabela são sugestões. Recomendamos que você trabalhe com o seu contador para determinar a melhor configuração para as necessidades de sua empresa.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | P/F | Seguir | Descrição |
|---|---|---|---|---|---|---|---|---|
| Emissão de ativo fixo | 180100 | Ativos fixos tangíveis | Ativo | Crédito | Número | Ambos | Não aplicável | Essa conta é usada quando você lança um diário de estoque para ativos fixos para remover um item do estoque e convertê-lo em um ativo fixo. |

## <a name="moving-average-posting"></a>Lançamento de média móvel

A média móvel é um modelo de custos perpétuo baseado no princípio de média. Os custos nas saídas de estoque não são alterados quando custo de compra é alterado. A diferença é capitalizada e baseia-se em um cálculo proporcional. O valor restante é despesa.

A tabela a seguir mostra exemplos dos tipos de lançamento padrão com as principais contas e descrições da amostra.

- A coluna "Débito/Crédito?" indica se a transação é normalmente um débito ou um crédito. Em alguns casos, a transação pode lançar débitos ou créditos.
- A coluna "Conta de compensação" indica que o tipo de lançamento é uma conta de compensação. Em outras palavras, o valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada.
- A coluna "P/F" indica o tipo de lançamento. "P" representa lançamento físico e "F" representa lançamento financeiro.
- A coluna "Seguir" indica se a conta principal para o tipo de lançamento é normalmente a mesma que a conta principal para outro tipo de lançamento. Especificamente, ela indica o tipo de lançamento que geralmente é usado para o lançamento.

> [!NOTE]
> As contas principais e os nomes das contas principais na tabela são sugestões. Recomendamos que você trabalhe com o seu contador para determinar a melhor configuração para as necessidades de sua empresa.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | P/F | Seguir | Descrição |
|---|---|---|---|---|---|---|---|---|
| Diferença de preço da média de movimentos | 510600 | Diferença de preço da média móvel | Despesa | Ambos | Número | Ambos | Não aplicável | Essa conta é usada quando há uma diferença no custo entre o recebimento e a fatura. |
| Reavaliação da média de movimentos | 510610 | Reavaliação da média de movimentos | Despesa | Ambos | Número | Ambos | Não aplicável | Essa conta é usada quando você ajusta a média móvel de um produto |

## <a name="sample-posting-profile-configuration"></a>Exemplo de configuração de perfil de lançamento

A tabela a seguir mostra exemplos dos tipos de lançamento padrão com as principais contas e descrições da amostra.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | P/F | Seguir | Descrição |
|---|---|---|---|---|---|---|---|---|
| Saída do estoque | 140100 | Estoque de materiais | Ativo | Crédito | Número | Ambos | Recebimento de estoque | Essa conta é usada quando uma transação de estoque lançada é uma saída (quantidade negativa) e não está relacionada a vendas, compras ou produção. A contrapartida para essa conta é a conta Despesas de estoque, perda. Essa conta normalmente representa o estoque no balanço patrimonial. |
| Despesas de estoque, perda | 510100 | Lucros e perdas de estoque | Despesa | Débito | Número | Ambos | Despesas de estoque, lucro | Essa conta é usada quando uma transação de estoque lançada é uma saída (quantidade negativa) e não está relacionada a vendas, compras ou produção. A contrapartida para essa conta é a conta Saída de estoque. |
| Recebimento de estoque | 140100 | Estoque de materiais | Ativo | Débito | Número | Ambos | Saída do estoque | Essa conta é usada quando uma transação de estoque lançada é um recebimento (quantidade positiva) e não está relacionada a vendas, compras ou produção. A contrapartida para essa conta é a conta Despesas de estoque, lucro. Essa conta normalmente representa o estoque no balanço patrimonial. |
| Despesas de estoque, lucro | 510100 | Lucros e perdas de estoque | Despesa | Crédito | Número | Ambos | Despesas de estoque, perda | Essa conta é usada quando uma transação de estoque lançada é um recebimento (quantidade positiva) e não está relacionada a vendas, compras ou produção. A contrapartida para essa conta é a conta Recebimento de estoque. |
| A pagar entre unidades | 231500 | Interunidade a pagar | Passivo | Débito | Número | Ambos | | Essa conta é usada quando o estoque é transferido entre dimensões de estoque, como locais, e o custo de um item é diferente entre os locais. |
| A receber entre unidades | 131500 | Interunidade recebível | Ativo | Crédito | Número | Ambos | | Essa conta é usada quando o estoque é transferido entre dimensões de estoque, como locais, e o custo de um item é diferente entre os locais. |
