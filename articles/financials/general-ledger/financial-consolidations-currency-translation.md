---
title: Consolidações financeiras e conversão de moeda
description: Este tópico descreve as consolidações financeiras e a conversão de moeda na contabilidade.
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 8427d53bac3216d362b2bf8983a847f069351b3b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559963"
---
# <a name="financial-consolidations-and-currency-translation"></a>Consolidações financeiras e conversão de moeda

[!include [banner](../includes/banner.md)]

Esse tópico conduz você na abordagem que o Microsoft Dynamics 365 for Finance and Operations e os relatórios financeiros usam para consolidações. Ele descreve cenários que envolvem relatórios, agregação, eliminação e interesses minoritários de várias empresas. Ele também explica como lidar com situações especiais, como cenários em que entidades legais têm diferentes períodos fiscais ou diferentes planos de contas.

Este tópico foi escrito para usuários e consultores funcionais e presume que os leitores tenham um entendimento geral de Finance and Operations e Relatório financeiro. A configuração básica não é abordada.

> [!NOTE]
> O termo *entidade legal* é usado no Finance and Operations e o termo *empresa* é usado no Relatório financeiro. Ambos os termos são usados neste tópico. Contudo, para os fins deste tópico, seus significados são os mesmos.

## <a name="audience"></a>Público-alvo
Este tópico é destinado a usuários de finanças e contabilidade e consultores de aplicativos que desejam usar o Finance and Operations e Relatório financeiro para consolidar dados de várias empresas e várias moedas.

## <a name="approach"></a>Abordagem
O Finance and Operations usa uma entidade legal separada para processar uma consolidação. Ele permite a consolidação de instância única, mas fornece uma opção para trazer dados de outras fontes. O processo de consolidação deve ser executado sempre que forem realizadas alterações nas entidades legais de origem.

O Relatório financeiro pode consolidar várias empresas durante a geração de relatórios. Embora os dados sejam armazenados em um data mart, sejam versionados e possam ser exportados, toda empresa de origem é o proprietário e o contêiner dos dados. O relatório pode ser executado a qualquer momento, até mesmo a cada minuto (por exemplo). Ele oferece muitos benefícios adicionais, como a capacidade de fazer uma busca detalhada em todas as empresas e dimensões.

Os usuários podem usar Consolidar Online, Relatório financeiro ou uma combinação. A escolha dependerá das necessidades da sua empresa e das preferências de seus auditores.

## <a name="consolidations"></a>Consolidações
O módulo **Consolidações** inclui opções para consolidar várias entidades legais durante o processo de consolidação e para importar ou exportar o saldo de uma empresa. Você também pode configurar eliminações e lançar diários de eliminação.

## <a name="benefits-of-using-consolidate-online"></a>Benefícios ao usar o Consolidar online
Clientes usando o módulo **Consolidações** receberão vários benefícios:

- **Profundidade de dados** – Você pode criar relatórios consolidados que reúnem dados reais e de orçamento no nível da conta e no nível da dimensão.
- **Consolidações dinâmicas** – As consolidações podem ser processadas várias vezes.
- **Recursos de auditoria** – Dimensões e contas são mantidas para análise e auditoria, e os saldos são criados por data.
- **Conversão de moeda** – Você pode configurar os intervalos e as taxas da conta para conversão da moeda contábil da empresa de origem para a moeda contábil da empresa de consolidação.
- **Eliminações de processo em uma empresa consolidada ou de eliminação** – Você pode processar e lançar eliminações como um único processo durante a consolidação. Como alternativa, você pode executar uma proposta separadamente.

## <a name="supported-consolidation-scenarios"></a>Cenários de consolidação compatíveis
Aqui estão alguns dos cenários de consolidação que o Consolidar online permite:

- Consolidações de nível único em entidades legais
- Consolidações que envolvem eliminações
- Participação minoritária (para este cenário, o cálculo manual e a entrada na empresa devem ser usados.)
- Vários gráficos de contas em entidades legais
- Calendários fiscais diferentes em várias entidades legais
- Consolidações que envolvem várias moedas de relatório

