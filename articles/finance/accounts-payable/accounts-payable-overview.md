---
title: Visão geral sobre configurar contas a pagar
description: Este tópico descreve as páginas que você usa para configurar funcionalidades básicas e opcionais de contas a pagar. Também mostra as etapas de configuração que devem ser concluídas antes de começar a configurar as contas a pagar.
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "24671"
- intro-internal
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6cbc800d7ae4d566fddb111b7ee9d67234e3cf8c
ms.sourcegitcommit: 43d0555c17a0643c9e5ba3bc2da3ce5f80754642
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2022
ms.locfileid: "8325985"
---
# <a name="configure-accounts-payable-overview"></a>Visão geral sobre configurar contas a pagar

[!include [banner](../includes/banner.md)]

Este artigo descreve as páginas que você usa para configurar funcionalidades básicas e opcionais de contas a pagar. Também mostra as etapas de configuração que devem ser concluídas antes de começar a configurar as contas a pagar.

## <a name="prerequisites-for-accounts-payable-setup"></a>Pré-requisitos para a configuração de contas a pagar

Antes de poder configurar contas a pagar, é necessário concluir a seguinte configuração:

-   Na contabilidade:
    -   Se você planeja usar diários de pagamentos, configure os diários de pagamentos.
    -   Se você planeja executar ajustes cambiais, configure os códigos de moeda na página **Moedas**, configure os tipos de taxa de câmbio na página **Tipos de taxa de câmbio** e configure as taxas de câmbio de moeda na página **Taxas de câmbio de moeda**.
-   No Gerenciamento de caixa e bancos, configure as contas bancárias a serem usadas com os métodos de pagamento.

## <a name="setup-pages-for-accounts-payable"></a>Páginas de configuração de contas a pagar

Use as páginas a seguir para configurar a funcionalidade básica de Contas a pagar para cada entidade legal. As páginas são listadas na ordem de configuração recomendada. Para simplificar o processo de configuração, você pode criar modelos a partir dos primeiros registros criados. Em um modelo, os valores são normalmente inseridos em vários campos para refletir os recursos que a organização quer implementar para um determinado tipo de fornecedor.
1.  Na página **Condições de pagamento**, defina as condições de pagamento que você atribui às ordens de venda, ordens de compra, clientes e fornecedores e que determinam as datas de vencimento de fatura. Para obter mais informações, consulte [Definir taxas de pagamento de fornecedor](tasks/define-vendor-payment-fees.md).
2.  Na página **Métodos de pagamento - fornecedores**, crie e mantenha informações sobre como a organização paga seus fornecedores.
3.  Na página **Grupos de fornecedores**, crie e mantenha grupos de fornecedores que compartilham parâmetros importantes referentes a lançamento, liquidação e pagamento, relatórios e previsão.
4.  Na página **Perfis de lançamento de fornecedor**, defina como as transações de fornecedor são lançadas na contabilidade.
5.  Na página **Parâmetros de contas a pagar**, defina as configurações padrão aplicadas na ausência de uma configuração mais específica, os parâmetros para vários tipos de funcionalidades e as diversas sequências numéricas para Contas a pagar.
6.  Na página **Configuração do formulário**, defina o formato de vários documentos relacionados a fornecedores que são usados na organização para rastrear recebimentos de fornecedores e inserir motivos do fluxo de pagamentos aos fornecedores.
7.  Na página **Fornecedores**, crie e mantenha contas de fornecedor e também as autoridades fiscais às quais sua organização declara impostos.

## <a name="optional-setup-pages-for-accounts-payable"></a>Páginas de configuração opcionais de contas a pagar
Além da funcionalidade básica, a sessão de contas a pagar possui outras funcionalidades que você pode configurar.

As páginas de configuração adicional são organizados por funcionalidade.

**Políticas**
-   Na página **Política de fatura de fornecedor**, configure políticas de fatura de fornecedor.

**Conciliação de fatura**

