---
title: Parâmetros de lançamento do Commerce
description: Este artigo descreve os parâmetros específicos do lançamento de transações financeiras e físicas no Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 10ea650b7c5c0cad7e1a3d7556c073aecef06036
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887105"
---
# <a name="commerce-posting-parameters"></a>Parâmetros de lançamento do Commerce

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve os parâmetros específicos do lançamento de transações financeiras e físicas no Microsoft Dynamics 365 Commerce. Os parâmetros de lançamento estão localizados no Commerce headquarters em **Varejo e Comércio \> Configuração do headquarters \> Parâmetros \> Parâmetros do Commerce \> Lançamentos**.

## <a name="periodic-discount-parameters"></a>Parâmetros de desconto periódico

A tabela a seguir lista os parâmetros de desconto periódicos específicos para o lançamento de transações financeiras e físicas.

| Parâmetro | Descrição |
|-----------|-------------|
| Lançar desconto periódico | Esta opção controla se as ofertas periódicas são lançadas nas contas contábeis. Os descontos periódicos incluem descontos de compra combinada, descontos por quantidade e ofertas de desconto. Quando este parâmetro é habilitado, os campos adicionais podem ser definidos na seção **Descontos periódicos**. |
| Tipo de conta contábil | <p>Selecione o tipo de conta usado para lançar descontos periódicos:</p><ul><li>**Padrão** – o sistema não usa os campos relacionados a descontos nesta página. Ele usa as contas definidas na página **Lançamento** na Commerce headquarters (**Gerenciamento de estoque \> Configuração \> Lançamentos \> Formulários de lançamento**).</li><li>**Periódico** – o sistema usa as contas de desconto do Commerce especificadas pelos campos relacionados ao desconto nesta página. Se você selecionar essa opção, será necessário especificar a conta contábil (GL) para cada tipo de oferta (desconto, compra combinada, quantidade e limite). Ao configurar cada desconto, você pode definir uma conta. Quando o recurso de lançamento de conta de desconto é usado na página de configuração de desconto, uma entrada de débito e uma entrada de crédito adicionais são feitas para reclassificar o lançamento de desconto da conta contábil de desconto do Commerce para a conta contábil de desconto. Para obter mais informações, consulte [Descontos de varejo](retail-discounts-overview.md).</li></ul> |
| Lançar desconto de código de informação | Esta opção não é mais usada na solução padrão do Commerce e será preterida. |
| Lançar desconto periódico das ordens | Esta opção controla se os descontos periódicos de varejo são lançados no razão para pedidos de clientes e pedidos de call center. |

## <a name="inventory-update-parameters"></a>Parâmetros de atualização de inventário

A tabela a seguir lista os parâmetros de atualização de inventário específicos para o lançamento de transações financeiras e físicas.

| Parâmetro | Descrição |
|-----------|-------------|
| Usar a ID do lote padrão quando os números de lote não forem encontrados | Esta opção controla se uma ID de lote padrão é usada para itens habilitados para lote se os números de lote não forem encontrados e o estoque negativo for permitido. |
| ID do lote padrão | O número de lote a ser usado se os números de lote dos itens não forem encontrados e o parâmetro **Usar ID de lote padrão quando os números de lote não forem encontrados** estiver ativado. |

## <a name="aggregation-parameters"></a>Parâmetros de agregação

A tabela a seguir lista os parâmetros de agregação específicos para o lançamento de transações financeiras e físicas.

| Parâmetro | Descrição |
|-----------|-------------|
| Depósito seguro | Ative este parâmetro para agregar todas as transações durante o lançamento do demonstrativo e criar uma única linha no diário para lançamento em vez de uma linha separada para cada remoção. |
| Depósito bancário | Ative este parâmetro para agregar todas as transações durante o lançamento do demonstrativo e criar uma única linha no diário para lançamento em vez de uma linha separada para cada remoção. |
| Transações de vendas | Habilite esse parâmetro para consolidar as transações como parte do processo de lançamento do demonstrativo da transação. Recomendamos que você habilite esse parâmetro. Anteriormente, ele era chamado de **Transações de comprovante**. |
| Não agregar devoluções | Se esta opção for selecionada, cada transação de devolução será lançada como um pedido de venda separado quando um demonstrativo de varejo for lançado. |

## <a name="batch-processing-parameters"></a>Parâmetros de processamento em lote

