---
title: "Processamento do diário geral"
description: "Este artigos descrevem os recursos do Microsoft Dynamics 365 para as operações que podem ajudar a facilitar processar geral de diário, e também que podem ajudar a garantir que os dados corretos estão capturados e o controle interno não for o compromisso."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 50cd203025be8857de943e458fc32315e494fb7a
ms.lasthandoff: 03/31/2017


---

# <a name="general-journal-processing"></a>Processamento do diário geral

Este artigos descrevem os recursos do Microsoft Dynamics AX que podem ajudar a facilitar o processamento de diário geral e que também pode ajudar a garantir que os dados corretos são capturados e o controle interno não está comprometido.  

Nomes de diário

Uma das áreas mais importantes para a configuração de nomes de diário. Convém definir nomes do diário para cada objetivo, como ajuste intercompanhia, acumulado, e o de correção de erros. Você pode personalizar cada nome de diário para ajudar a tornar a entrada de dados para cada objetivo fácil e seguro. 

Na página **Nomes de diário**, você pode configurar os seguintes elementos:

-   **Aprovação do fluxo de trabalho** – Para aumentar o controle interno, defina fluxos de trabalho do diário que estabeleçam limites de materialidade para as etapas de análise e aprovação, com base em critérios como o valor de débito total. Você fluxos de trabalho configuradas para os diários gerais ** fluxos de trabalho da contabilidade ** na página.
-   **Valores padrão** – Selecione valores padrão para contrapartidas, moeda e dimensões financeiras.
-   **Controle de diário** – Você pode configurar restrições da empresa e o tipo de conta, e também os valores do segmento. 

**Exemplos**

Um nome de diário pode ser usado somente para ajustes. Nesse caso, você pode especificar qual apenas o tipo de conta **Razão** é válido em todas as empresas. [tipos de conta de controle de diário do![(]. /media/journal-control-account-types1.png)](. /media/journal-control-account-types1.png)

Um nome de diário pode ser usado somente para um segmento específico ou para um intervalo de contas principais. [segmento de controle de diário do![(]. /media/journal-control-segment1.png)](. /media/journal-control-segment1.png)

A opção **Estorno automático** está disponível em diários gerais. Por exemplo, você tem um ajuste de competência em que o documento real ainda não foi processado, conforme mostrado na ilustração.
[diário geral![que reverter (]. /media/general-journal-reversing1.png)](. /media/general-journal-reversing1.png) 

O manuais suplementam o Microsoft Excel para entrada de diário fornece um nível adicional de automação e facilita a entrada de dados. A ação **Abrir linhas no Excel ** está disponível nas páginas **Diário geral** e **Comprovante de diário**. 

Na página **Diários periódicos**, você pode configurar diários de devolução para automatizar o processamento do diário. 

Você pode usar modelos de comprovante a qualquer momento. ** Diários gerais ** na página, e salvar ** ** ** modelo de comprovante ** selecione as ações são localizadas ** ** comprovante de diário na página, abaixo ** funções ** comprovante para a linha.

## <a name="related-setup"></a>Configuração relacionada
A configuração a seguir não é específica de diários gerais, mas ajudará a garantir que a entrada de dados seja fácil e com dados corretos.

### <a name="main-account"></a>Conta principal

A configuração da conta principal fornece várias opções para o processamento do diário geral:

-   **Necessidade de DC/CR** – Use esta opção se uma conta principal for limitada a transações de débito ou de crédito. A configuração é verificada quando um diário é validado ou lançado.
-   **Contrapartida padrão**
-   **Suspenso** – Suspender um conta principal para a entrada de dados em todas as empresas ou para uma empresa específica/entidades legais.
-   **Não permitir entrada manual** – Impedir que usuários insiram manualmente um valor para a conta em diários.
-   **Padrão/Validar moeda**
-   **Substituição da entidade legal** – Esta configuração é específica da empresa/entidade legal definida:
    -   **Padrão/Validar imposto**
    -   **Dimensão padrão** – **Não fixo** ou **Valor fixo**. **Valor fixo** ajudará a garantir que todas as postagens para esta conta principal usem sempre um valor de dimensão configurado como **Fixo**.
-   **Validação de lançamento**
    -   **Validação do usuário** – Esta opção controla quais usuários têm permissão para lançar em uma conta principal.
    -   **Validação de tipo de lançamento** – Esta opção controla os tipos de lançamento com permissão para uma conta principal.

### <a name="accounting-structures-and-advanced-rules-structures"></a>Estruturas de contabilidade e estruturas de regras avançadas

As estruturas de contabilidade e as estruturas de regras avançadas são muito importantes para garantir que os dados necessários para relatórios financeiros e rastreamento de desempenho sejam capturados durante o processamento do diário geral e em qualquer outra documentação. As estruturas de contabilidade e as estruturas de regras avançadas permitem personalizar a experiência da entrada de dados. Você pode permitir a entrada de dados somente para as dimensões financeiras que são relevantes para cada situação, e também pode forçar a exigência de captura de dados obrigatórios e corretos.

Para obter mais informações, consulte: [planejamento Plano de contas (plan-chart-of-accounts.md]). 