## <a name="legal-entity-setup"></a>Configuração de entidade legal
Antes de processar uma consolidação, você deve configurar a entidade legal. Você pode executar a consolidação quantas vezes precisar e todos os dados serão convertidos da moeda contábil da empresa de origem para a moeda definida para a empresa de consolidação. Portanto, para a estrutura organizacional a seguir, se você precisar converter todas as empresas norte-americanas primeiro em dólares americanos (USD) e depois em euros (EUR), a moeda da empresa principal, você deve ter pelo menos duas empresas de consolidação.

![Estrutura organizacional](./media/organizational-structure.png "Estrutura organizacional")

Na estrutura organizacional anterior, você deve ter uma entidade legal para a consolidação na América do Norte, porque as consolidações sempre se consolidam da moeda contábil da empresa de origem para a moeda da empresa de consolidação. No exemplo, se todas as empresas estiverem incluídas em uma única consolidação, a subsidiária mexicana será convertida de pesos mexicanos (MXN) para EUR, não de MXN para USD para EUR.

Ao criar a entidade legal, você pode especificar se a empresa é usada para o processo de consolidação e o processo de eliminação ou para apenas um desses processos. Na ilustração a seguir, a empresa é usada para ambos os processos. Observe que você não pode lançar diários em uma empresa de consolidação, mas pode publicá-los em uma empresa de eliminação. Portanto, você pode querer ter uma empresa de eliminação separada.

![Entidade legal usada para consolidação e eliminação](./media/sep-elimination-company.png "Entidade legal usada para consolidação e eliminação")

## <a name="main-accounts-and-consolidation-account-groups"></a>Contas principais e grupos de contas de consolidação
É preciso escolher como deseja consolidar seu plano de contas. Durante o processo de consolidação, você tem três opções para consolidar as contas principais.

A primeira opção é usar as contas principais das empresas de origem. Nesse caso, todas as contas de todas as empresas serão consolidadas. Por exemplo, se Pagamento à vista for a conta 100000 na empresa USMF e a conta 1100 na empresa DEMF, a empresa de consolidação incluirá as duas contas. Cada conta terá seu respectivo saldo.

A segunda opção é especificar uma conta de consolidação padrão na página **Contas principais**. A conta será então mapeada para a conta de consolidação. Essa opção pode ser útil quando você tem diferentes planos de contas ou precisa mapear para um gráfico definido pela matriz.

![Conta de consolidação padrão especificada na página Contas principais](./media/main-accounts.png "Conta de consolidação padrão especificada na página Contas principais")

A terceira opção é usar grupos de contas de consolidação. Você pode definir quantos grupos de contas de consolidação forem necessários. Depois, na página **Contas de consolidação adicionais**, basta mapear a conta principal do plano de contas para a conta que você precisa para esse grupo.

![Mapeamento na página Contas de consolidação adicionais](./media/additional-consolidation-accounts.png "Mapeamento na página Contas de consolidação adicionais")

## <a name="consolidating-online"></a>Consolidação online
Para saber como inserir detalhes de consolidações online, consulte [Consolidar online](./consolidate-online.md).

## <a name="managing-consolidation-transactions"></a>Gerenciamento de transações de consolidação
Para exibir os resultados da consolidação, você tem várias opções:

- Gere um relatório financeiro em relação à empresa de consolidação.
- Revise a lista **Balancete** na empresa de consolidação.
- Na lista de transações de consolidação na página **Consolidações**, exiba os saldos criados por data para cada empresa de origem para cada período.

    ![Transações de consolidação na página Consolidações](./media/managing-consolidation-transactions.png "Transações de consolidação na página Consolidações")

Para executar a consolidação novamente, basta processar a consolidação. Como alternativa, você pode primeiro selecionar **Remover as transações** na página **Consolidações**.

## <a name="consolidate-with-import"></a>Consolidar com importação
A funcionalidade Consolidar com importação funciona como a funcionalidade Consolidar online. Quando você seleciona as entidades legais, você navega até o arquivo de origem que contém os dados.

## <a name="export-company-balances"></a>Exportar saldos da empresa
A funcionalidade Exportar saldos da empresa também funciona como a funcionalidade Consolidar online. Ao selecionar as entidades legais, você definirá um caminho de arquivo para a saída.

