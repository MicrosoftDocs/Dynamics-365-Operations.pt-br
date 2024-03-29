---
title: Testes independentes de dados usando a Regression Suite Automation Tool
description: Este artigo discute as recomendações para testes independentes de dados usando a Regression Suite Automation Tool.
author: FrankDahl
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.custom: 21761
ms.openlocfilehash: f4322cb76d1d83c02ec9d4dcb997a1cd4730d090
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269581"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Testes independentes de dados usando a Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

Embora a validação funcional de um aplicativo ERP não possa ser totalmente independente de dados, há várias fases e abordagens para teste. Essas fases de teste incluem:  

- Estrutura SysTest
- Estrutura ATL
- RSAT (Regression Suite Automation Tool)

[![Pirâmide de classificação de teste.](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Visão Geral
-   **Estrutura SysTest** – A estrutura SysTest é confiável para gravação de testes de unidade. Como os testes de unidade geralmente testam um método ou uma função, eles sempre devem ser independentes de dados e dependentes apenas dos dados de entrada que são fornecidos como parte do teste.
-   **Estrutura ATL** – A Microsoft tem uma estrutura ATL que é uma abstração da estrutura SysTest e torna a gravação do teste funcional muito mais simples e confiável. Essa estrutura deve ser usada para gravar testes de componente ou testes simples de integração.
-   **RSAT** – O RSAT é usado para testes de integração e testes de ciclo comercial. Os testes de ciclo comercial, também chamados de testes de validação de regressão, dependem dos dados existentes. Entretanto, esses testes podem se tornar independentes de dados se você considerar fatores adicionais. 

    - o Onde os testes de unidade e testes de componente forem de nível baixo e puderem ser totalmente independentes de dados (não dependentes de conjuntos de dados existentes), os testes de ciclo comercial ou de validação de regressão dependerão de alguns dados existentes. Esses dados incluem definições de instalação, configuração (parâmetros) e dados mestres (cliente, fornecedores, itens, etc.), mas nunca dados de transação. Certifique-se de que durante o teste, se algum deles estiver sendo alterado, que sejam revertidos como parte do teste final.
    - Selecione os dados mestres com base em determinados critérios em vez de selecionar um registro específico. Por exemplo, se desejar selecionar um item com base nos valores de sua própria dimensão e disponibilidade de estoque, filtre a lista de produtos com esses valores, selecione o primeiro item e copie o número a ser usado para testes futuros. Se for uma linha simples de dados mestres, como cliente, fornecedor ou item, ele poderá ser criado como parte da automação e usado em futuros testes pelo encadeamento. 
    - o Informe os identificadores exclusivos, como números de fatura, por sequência numérica ou usando as funções do Microsoft Excel, como =TEXT(NOW(),"yyyymmddhhmm"). Essa função fornecerá um número exclusivo a cada minuto, o que permite rastrear quando a ação aconteceu. Isso pode ser usado para variáveis, como números de recebimento de produto e números de fatura do fornecedor. Esses testes continuam trabalhando no mesmo banco de dados repetidas vezes, sem exigir qualquer restauração.
    - Sempre defina o **Modo de edição** do ambiente para **Leitura** ou **Edição** como o primeiro caso de teste, pois a opção padrão é **Automático**. As opções **Automático** sempre usam a configuração anterior e podem gerar testes não confiáveis. 
 
    [![Página Opções, guia Desempenho.](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Valide apenas depois que você filtrar por uma determinada transação, e não por validação genérica. Por exemplo, para o número de registros, filtre pelo número da transação ou pela data da transação para que a validação exclua todas as outras transações. 
    - Se você estiver verificando o saldo ou controle orçamentário de um cliente, salve o valor primeiro e, em seguida, adicione o valor de transação para validar o resultado esperado em vez de validar um valor fixo esperado. 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
