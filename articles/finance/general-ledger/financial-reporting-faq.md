---
title: Perguntas frequentes sobre relatórios financeiros
description: Este tópico fornece respostas a algumas perguntas frequentes sobre relatórios financeiros.
author: jiwo
ms.date: 07/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd493e855e45362c1681dc9cdfbbcb71f7627d64624cd093eadab32fd966c174
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733602"
---
# <a name="financial-reporting-faq"></a>Perguntas frequentes sobre relatórios financeiros

Este tópico fornece respostas a perguntas frequentes sobre relatórios financeiros.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>Como posso restringir o acesso a um relatório usando a segurança em árvore?

O exemplo a seguir mostra como restringir o acesso a um relatório usando a segurança em árvore.

A empresa de demonstração USMF tem um relatório de **Balanço** ao qual nem todos os usuários do relatório financeiro devem ter acesso. Você pode usar a segurança em árvore para restringir o acesso a um único relatório, de modo que somente usuários específicos possam acessá-lo.

1. Entre no Financial Reporter Report Designer.
2. Selecione **Arquivo \> Novo \> Definição em árvore** para criar uma definição em árvore.
3. Toque (ou clique) duas vezes na linha **Resumo** na coluna **Segurança da unidade**.
4. Selecione **Usuários e Grupos**.
5. Selecione os usuários ou os grupos que precisam acessar o relatório.
6. Selecione **Salvar**.
7. Na definição de relatório, adicione sua nova definição em árvore.
8. Na definição em árvore, selecione **Configuração**. Em **Seleção de unidade organizacional**, selecione **Incluir todas as unidades**.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>Como posso identificar quais contas não correspondem aos meus saldos?

Se você tiver um relatório que não tem saldos correspondentes, use os procedimentos a seguir para identificar cada conta e variação.

### <a name="in-financial-reporter-report-designer"></a>No Financial Reporter Report Designer

1. Crie uma definição de linha.
2. Selecione **Editar \> Inserir Linhas de Dimensões**.
3. Selecione **MainAccount**.
4. Selecione **OK**.
5. Salve a definição de linha.
6. Crie uma definição de coluna.
7. Crie uma definição de relatório.
8. Selecione **Configurações** e desmarque esta opção.
9. Gere o relatório. 
10. Exporte o relatório para o Microsoft Excel.

### <a name="in-dynamics-365-finance"></a>No Dynamics 365 Finance

1. Vá para **Contabilidade \> Consultas e Relatórios \> Balancete**.
2. Defina os seguintes campos:

    - **Data de Início** – insira a data de início do ano fiscal.
    - **Data de Término** – insira a data para a qual você está gerando o relatório.
    - **Dimensão Financeira** – defina este campo como **Conta principal definida**.

3. Selecione **Calcular**.
4. Exporte o relatório para o Excel.

Agora, você poderá copiar os dados do relatório do Excel do Financial Reporter para o relatório de **Balancete** a fim de comparar as colunas **Saldo de fechamento**.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Ao criar um relatório no Report Designer ou gerar um relatório financeiro, recebo a seguinte mensagem: "Não foi possível concluir a operação devido a um problema na estrutura do provedor de dados". Como devo responder?

A mensagem indica que ocorreu um problema quando o sistema tentou recuperar metadados financeiros do data mart enquanto você estava usando relatórios financeiros. Há duas maneiras de responder a esse problema:

- Revise o status da integração dos dados em **Ferramentas \> Status da integração** no Report Designer. Se a integração estiver incompleta, aguarde sua conclusão. Em seguida, repita o que você estava fazendo quando recebeu a mensagem.
- Contate o suporte para identificar e solucionar o problema. Pode haver dados inconsistentes no sistema. Os engenheiros de suporte podem ajudar você a identificar esse problema no servidor e encontrar os dados específicos que podem exigir uma atualização.

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>Como a seleção da conversão da taxa histórica afeta o desempenho do relatório?

A taxa histórica geralmente é usada com ganhos retidos, propriedades, plantas, equipamentos e contas de capital próprio. A taxa histórica pode ser necessária, com base nas diretrizes da Financial Accounting Standards Board (FASB) ou nos princípios contábeis geralmente aceitos (GAAP). Para obter mais informações, consulte [recursos de moeda em relatórios financeiros](financial-reporting-currency-capability.md).

## <a name="how-many-types-of-currency-rate-are-there"></a>Quantos tipos de taxa de moeda existem?

Há três tipos:

- **Taxa atual** – esse tipo geralmente é usado com contas de balanço. Em geral, é conhecido como *taxa de câmbio pontual* e pode ser a taxa no último dia do mês ou em outra data predeterminada.
- **Taxa média** – normalmente, este tipo é usado com contas de demonstrativo de renda (lucros/perdas). Você pode configurar a taxa média para fazer uma média simples ou uma média ponderada.
- **Taxa histórica** – geralmente é usada com ganhos retidos, propriedades, plantas, equipamentos e contas de capital próprio. Essas contas podem ser necessárias, com base nas diretrizes FASB ou GAAP.

## <a name="how-does-historical-currency-translation-work"></a>Como funcionam as conversões históricas da moeda?

As taxas são específicas da data da transação. Portanto, cada transação é convertida individualmente, com base na taxa de câmbio mais próxima.

Para a conversão de moeda histórica, os saldos do período previamente calculado podem ser usados em vez de detalhes da conversão individual. Esse comportamento é diferente do comportamento da conversão da taxa atual.

## <a name="how-does-historical-currency-translation-affect-performance"></a>Como as conversões históricas da moeda afetam o desempenho?

Quando os dados apresentados nos relatórios são atualizados, pode haver um atraso porque os valores devem ser recalculados com a verificação dos detalhes da transação. Esse atraso ocorre toda vez que as taxas são atualizadas ou mais transações são lançadas. Por exemplo, se milhares de contas estiverem configuradas para a conversão histórica uma vez por dia, pode haver um atraso de até uma hora antes que os dados no relatório sejam atualizados. Por outro lado, se houver um número menor de contas específicas, os tempos de processamento das atualizações para os dados do relatório podem ser reduzidos para minutos ou menos.

Da mesma forma, quando os relatórios são gerados usando a conversão de moeda para contas de tipo históricas, haverá cálculos extra por transação. Dependendo do número de contas, o tempo de geração do relatório pode duplicar.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
