---
title: Configurar contas a pagar
description: Este artigo descreve as páginas que você usa para configurar a funcionalidades básicas e opcionais de contas a pagar no Microsoft Dynamics 365 for Finance and Operations. Também mostra as etapas de configuração que devem ser concluídas antes de começar a configurar as contas a pagar.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a832a30870f77578503bae6eea17ad1d0881d91
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "326690"
---
# <a name="configure-accounts-payable"></a>Configurar contas a pagar

[!include [banner](../includes/banner.md)]

Este artigo descreve as páginas que você usa para configurar a funcionalidades básicas e opcionais de contas a pagar no Microsoft Dynamics 365 for Finance and Operations. Também mostra as etapas de configuração que devem ser concluídas antes de começar a configurar as contas a pagar.

<a name="prerequisites-for-accounts-payable-setup"></a>Pré-requisitos para a configuração de contas a pagar
----------------------------------------

Antes de poder configurar contas a pagar, é necessário concluir a seguinte configuração:

-   Na contabilidade:
    -   Se você planeja usar diários de pagamentos, configure os diários de pagamentos.
    -   Se você planeja executar ajustes cambiais, configure os códigos de moeda na página Moedas, configure os tipos de taxa de câmbio na página Tipos de taxa de câmbio, e configure as taxas de câmbio de moeda na página Taxas de câmbio de moeda.
-   No Gerenciamento de caixa e bancos, configure as contas bancárias a serem usadas com os métodos de pagamento.

## <a name="setup-pages-for-accounts-payable"></a>Páginas de configuração de contas a pagar

Use as páginas a seguir para configurar a funcionalidade básica de Contas a pagar para cada entidade legal. As páginas são listadas na ordem de configuração recomendada. Para simplificar o processo de configuração, você pode criar modelos a partir dos primeiros registros criados. Em um modelo, os valores são normalmente inseridos em vários campos para refletir os recursos que a organização quer implementar para um determinado tipo de fornecedor.
1.  Na página Condições de pagamento, defina as condições de pagamento que você atribui às ordens de venda, ordens de compra, clientes, e fornecedores, e que determinam as datas de validade de fatura. Para obter mais informações, consulte [Definir taxas de pagamento de fornecedor](tasks/define-vendor-payment-fees.md).
2.  Na página Métodos de pagamento - fornecedores, crie e mantenha informações sobre como a organização paga seus fornecedores.
3.  Na página Grupos de fornecedores, crie e mantenha grupos de fornecedores que compartilham parâmetros importantes para lançamento, liquidação e pagamento, relatórios, e previsão.
4.  Na página Perfis de lançamento de fornecedor, defina como as transações de fornecedor são lançadas na contabilidade.
5.  Na página Parâmetros de contas a pagar, defina as configurações padrão aplicadas na ausência de uma configuração mais específica, os parâmetros para vários tipos de funcionalidades e as diversas sequências numéricas para Contas a pagar.
6.  Na página Configuração do formulário, defina o formato de vários documentos relacionados a fornecedores que são usados na organização para rastrear recebimentos de fornecedores e para inserir motivos para o fluxo de pagamentos aos fornecedores.
7.  Na página Fornecedores, crie e mantenha contas de fornecedor, e também as autoridades fiscais às quais sua organização declara os impostos sobre vendas.

## <a name="optional-setup-pages-for-accounts-payable"></a>Páginas de configuração opcionais de contas a pagar
Além da funcionalidade básica, a sessão de contas a pagar possui outras funcionalidades que você pode configurar.

As páginas de configuração adicional são organizados por funcionalidade.

**Políticas**
-   Na página Política de fatura de fornecedor, configure as políticas de fatura de fornecedor.

**Conciliação de fatura**

-   Na página Tolerâncias dos totais de fatura, configure as tolerâncias para os totais de faturas.
-   Na página Política de conciliação, configure as políticas de conciliação dupla e tripla.
-   Na página Tolerâncias de preço, configure as tolerâncias para preços unitários.
-   Na página Grupos de tolerância de preços de item, configure os grupos de tolerância para os preços de item.
-   Na página Grupos de tolerância de preços de fornecedor, configure os grupos de tolerância para os preços de fornecedor.
-   Na página Tolerâncias de encargos, configure as tolerâncias para encargos.

