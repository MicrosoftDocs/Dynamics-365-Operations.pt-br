---
title: Princípio contábil de lançar na conta de encargos
description: Este artigo fornece uma visão geral do princípio contábil de lançar em conta de encargos.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: c03109baaa341b25af70840b791ddf04f692fb1a
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016555"
---
# <a name="post-to-charge-account-accounting-principle"></a>Princípio contábil de lançar na conta de encargos

O princípio contábil *lançar na conta de encargos* permite que você faça a contabilização e reconcilie quaisquer diferenças ocorridas no preço unitário entre um lançamento físico e um lançamento financeiro, custos indiretos em itens comprados ou encargos em uma ordem de compra.

Duas configurações para os códigos de encargos de Contas a pagar na página de **Código de encargos** (**Contas a pagar \> Configuração de encargos \> Código de encargos**) podem fazer com que uma ordem de compra afete a avaliação dos ativos em estoque:

- Para códigos de encargos nos quais o campo **Tipo de débito** está definido como *Item* e o campo **Tipo de crédito** é definido como *Conta contábil*, a conta contábil selecionada como a conta de absorção atua como uma conta de variação de estoque.
- Para códigos de encargos nos quais o campo **Tipo de débito** está definido como *Item* e o campo **Tipo de crédito** está definido como *Cliente/Fornecedor*, o encargo será contabilizado como custo de material e a conta de variação de estoque do item será usada.

## <a name="european-special-accounting-rule"></a>Regra de contabilidade especial europeia

Na Europa, o princípio contábil de *lançar na conta de encargos* é geralmente usado para incorporar uma regra de contabilidade especial. Por exemplo, um dos métodos a seguir geralmente é usado para contabilizar as alterações de estoque:

- **Custo do método de vendas** – a configuração do perfil de lançamentos de estoque padrão oferece suporte a esse método. O princípio contábil de *lançar na conta de encargos* não é necessário.
- **Natureza do método de despesas** – as organizações menores geralmente usam esse método. Em geral, ele envolve as seguintes etapas:

    1. As mercadorias ou os serviços são totalmente despendidos no momento do recebimento.
    2. No final do período, uma contagem de ciclos é executada.
    3. Um ajuste manual da quantidade e do valor é lançado no estoque. (A contrapartida é uma conta de variação de estoque que desloca as despesas lançadas na etapa 1. Portanto, a variação no valor do estoque só é exibida nesta conta).

O princípio de *lançar na conta de encargos* permite automatizar totalmente os dois lançamentos. Dessa forma, você poderá eliminar um lançamento manual de um ajuste de fechamento de final de período.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>Habilitar o princípio contábil de lançar na conta de encargos

Para habilitar o princípio contábil de *lançar na conta de encargos*, siga estas etapas.

1. Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.
2. Na guia **Fatura**, na Guia Rápida **Fatura**, defina a opção **Lançar na conta de encargos no razão** como *Sim*.
3. Feche a página.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>Pré-requisitos e parâmetros recomendados para o princípio contábil de lançar na conta de encargos

Se você planeja considerar os encargos de compra e as variações de estoque, os seguintes pré-requisitos deverão estar em vigor:

- Na guia **Fatura** da página **Parâmetros de contas a pagar** (**Contas a pagar \> Configuração \> Parâmetros de contas a pagar**), a opção **Lançar na conta de encargos no razão** deve ser definida como *Sim*.
- Na página **Grupos de modelos de custo** (**Gerenciamento de custos \> Configuração de políticas contábeis de estoque \> Grupos de modelos de item**), todas as opções a seguir devem ser definidas como *Sim* para cada grupo de modelos relevante que contenha itens incluídos em uma ordem de compra:

    - Lançar estoque físico
    - Lançar estoque financeiro
    - Acumular passivo no recebimento de produtos

- Na guia **Entrega** da página **Parâmetros de compra e fornecimento** (**Compras e fornecimento \> Configuração \> Parâmetros de compras e fornecimento**), a opção **Gerar encargos no recebimento do produto** deve ser definida como *Sim*.
- Na guia **Contabilidade de estoque** da página **Parâmetros de gerenciamento de estoque e depósito** (**Gerenciamento de estoque \> Configuração \> Parâmetros de gerenciamento de estoque e depósito**), a opção **Lançar guia de remessa no razão** deve ser definida como *Sim*.
- Na guia **Ordem de compra** da página **Lançamento** (**Gerenciamento de estoque \> Configuração \> Lançamento \> Lançamento**), as contas principais que se aplicam a cada item relevante devem ser especificadas para cada um dos seguintes tipos de lançamento:

    - Despesa de compra, não faturada
    - Despesa de compra para produto
    - Variação de estoque

## <a name="example-scenario-1-change-in-unit-cost-price"></a>Cenário 1 de exemplo: alteração no preço de custo unitário

Este cenário de exemplo tem os seguintes pré-requisitos:

- Modelo de custos PEPS (primeiro a entrar, primeiro a sair)

O procedimento a seguir fornece um exemplo que mostra o que acontece quando você altera o preço de custo unitário em uma ordem de compra.