A tabela a seguir lista os parâmetros de processamento em lote específicos para o lançamento de transações financeiras e físicas.

| Parâmetro | Descrição |
|-----------|-------------|
| Número máximo de demonstrativos paralelos | Este campo define o número de tarefas em lotes usadas para lançar vários demonstrativos. |
| Máximo de threads para o processamento de ordens por demonstrativo | Esse campo representa o número máximo de threads que o trabalho em lote de lançamento de demonstrativo usa para criar e faturar ordens de venda para um único demonstrativo. O número total de threads que o processo de lançamento de demonstrativo usa é calculado multiplicando o valor desse parâmetro pelo valor do parâmetro **Número máximo de lançamentos de demonstrativos paralelos**. Se o valor deste parâmetro for muito alto, poderá afetar negativamente o desempenho do processo de lançamento do demonstrativo. |
| Máximo de linhas de transação incluídas em agregação | Esse campo define o número de linhas de transação que são incluídas em uma única transação agregada antes de uma nova ser criada. As transações agregadas são criadas com base em critérios de agregação diferentes, como o cliente, a data do negócio ou as dimensões financeiras. Observe que as linhas de uma única transação não serão divididas entre transações agregadas diferentes. No entanto, o número de linhas em uma transação agregada pode ser levemente maior ou menor, com base nos fatores como o número de produtos distintos. |
| Número máximo de threads para validar transações de loja | Este campo define o número máximo de threads que são usados para validar transações. A validação de transações é uma etapa obrigatória que deve acontecer antes das transações serem recebidas nos demonstrativos. Também é necessário definir um produto de vale-presente na guia rápida **Vale-presente** na guia **Lançamento** da página **Parâmetros do Commerce**, mesmo que a organização não use vales-presente. |

A tabela a seguir lista os valores recomendados para os parâmetros na tabela anterior. Esses valores devem ser testados e ajustados para a configuração de implantação e a infraestrutura disponível. Os valores que excedem os valores recomendados podem afetar negativamente o processamento de outros lotes e devem ser validados.

| Parâmetro | Valor recomendado | Detalhes |
|-----------|-------------------|---------|
| Número máximo de lançamentos paralelos de demonstrativos | <p>Defina esse parâmetro como o número de tarefas em lotes disponíveis para o grupo de lotes que está executando o trabalho do **Demonstrativo**.</p><p>**Regra geral:** multiplique o número de servidores virtuais do Servidor de Objetos de Aplicativo (AOS) pelo número de tarefas em lotes disponíveis por servidor virtual do AOS.</p> | Esse parâmetro não é aplicável quando o recurso **Demonstrativos de varejo - Fluxo constante** estiver habilitado. |
| Máximo de threads para o processamento de ordens por demonstrativo | Comece a testar valores em **4**. Normalmente, o valor não deve exceder **8**. | Esse parâmetro define o número de threads usados para criar e lançar ordens de venda. Ele representa o número de threads disponíveis para lançamento por demonstrativo. |
| Máximo de linhas de transação incluídas em agregação | Comece a testar valores em **1000**. Dependendo da configuração do Commerce headquarters, ordens menores podem ser mais benéficas para o desempenho. | Esse parâmetro define o número de linhas que são incluídas em cada ordem de venda durante o lançamento do demonstrativo. Depois que esse número for atingido, as linhas serão divididas em uma nova ordem. O número de linhas de vendas não será exatamente igual ao número especificado porque a divisão ocorre no nível da ordem de venda. No entanto, o número será próximo do número definido. Esse parâmetro é usado para gerar ordens de venda para transações de varejo que não têm um cliente nomeado. |
| Número máximo de threads para validar transações de loja | É recomendável definir esse parâmetro como **4** e aumentá-lo somente se não obtiver um desempenho aceitável. O número de threads que esse processo usa não pode exceder o número de processadores disponíveis para o servidor de lote. Se o número de threads for muito alto, o processamento em lotes poderá ser afetado. | Esse parâmetro controla o número de transações que podem ser validadas ao mesmo tempo para uma determinada loja. |

> [!NOTE]
> Todas as configurações e os parâmetros relacionados às postagens de demonstrativo, e definidos em lojas do Commerce na página **Parâmetros do Commerce**, são aplicáveis ao recurso aprimorado de postagem do demonstrativo.

## <a name="invoice-parameters"></a>Parâmetros de fatura

