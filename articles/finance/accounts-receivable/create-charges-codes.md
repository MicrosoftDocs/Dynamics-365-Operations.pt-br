---
title: Criar códigos de encargos
description: Este artigo explica como configurar códigos de encargos para Contas a pagar e Contas a receber.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MarkupTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d65952cb989672e4eac2dd6101ee9c7c9424daed
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866073"
---
# <a name="create-charges-codes"></a>Criar códigos de encargos

Este artigo explica como configurar códigos de encargos para Contas a pagar e Contas a receber. Se a sua organização exigir que os valores de venda ou de compra sejam acompanhados além dos itens de linha em uma ordem de venda ou de compra, você poderá usar os códigos de encargos diversos para essa finalidade. Por exemplo, é possível pagar o frete e o seguro em uma ordem de compra, e esses valores são especificados separadamente na ordem de compra. Nesse caso, você pode especificar se os valores serão lançados em contas de despesas ou adicionados ao custo dos itens.

## <a name="set-up-charges-codes-for-accounts-receivable"></a>Configurar códigos de encargos para Contas a receber

Para criar códigos de encargos para Contas a receber, siga estas etapas.

1. Acesse **Contas a receber** &gt; **Configuração de encargos** &gt; **Código de encargos**.
2. Selecione **Novo**.
3. No campo **Código de encargos**, insira um código para o encargo.
3. No campo **Descrição**, insira uma descrição do encargo.
4. Opcional: no campo **Grupo de impostos do item**, selecione um grupo de impostos do item.
5. Na Guia Rápida **Lançamento**, especifique como o encargo deverá ser automaticamente debitado e creditado.
6. Se você tiver selecionado **Conta contábil** como o tipo de débito ou crédito, especifique um tipo de lançamento nos campos **Lançamento** e especifique a conta principal nos campos **Conta**.

### <a name="example"></a>Exemplo

O cliente paga o encargo. Portanto, ele é adicionado aos totais da ordem de venda. Você configura as seguintes informações de lançamento:

- No campo **Tipo** da seção **Débito**, selecione **Cliente/Fornecedor** para adicionar o encargo da fatura à conta do cliente.
- No campo **Tipo** da seção **Crédito**, selecione **Conta contábil**. Em seguida, no campo **Conta**, selecione a conta principal para a receita dos encargos da fatura.

> [!NOTE]
> Se o tipo de débito ou tipo de crédito para o código selecionado for **Conta contábil** ou **Item**, você poderá inserir uma moeda diferente para a transação de encargo.

Você pode imprimir o texto para os encargos no idioma atribuído ao cliente. Para especificar o texto para o código de encargos em outros idiomas, selecione **Traduções**.

## <a name="set-up-charges-codes-for-accounts-payable"></a>Configurar códigos de encargos para Contas a pagar

Para criar códigos de encargos para Contas a pagar, siga estas etapas.

1. Siga uma destas etapas:

    - Acesse **Contas a pagar** &gt; **Configuração** **de encargos** &gt; **Código de encargos**.
    - Acesse **Compras e fornecimento** &gt; **Configuração** &gt; **Encargos** &gt; **Código de encargos**.

2. Selecione **Novo**.
3. No campo **Código de encargos**, insira um código para o encargo.
3. No campo **Descrição**, insira uma descrição do encargo.
4. Opcional: no campo **Grupo de impostos do item**, selecione um grupo de impostos do item.
5. Opcional: no campo **Valor máximo**, insira o valor máximo permitido para o código de encargos.

    Esse campo é usado para validar encargos para faturas de fornecedor. Para habilitar a validação de encargos, marque a caixa de seleção **Habilitar a validação da conciliação de faturas** na guia **Validação da fatura** da página **Parâmetros de contas a pagar**.

    > [!IMPORTANT]
    > Para validar encargos para faturas, você também deve criar uma instância de um tipo de regras de política que se baseie em encargos para a política de fatura de fornecedor específica.

6. Na Guia Rápida **Lançamento**, especifique como o encargo deverá ser automaticamente debitado e creditado.
7. Se você tiver selecionado **Conta contábil** como o tipo de débito ou tipo de crédito, especifique um tipo de lançamento nos campos **Lançamento de débito** e **Lançamento de crédito** e especifique a conta principal nos campos **Conta de débito** e **Conta de crédito**.
8. Para permitir a comparação de valores de encargo de uma fatura que contém os encargos das linhas ou do cabeçalho da ordem de compra correspondente, marque a caixa de seleção **Comparar ordem de compra com valores da fatura**.

### <a name="example"></a>Exemplo

Você pode registrar o encargo como uma despesa como parte do total da ordem de compra ou da fatura de fornecedor. Siga estas etapas para configurar as informações de lançamento. 

- No campo **Tipo** da seção **Crédito**, selecione **Cliente/Fornecedor** para adicionar o encargo da fatura à conta do fornecedor.
- No campo **Tipo** da seção **Débito**, selecione **Conta contábil**. Em seguida, no campo **Conta**, selecione a conta principal para as despesas dos encargos da fatura.

Siga estas etapas para configurar as informações de lançamento para que o encargo da unidade seja adicionado ao custo do item.

- No campo **Tipo** da seção **Crédito**, selecione **Cliente/Fornecedor** para adicionar o encargo da fatura à conta do fornecedor.
- No campo **Tipo** na seção **Débito**, selecione **Item** para adicionar o encargo ao custo do item.

> [!NOTE]
> Você poderá usar uma moeda diferente da especificada na ordem de compra ou fatura. Você poderá inserir uma moeda diferente se o tipo de débito ou tipo de crédito do código de encargos selecionado for **Conta contábil** ou **Item**.

Você pode imprimir o texto para os encargos no idioma atribuído ao cliente. Para especificar o texto para o código de encargos em outros idiomas, selecione **Traduções**.