## <a name="elimination-rules"></a>Regras de eliminação
Para eliminar transações intercompanhia, você pode criar uma regra de eliminação. Como alternativa, você pode fazer uma entrada de eliminação manual em uma empresa designada como uma empresa de eliminação. Se criar uma regra de eliminação, você terá duas opções para o método de eliminação: **Alteração líquida** e **Fixo**.

### <a name="set-up-elimination-rules"></a>Configurar regras de eliminação
Ao configurar regras de eliminação no Finance and Operations, você pode criar uma dimensão financeira que é usada especificamente para eliminação. A maioria dos clientes nomeia essa dimensão financeira de **Parceiro comercial** ou algo semelhante. Se optar por não usar uma dimensão financeira, certifique-se de ter contas principais usadas apenas para transações intercompanhia.

Você pode encontrar a configuração para as eliminações na área **Configuração** do módulo **Consolidações**. Depois de digitar uma descrição para a regra, escolha a empresa na qual o diário de eliminação será lançado. A empresa escolhida deve ter a opção **Usar para o processo de eliminação financeira** selecionada na configuração da entidade legal.

Você pode definir a data em que a regra de eliminação entra em vigor e a data em que ela expira, conforme necessário. Se quiser que a regra de eliminação esteja disponível no processo de proposta de eliminação, você deve definir a opção **Ativo** como **Sim**. Selecione um nome de diário do tipo **Eliminação**.

![Propriedades básicas de uma regra de eliminação](./media/ledger-elimination-rule-journal.png "Propriedades básicas de uma regra de eliminação")

Após a definição das propriedades básicas, selecione **Linhas** para definir as regras de processamento reais. Há duas opções para eliminações: eliminar o valor líquido de modificação ou definir um valor fixo.

Selecione as contas de origem. Você pode usar asterisco (\*) como um caractere curinga. Por exemplo, **1\*** seleciona todas as contas que começam com **1** como a fonte de dados da alocação.

Após a seleção das contas de origem, use o campo **Especificação da conta** para especificar a conta usada na empresa de destino. Selecione **Origem** para usar a mesma conta principal definida na conta de origem. Se você selecionar **Definido pelo usuário**, deverá especificar a conta de destino.

![Página Linha da regra de eliminação do razão](./media/ledger-elimination-rule-line.png "Página Linha da regra de eliminação do razão")

O campo **Especificação da dimensão** funciona como o campo **Especificação da conta**. Selecione **Origem** para usar as mesmas dimensões da empresa de destino e da empresa de origem. Se você selecionar **Definido pelo usuário**, será necessário especificar as dimensões da empresa de destino, selecionando **Dimensões de destino**. Depois selecione as dimensões de origem e as dimensões financeiras e os valores usados como a fonte de eliminação.

### <a name="process-elimination-transactions"></a>Processar transações de eliminação
Existem duas maneiras de processar transações de eliminação. A transação pode ser processada durante o processo Consolidar online ou você pode criar um diário de eliminação e executar o processo de proposta de eliminação. Esta seção concentra-se na segunda opção.

Em uma empresa definida como empresa de eliminação, selecione **Diário de eliminação** no módulo **Consolidações**. Depois de selecionado o nome do diário, selecione **Linhas**. Para executar a proposta, selecione **Propostas** \> **Proposta de eliminação**.

Selecione a empresa que é a origem de dados consolidados e depois selecione a regra a ser processada. Insira as datas de início e término para definir o intervalo de datas que é procurado pelos valores de eliminação. O campo **Data de lançamento GL** especifica a data usada para lançar o diário na contabilidade. Após selecionar **OK**, você pode revisar os valores e lançar no diário.

> [!NOTE]
> O diário de eliminação mostra as quantidades dos valores cumulativos na moeda de suas transações originárias, não na moeda contábil. Ao revisar os valores no diário de eliminação, você pode achar esse comportamento confuso.

Para obter mais informações e exemplos, consulte [Regras de eliminação](./elimination-rules.md).

