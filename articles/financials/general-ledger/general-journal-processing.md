---
title: "Processamento do diário geral"
description: "Este artigos descrevem os recursos do Microsoft Dynamics 365 for Finance and Operations que podem ajudar a facilitar o processamento de diário geral e que também pode ajudar a garantir que os dados corretos são capturados e o controle interno não está comprometido."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: eb46613f805999753c2ab73ffb91a6fdae04c68e
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="general-journal-processing"></a>Processamento do diário geral

[!include[banner](../includes/banner.md)]


Este artigos descrevem os recursos do Microsoft Dynamics 365 for Finance and Operations que podem ajudar a facilitar o processamento de diário geral e que também pode ajudar a garantir que os dados corretos são capturados e o controle interno não está comprometido.  

Nomes de diário

Uma das áreas mais importantes para a configuração é nomes de diário. Convém definir nomes do diário específicos para cada objetivo, como ajuste intercompanhia, acumulado e correção de erro. Você pode personalizar cada nome de diário para ajudar a tornar a entrada de dados fácil e segura para cada objetivo. 

Na página **Nomes de diário**, você pode configurar os seguintes elementos:

-   **Aprovação do fluxo de trabalho** – Para aumentar o controle interno, defina fluxos de trabalho do diário que estabeleçam limites de materialidade para as etapas de análise e aprovação, com base em critérios como o valor de débito total. Você configura fluxos de trabalho para os diários gerais na página **Fluxos de trabalho de contabilidade**.
-   **Valores padrão** – Selecione valores padrão para contrapartidas, moeda e dimensões financeiras.
-   **Controle de diário** – Você pode configurar restrições da empresa e o tipo de conta, e também os valores do segmento. 

**Exemplos**

Um nome de diário pode ser usado somente para ajustes. Nesse caso, você pode especificar qual apenas o tipo de conta **Razão** é válido em todas as empresas. [![Tipos de contas de controle de diário](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

Um nome de diário pode ser usado somente para um segmento específico ou para um intervalo de contas principais. [![Segmento de controle de diário](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

A opção **Estorno automático** está disponível em diários gerais. Por exemplo, você tem um ajuste de competência em que o documento real ainda não foi processado, conforme mostrado na ilustração.
[![Processamento do Diário geral](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

O suplemento do Microsoft Excel para a entrada de diário fornece um nível adicional de automação e facilita a entrada de dados. A ação **Abrir linhas no Excel** está disponível nas páginas **Diário geral** e **Comprovante de diário**. 

Na página **Diários periódicos**, você pode configurar diários de devolução para automatizar o processamento do diário. 

Você pode usar modelos de comprovante a qualquer momento. Na página **Diários gerais**, as ações **Salvar** e **Selecionar modelo de comprovante** estão na página **Comprovante de diário**, em **Funções** para as linhas do comprovante.

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

Para obter mais informações, consulte os seguintes tópicos:
- [Planejamento: plano de contas](plan-chart-of-accounts.md) 
- [Criar regras avançadas para diários](tasks/create-advanced-rules-journals.md)
- [Criar uma entrada de diário usando um modelo](tasks/create-journal-entry-template.md)
- [Criar e validar diários](tasks/create-validate-journals.md)
- [Lançar diários periódicos](tasks/post-periodic-journals.md)
- [Processar diário de alocação do razão](tasks/process-ledger-allocation-journal.md)