A tabela a seguir lista os parâmetros de fatura específicos para o lançamento de transações financeiras e físicas.

| Parâmetro | Descrição |
|-----------|-------------|
| Nome do diário | O nome do diário de pagamento usado quando os diários de pagamento do cliente para pagamentos de ordens de vendas são criados. Essa configuração se aplica a todos os pagamentos de ordem lançados para ordens de ponto de venda (PDV), call center e canal de comércio eletrônico. |
| Nome da conta | O nome da conta de pagamento. |
| Priorizar dimensões do método de pagamento | Quando esse sinalizador está habilitado, os diários de pagamento priorizam as dimensões da forma de pagamento em vez das dimensões da loja. |
| Comportamento do cálculo de imposto | Esse parâmetro especifica o comportamento quando ordens de venda criadas durante o lançamento do demonstrativo são faturadas:<ul><li>**Recalcular** – calcule novamente os impostos.</li><li> **Não recalcular** – use os valores de imposto calculados no PDV.</li></ul> |
| Nome do diário | O nome do diário usado quando um diário de pagamentos do cliente para reembolsos é criado. Essa configuração se aplica a todos os pagamentos de ordem lançados para ordens de PDV, call center e canal de comércio eletrônico. |

## <a name="statement-parameters"></a>Parâmetros de demonstrativo

A tabela a seguir lista os parâmetros de demonstrativo específicos para o lançamento de transações financeiras e físicas.

| Parâmetro | Descrição |
|-----------|-------------|
| Reservar estoque durante o cálculo | Quando este parâmetro é habilitado, o cálculo do demonstrativo reserva temporariamente o estoque até o demonstrativo seja lançado. Esse parâmetro é desabilitado por padrão para ajudar a melhorar o desempenho do cálculo do demonstrativo. As informações de estoque atualizadas podem ser calculadas usando o trabalho em lote **Lançar estoque**. Lembre-se de que o trabalho em lote de estoque **Lançar** não é mais usado quando a criação de ordens baseada em um [fluxo constante](trickle-feed.md) para transações de loja de varejo está habilitada. |
| É necessário desabilitar a contagem | Este sinalizador desabilita a contagem durante o lançamento no Commerce headquarters. |
| Recalcular dimensões financeiras no erro | Quando esse parâmetro está habilitado, as dimensões financeiras podem ser reavaliadas em lançamentos de demonstrativo subsequentes se o lançamento de demonstrativo falhar. |
| Usar as dimensões financeiras da loja de devolução | Quando esse parâmetro é habilitado, podem ser criadas ordens de venda de devolução vinculadas que usam as dimensões financeiras da loja em vez das dimensões financeiras da transação original. |
| Desvincular devoluções | Quando esse parâmetro é habilitado, o demonstrativo pode criar devoluções de vendas não lançadas como devoluções cegas. Esse parâmetro é desabilitado por padrão e recomenda-se mantê-lo desabilitado. |
| Desabilitar o lançamento da diferença de arredondamento | Este parâmetro desativa o lançamento da diferença de arredondamento entre um pagamento de transação e o valor bruto durante o processamento de pagamentos. |
| Liquidar depósitos de cliente automaticamente | Quando este parâmetro está habilitado, os depósitos do cliente lançados durante o lançamento do demonstrativo de varejo são liquidados em relação às transações abertas do cliente. |
| Habilitar e usar a reconciliação de gerenciamento de pagamentos à vista no PDV | Quando este parâmetro está habilitado, a reconciliação do gerenciamento de caixa é feita no PDV e os valores são passados para o lançamento do demonstrativo financeiro de varejo para criar linhas do demonstrativo. |
| Nível de detalhe do comprovante do razão | Esse parâmetro define o nível de detalhe incluído no comprovante do razão para transações selecionadas originadas no PDV. Os tipos de transação incluem receita, despesas e descontos. Para descontos, este parâmetro é considerado somente quando o número da conta de um desconto periódico e o número da conta de um desconto regular não são iguais. A menos que sejam necessários detalhes, o **Resumo** é o valor recomendado para esses lançamentos. Quando o lançamento em nível de resumo é definida, **TransactionDiscountTrans.RecID** não será preenchido. Na versão do Commerce 10.0.27, esse sinalizador foi renomeado e transferido. Anteriormente, ele era chamado de **Nível de detalhe** e estava na seção **Atualização de estoque**. |
