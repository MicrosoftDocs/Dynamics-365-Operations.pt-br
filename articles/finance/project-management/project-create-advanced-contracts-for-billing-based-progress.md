---
title: Criar contratos avançados para cobrança com base no progresso
description: Este tópico explica como criar contratos de projeto para que você possa gerar notas fiscais para clientes com base em uma porcentagem de trabalho concluído.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282811"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a>Criar contratos avançados para cobrança com base no progresso
[!include [banner](../includes/banner.md)]

Este tópico explica como criar contratos de projeto para que você possa criar notas fiscais para clientes com base em uma porcentagem de trabalho concluído. Os valores de fatura são calculados automaticamente para as categorias de orçamento do trabalho que você configurou para um projeto. A hora da fatura é configurada quando você negocia o contrato do projeto com o cliente.

Use os procedimentos neste tópico para configurar um contrato, um projeto associado e as regras de cobrança que calculam os valores da fatura para as categorias de orçamento do trabalho configuradas para o projeto.

Após criar o contrato e o projeto, você poderá configurar os detalhes do projeto. Por exemplo, você pode definir as atividades e atribuir trabalhadores ao projeto.

## <a name="example"></a>Exemplo

Sua organização é uma empresa de desenvolvimento de software. Você concorda em desenvolver um pacote de contabilidade de folha de pagamento para um cliente por uma tarifa total de US$ 20.000. A organização concorda em enviar uma fatura para o cliente ao concluir porcentagens específicas do projeto. Configure as seguintes categorias de projeto para o trabalho, de forma que possa usá-las no processo de cobrança:

- Consultoria
- Design
- Instalação

Você também configura regras de cobrança que calculam automaticamente os valores da fatura pelo percentual de trabalho do projeto que é concluído em cada categoria.

O gerente de orçamento cria um orçamento para as categorias de projeto. O valor do trabalho de concluído é calculado automaticamente como uma porcentagem de trabalho real comparado com os valores orçados.

## <a name="prerequisites"></a>Pré-requisitos

Antes de criar um projeto que use regras de cobrança, você deve configurar as sequências numéricas para regras de cobrança e um diário de taxas usado para lançar cobranças de andamento.

1. Vá para **Gerenciamento e contabilidade de projeto** \> **Configuração** \> **Parâmetros de gerenciamento e contabilidade de projetos**.
2. Na página **Parâmetros de gerenciamento e contabilidade de projetos**, na guia **Sequências numéricas**, configure a sequência numérica que você deseja usar ao criar regras de cobrança.
3. Vá para **Gerenciamento e contabilidade de projetos** \> **Diários** \> **Taxa**.
4. Na página **Diário de taxas**, selecione **Novo** e insira o nome do diário.

## <a name="create-a-contract-for-progress-billings"></a>Criar um contrato de cobrança parciais

Use este procedimento para criar um contrato de projeto para um projeto de preço fixo. Você cria uma fatura do projeto quando o trabalho concluído no projeto atinge uma porcentagem específica.

1. Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Contratos do projeto**.
2. Na página **Contratos do projeto**, selecione **Novo**.
3. Na caixa de diálogo **Novo contrato de projeto**, defina os seguintes campos:

    - **Nome**
    - **Tipo de financiamento**
    - **Fonte de financiamento**
    - **Moeda de venda** – Por padrão, essa moeda é usada para todas as faturas de cliente associadas ao contrato de projeto. No entanto, é possível modificar a moeda de venda para uma fatura de cliente específica.

4. Selecione **OK**. As informações são copiadas para o cabeçalho da página **Contratos do projeto**.
5. Na página **Contratos do projeto**, preencha o restante das informações necessárias para o projeto.

## <a name="create-a-project-for-progress-billings"></a>Criar um projeto para cobrança parciais

Siga estas etapas para criar um projeto e quaisquer subprojetos associados a um contrato de projeto.

1. Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos**.
2. Na página **Todos os projetos** , selecione **Novo**.
3. Na caixa de diálogo **Novo projeto**, no campo **Tipo de projeto**, selecione **Hora e material**.
4. Selecione um grupo de projetos. Um grupo de projetos define as informações de lançamento para os projetos atribuídos ao grupo.
5. Selecione **Criar projeto**.
6. Depois de criar o projeto, defina a fase do projeto para **Em andamento**.

## <a name="create-a-budget-for-a-project"></a>Crie um orçamento para um projeto.

As categorias de orçamento são usadas para calcular automaticamente os valores para faturar pelo percentual de trabalho que foi concluído para cada categoria. Siga estas etapas para criar categorias de orçamento para os custos previstos.

1. Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos**.
2. Na página **Todos os projetos**, selecione e abra o projeto desejado.
3. Na página **Projetos**, no Painel de Ações, na guia **Plano**, no grupo **Orçamento**, selecione **Orçamento do projeto**.
4. Na página **Orçamento do projeto**, insira um custo estimado para cada categoria no projeto.

## <a name="create-billing-rules-for-progress-billings"></a>Criar regras de cobrança para cobrança parciais

1. Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Contratos do projeto**.
2. Na página **Contratos do projeto**, selecione e abra um contrato de projeto.
3. Na página contrato de projeto, na Guia Rápida **Regras de cobrança**, selecione **Adicionar**.
4. Na página **Regra de cobrança**, no campo **Tipo de linha**, selecione **Em andamento**.
5. Na Guia Rápida **Detalhes da linha de regra de cobrança**, no campo **Valor de contrato**, insira o valor total do contrato.
6. No campo **Categoria**, selecione a categoria na qual lançar a transação de taxa.
7. No campo **Projeto**, selecione o projeto que usa essa regra de cobrança.
8. Opcional: Atribuir a regra de cobrança a projetos adicionais. Na Guia Rápida **Projeto**, na seção **Projetos disponíveis**, selecione um projeto e, em seguida, selecione o botão de seta para a direita para adicionar o projeto à seção **Projetos selecionados**.
9. Opcional: Calcular a o valor da porcentagem que o cliente retém dos pagamentos em uma fatura. Na Guia Rápida **Termos de retenção de pagamento**, selecione a fonte de financiamento e, em seguida, no campo **Porcentagem de retenção**, insira a porcentagem de retenção.
10. Repita essas etapas para criar regras adicionais de cobrança para o contrato de projeto.