**Fluxo de trabalho**

-   Na página Fluxos de trabalho de contas a pagar, defina as configurações de fluxo de trabalho para aprovações de diários e requisições de compra.

**Motivos**

-   Na página Motivos de fornecedor, configure os códigos de motivo.

**Encargos**

-   Na página Código de encargos, configure os códigos para os encargos que são usados em ordens de compra.
-   Na página Grupo de encargos de fornecedor, crie e mantenha grupos de encargos para fornecedores.
-   Na página Grupos de encargos de item , crie e mantenha grupos de encargos para itens.
-   Na página Encargos automáticos , defina os encargos que são atribuídos automaticamente às ordens.

**Itens suplementares**

-   Na página Grupos de itens complementares - Fornecedor , crie e mantenha grupos de itens complementadores para fornecedores.
-   Na página Grupos de itens complementares - Estoque , crie e mantenha grupos de itens complementadores para itens.

**Distribuição**

-   Na página Condições de entrega , crie e mantenha as condições para uma transferência de item do vendedor para o comprador.
-   Na página Modos de entrega , crie e mantenha os métodos de transporte usados quando uma ordem é entregue do vendedor ao comprador.
-   Na página Códigos de destino , crie e mantenha identificadores e descrições para os destinos de entrega.

**Formulários**

-   Na página Notas do formulário , crie o texto padrão que aparece em diversas páginas.
-   Na página Parâmetros de classificação de formulário , configure a ordem de classificação para requisições, listas de recebimento, guias de remessa, e faturas.
-   Na página Gerenciamento de impressão , configure as informações de gerenciamento de impressão para documentos originais e cópias de páginas.

**Pagamentos**

-   Na página Descontos à vista , configure e gerencie as condições para a obtenção de descontos à vista. Os códigos de desconto à vista estão associados a fornecedores e são aplicados a ordens de compra.
-   Na página Planos de pagamento , configure os planos de pagamento usados para gerenciar pagamentos a prestação para fornecedores.
-   Na página Dias de pagamento , defina os dias de pagamento usados para calcular as datas de validade, e especifique os dias de pagamento para um dia específico da semana ou mês.
-   Na página Taxa de pagamento , crie e mantenha as taxas de pagamento que estão associadas aos fornecedores.
-   Na página Instrução de pagamento , crie e mantenha as instruções de pagamento.

**Estatísticas**

-   Na página Definições do período de classificação por vencimento , configure intervalos definidos pelo usuário para analisar a distribuição de vencimentos de contas de fornecedores.
-   Na página Linha de negócio , crie os códigos de linha de negócio (LOB) que são atribuídos aos fornecedores.

**Imposto 1099**

-   Na página **Campos 1099**, verifique e atualize os valores mínimos que devem ser informados à Administração Fiscal (IRS), com base nos requisitos mais recentes da IRS.

## <a name="optional-setup-for-other-modules"></a>**Configuração opcional para outros módulos**
**Administração da organização**

-   Na página Sequências numéricas , configure os grupos de sequência numérica para números de fatura.
-   Nas páginas a seguir, configure as informações de endereço:
    -   Configuração de endereço
    -   Códigos NAF
    -   Importar CEPs

**Contabilidade**

-   Na página Dimensões financeiras , configure as dimensões financeiras.
-   Nas páginas a seguir, configure as informações de imposto:
    -   Códigos de imposto
    -   Grupos de impostos
    -   Grupos de impostos do item
    -   Grupo de contas
    -   Códigos de isenção do imposto
    -   Jurisdições de impostos
    -   Autoridades do imposto
    -   Períodos de liquidação de imposto

**Gerenciamento de caixa e bancos**

-   Na página Códigos de finalidade de pagamento, configure o código de finalidade do banco central.