1. Crie uma ordem de compra para uma quantidade 1 de um item e um preço unitário 100,00.
2. Confirme uma ordem de compra.
3. Lance o recebimento de produtos para a ordem de compra.
4. Valide o comprovante no recebimento de produtos. A tabela a seguir mostra um comprovante de exemplo.

    | Tipo de lançamento | Conta principal | Nome da conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Físico/Financeiro? | Valor |
    |---|---|---|---|---|---|---|---|
    | Compra, variação de estoque | 600170 | Materiais de variação de estoque | Despesa | Crédito | Número | Físico | -100,00 |
    | Custo de materiais comprados recebidos | 140100 | Estoque de Materiais | Ativo | Débito | Sim | Físico | 100.00 |
    | Despesa de compra, não faturada | 600180 | Recebimentos de Material | Despesa | Débito | Sim | Físico | 100.00 |
    | Compra, acúmulo | 200140 | Compras Acumuladas | Passivo | Crédito | Sim | Físico | -100,00 |

5. Lance a fatura da ordem de compra com um preço unitário atualizado para 110,00.
6. Valide o comprovante na fatura. A tabela a seguir mostra um comprovante de exemplo.

    | Tipo de lançamento | Conta principal | Nome da conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Físico/Financeiro? | Valor |
    |---|---|---|---|---|---|---|---|
    | Compra, variação de estoque | 600170 | Materiais de variação de estoque | Despesa | Crédito | Número | Financeiras | -10,00 |
    | Custo de materiais comprados recebidos | 140100 | Estoque de Materiais | Ativo | Débito | Sim | Financeiras | -100,00 |
    | Despesa de compra, não faturada | 600180 | Recebimentos de Material | Despesa | Débito | Sim | Financeiras | -100,00 |
    | Compra, acúmulo | 200140 | Compras Acumuladas | Passivo | Crédito | Sim | Financeiras | 100.00 |
    | Custo de materiais comprados faturados | 140100 | Estoque de Materiais | Ativo | Débito | Número | Financeiras | 110.00 |
    | Despesa de compra para produto | 600180 | Recebimento de Material | Despesa | Crédito | Número | Financeiras | 110.00 |
    | Saldo de fornecedor | 211000 | Comercial de Contas a Pagar | Passivo | Crédito | Número | Financeiras | -110,00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>Exemplo 2: Encargos e custos indiretos na ordem de compra

Este cenário de exemplo tem os seguintes pré-requisitos:

- Modelo de custos PEPS
- **Código de encargos 1:** item de débito e conta contábil de crédito para 10%
- **Código de encargos 2:** item de débito e cliente/fornecedor de crédito para 10,00 proporcional
- **Custo indireto:** 2,00% adicionados ao preço de compra

O procedimento a seguir fornece um exemplo que mostra o que acontece quando você inclui encargos e custos indiretos em uma ordem de compra.

1. Crie uma ordem de compra para uma quantidade 1 de um item e um preço unitário 100,00.
2. Adicione um código de encargos para 10% que debite o item e credite o razão.
3. Adicione um código de encargos para 10,00 que debite o item e credite o cliente/fornecedor.
4. Aloque os encargos nas linhas da ordem de compra.
5. Confirme uma ordem de compra.
6. Lance o recebimento de produtos para a ordem de compra.
7. Valide o comprovante no recebimento de produtos. A tabela a seguir mostra um comprovante de exemplo.

    | Tipo de lançamento | Conta principal | Nome da conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Físico ou Financeiro | Valor |
    |---|---|---|---|---|---|---|---|
    | Compra, variação de estoque | 600170 | Materiais de variação de estoque | Despesa | Crédito | Número | Físico | -110,00 |
    | Custo indireto estimado absorvido | 600520 | Custos Indiretos Absorvidos | Despesa | Crédito | Sim | Físico | -2,40 |
    | Frete de compra | 600120 | Custos de Frete/Transporte | Despesa | Crédito | Número | Físico | -10,00 |
    | Custo de materiais comprados recebidos | 140100 | Estoque de Materiais | Ativo | Débito | Sim | Físico | 122.40 |
    | Despesa de compra, não faturada | 600180 | Recebimentos de Material | Despesa | Débito | Sim | Físico | 110.00 |
    | Compra, acúmulo | 200140 | Compras Acumuladas | Passivo | Crédito | Sim | Físico | -110,00 |

8. Lance a fatura para a ordem de compra.
9. Valide o comprovante na fatura. A tabela a seguir mostra um comprovante de exemplo.

    | Tipo de lançamento | Conta principal | Nome da conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | Físico/Financeiro? | Valor |
    |---|---|---|---|---|---|---|---|
    | Compra, variação de estoque | 600170 | Materiais de variação de estoque | Despesa | Crédito | Número | Financeiras | 0,00 |
    | Custo indireto estimado absorvido | 600520 | Custos Indiretos Absorvidos | Despesa | Débito | Sim | Financeiras | 2.40 |
    | Custo indireto absorvido | 600520 | Custos Indiretos Absorvidos | Despesa | Débito | Número | Financeiras | -2,40 |
    | Custo de materiais comprados recebidos | 140100 | Estoque de Materiais | Ativo | Crédito | Sim | Financeiras | -110,00 |
    | Despesa de compra, não faturada | 600180 | Recebimentos de Material | Despesa | Crédito | Sim | Financeiras | -110,00 |
    | Compra, acúmulo | 200140 | Compras Acumuladas | Passivo | Débito | Sim | Financeiras | 110.00 |
    | Custo de materiais comprados faturados | 140100 | Estoque de Materiais | Ativo | Débito | Número | Financeiras | 110.00 |
    | Despesa de compra para produto | 600180 | Recebimento de Material | Despesa | Crédito | Número | Financeiras | 110.00 |
    | Saldo de fornecedor | 211000 | Comercial de Contas a Pagar | Passivo | Crédito | Número | Financeiras | -110,00 |