-   Na página **Tolerâncias dos totais de fatura**, configure tolerâncias para os totais de faturas.
-   Na página **Política de conciliação**, configure políticas de conciliação dupla e tripla.
-   Na página **Tolerâncias de preço**, configure tolerâncias para preços unitários.
-   Na página **Grupos de tolerância de preços de item**, configure grupos de tolerância para preços de item.
-   Na página **Grupos de tolerância de preços de fornecedor**, configure grupos de tolerância para preços de fornecedor.
-   Na página **Tolerâncias de encargos**, configure tolerâncias para encargos.

**Fluxo de trabalho**

-   Na página **Fluxos de trabalho de contas a pagar**, defina as configurações de fluxo de trabalho para aprovações de diários e requisições de compra.

**Motivos**

-   Na página **Motivos de fornecedor**, configure os códigos de motivo.

**Encargos**

-   Na página **Código de encargo**, configure os códigos dos encargos usados nas ordens de compra.
-   Na página **Grupo de encargos de fornecedor**, crie e mantenha grupos de encargos para fornecedores.
-   Na página **Grupos de encargos de item**, crie e mantenha grupos de encargos para itens.
-   Na página **Encargos automáticos**, defina os encargos que são atribuídos automaticamente às ordens.

**Itens suplementares**

-   Na página **Grupos de itens complementares - Fornecedor**, crie e mantenha grupos de itens complementadores para fornecedores.
-   Na página **Grupos de itens complementares - Estoque**, crie e mantenha grupos de itens complementadores para itens.

**Distribuição**

-   Na página **Condições de entrega**, crie e mantenha as condições para uma transferência de item do vendedor para o comprador.
-   Na página **Modos de entrega**, crie e mantenha os métodos de transporte usados quando uma ordem é entregue do vendedor ao comprador.
-   Na página **Códigos de destino**, crie e mantenha identificadores e descrições para os destinos de entrega.

**Formulários**

-   Na página **Notas do formulário**, crie o texto padrão exibido em diversas páginas.
-   Na página **Parâmetros de classificação de formulário**, configure a ordem de classificação para requisições, listas de recebimento, guias de remessa e faturas.
-   Na página **Configuração de gerenciamento de impressão**, configure as informações de gerenciamento de impressão para documentos originais e cópias de páginas.

**Pagamentos**

-   Na página **Descontos à vista**, configure e gerencie as condições para a obtenção de descontos à vista. Os códigos de desconto à vista estão associados a fornecedores e são aplicados a ordens de compra.
-   Na página **Planos de pagamento**, configure os planos de pagamento usados para gerenciar pagamentos parcelados para fornecedores.
-   Na página **Dias de pagamento**, defina os dias de pagamento usados para calcular as datas de vencimento e especifique os dias de pagamento para um dia específico da semana ou do mês.
-   Na página **Valor de pagamento**, crie e mantenha os valores de pagamento associados aos fornecedores.
-   Na página **Instrução de pagamento**, crie e mantenha instruções de pagamento.

**Estatísticas**

-   Na página **Definições do período de classificação por vencimento**, configure intervalos definidos pelo usuário para analisar a distribuição de vencimentos de contas de fornecedores.
-   Na página **Linha de negócios**, crie os códigos de linha de negócios (LOB) atribuídos aos fornecedores.

**Imposto 1099**

-   Na página **Campos 1099**, verifique e atualize os valores mínimos que devem ser informados à Administração Fiscal (IRS), com base nos requisitos mais recentes da IRS.

## <a name="optional-setup-for-other-modules"></a>**Configuração opcional para outros módulos**
**Administração da organização**

-   Na página **Sequências numéricas**, configure grupos de sequências numéricas para números de fatura.
-   Nas páginas a seguir, configure as informações de endereço:
    -   **Configuração de endereço**
    -   **Códigos NAF**
    -   **Importar CEPs**

**Contabilidade**

-   Na página **Dimensões financeiras**, configure dimensões financeiras.
-   Nas páginas a seguir, configure as informações de imposto:
    -   **Códigos de imposto**
    -   **Grupos de impostos**
    -   **Grupos de impostos do item**
    -   **Grupo de contas**
    -   **Códigos de isenção do imposto**
    -   **Jurisdições de impostos**
    -   **Autoridades do imposto**
    -   **Períodos de liquidação de imposto**

**Gerenciamento de caixa e bancos**

-   Na página **Códigos de finalidade de pagamento**, configure o **Código de finalidade do Banco Central**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