## <a name="currency-revaluation-in-a-consolidation-company"></a>​Reavaliação de moeda em uma empresa de consolidação​
Após consolidar dados de uma moeda contábil para outra, você ainda deverá executar a reavaliação de moeda se houver uma alteração em taxas de câmbio, de forma que os saldos da conta sejam reavaliados corretamente. Ao consolidar originalmente os dados, use a guia **Conversão de moeda** para selecionar as taxas de câmbio iniciais que devem ser usadas para conversão durante o processo de consolidação. Após inserir uma nova taxa de câmbio (por exemplo, no mês seguinte), você deve reavaliar os saldos da conta. Os lucros não realizados ou as perdas são atualizados, com base na nova taxa de câmbio e data.

Para obter mais informações sobre a reavaliação de moeda em uma empresa de consolidação, consulte [Reavaliação de moeda em uma empresa de consolidação](currency-revaluation-consolidation-company.md).

Para mais informações sobre como a reavaliação de moeda funciona no módulo **Contabilidade**, consulte [Reavaliação de moeda estrangeira para contabilidade](./foreign-currency-revaluation-general-ledger.md).

### <a name="additional-information"></a>Informações Adicionais
- Todos os níveis de lançamento são consolidados quando a consolidação é processada.
- Os diários de eliminação podem ser lançados apenas no nível Atual.
- Apenas os saldos operacionais são consolidados. Portanto, para ver os saldos iniciais, você ainda deve executar um fechamento de exercício na empresa de consolidação.
- Você pode lançar um diário em uma empresa de eliminação, mas não em uma empresa de consolidação.

## <a name="benefits-of-using-financial-reporting-for-financial-consolidations-and-currency-translation-or-to-complement-consolidate-online-for-consolidated-reporting"></a>Benefícios ao usar o Relatório financeiro para consolidações financeiras e conversão de moeda ou para complementar Consolidar online para relatórios consolidados
Os clientes que usam o Relatório financeiro para consolidações financeiras e conversão de moeda ou para complementar Consolidar online para relatórios consolidados receberão vários benefícios:

- **Profundidade de dados** – Você pode criar relatórios consolidados que reúnem dados reais e de orçamento no nível da conta e no nível da dimensão. No caso do Finance and Operations, esses dados incluem dados do controle de orçamento e do planejamento de orçamento.
- **Consolidações dinâmicas** – As consolidações podem ser realizadas a qualquer momento e em qualquer nível na hierarquia organizacional.
- **Recursos de auditoria completos** – Todas as dimensões, contas e detalhes transacionais são mantidos para análise e auditoria. Além disso, o Relatório financeiro fornece uma busca detalhada completa da transação original em qualquer uma das entidades legais consolidadas.
- **Conversão de moeda simplificada** – Após a configuração mínima no Finance and Operations, você pode converter qualquer relatório Relatório financeiro em qualquer moeda de relatório configurada. Além disso, você pode configurar um número ilimitado de moedas de relatório.
- **Lançamento de eliminações na origem** – Você pode criar e imprimir um relatório de eliminação para verificar as transações de eliminação. Você pode lançar quaisquer novas eliminações como transações intercompanhia. Você também pode usar uma entidade legal de eliminação para qualquer transação que não queira em suas entidades legais.

## <a name="supported-consolidation-scenarios"></a>Cenários de consolidação compatíveis
Aqui estão alguns dos cenários de consolidação que o Relatório financeiro permite:

- Consolidações de nível único e de vários níveis em entidades legais
- Consolidações que usam estruturas organizacionais criadas a partir de entidades legais
- Consolidações que envolvem eliminações
- Interesse minoritário
- Vários gráficos de contas em entidades legais
- Calendários fiscais diferentes em várias entidades legais
- Consolidações que envolvem várias moedas de relatório
- Consolidações da unidade de negócios

## <a name="generating-consolidated-financial-statements"></a>Criação de demonstrativos financeiros consolidados
Para obter informações sobre os cenários onde você poderá gerar demonstrativos financeiros consolidados, consulte [Gerar demonstrativos financeiros consolidados](./generating-consolidated-financial-statements.md).
