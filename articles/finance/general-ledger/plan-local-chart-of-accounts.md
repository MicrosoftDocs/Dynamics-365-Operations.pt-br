---
title: Planejar seu plano de contas local
description: Este artigo fornece informações que ajudarão você a planejar o plano de contas quando tiver requisitos de requisitos estatutários/locais para sua organização.
author: VeselinaE
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: twheeloc
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78379fd51cf24985fce83e2b6aa9a475af7df363
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946235"
---
# <a name="plan-your-local-chart-of-accounts"></a>Planejar seu plano de contas local

[!include [banner](../includes/banner.md)]

Este artigo fornece informações que o ajudarão a planejar o plano de contas quando sua organização incluir entidades legais que devem atender requisitos para localidades específicas em que fazem negócios. Este artigo usa os seguintes termos para descrever os planos de contas:

- **Global** – o plano de contas que a organização usa globalmente. Na maioria dos casos, você se consolidará neste plano de contas.
- **Local** – um plano de contas que as entidades legais em um país ou região específico usam.
- **Compartilhado** – um plano de contas que pode ser usado por mais de uma entidade legal. O gráfico global de contas e os gráficos locais de contas podem ser compartilhados.

Você pode criar e compartilhar vários gráficos de contas. Um plano de contas compartilhado pode ser usado por mais de uma entidade legal, mas somente um gráfico de contas pode ser atribuído a cada entidade legal. O plano de contas que uma entidade legal usa é definido na página **Razão**.

Ao criar o plano de contas, muitas empresas visam um gráfico global de contas. O recurso de plano de contas compartilhado permite a criação de um plano de contas global. Existem benefícios na criação e no uso de um único plano de contas. Por exemplo, governança e controle, manutenção e geração de relatórios são mais fáceis.

A maioria das organizações prefere um gráfico global de contas e é o tipo mais fácil de implementar. No entanto, algumas entidades legais exigem um plano de contas local pelos seguintes motivos:

- Requisitos estatutários locais
- Requisitos de padrões contábeis locais
- Requisitos do setor
- Requisitos de relatório e análise específicos da empresa

Se a sua organização exigir que uma entidade legal use um plano de contas local, duas opções estarão disponíveis para implementá-las:

- Atribua o gráfico global de contas e defina outras formas de atender aos requisitos locais.
- Atribua um plano de contas local à entidade legal e defina relações com o plano de contas global.

A estrutura da organização e a estrutura de relatório determinam a opção usada.

[![Diagrama mostrando como a estrutura da organização determina se deve ser usado um plano de contas global ou local](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

Se o gráfico global de contas for atribuído à entidade legal, as seguintes opções estarão disponíveis para atender aos requisitos de relatórios locais:

- Faça a consolidação local.
- Use uma dimensão financeira para rastrear o plano de contas local.
- Crie contas principais locais no plano de contas global.
- Faça o mapeamento externo para o plano de contas local.

Se um plano de contas local for atribuído à entidade legal, a única opção disponível no momento para atender aos requisitos globais de geração de relatórios é a consolidação global.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>Plano de contas global atribuído a uma entidade legal

Se for necessário atribuir o plano de contas global a uma entidade legal, quatro opções estarão disponíveis para configurar o sistema, conforme descrito anteriormente. Para todas as quatro opções, um único plano de contas é configurado e vinculado a cada entidade legal na página **Razão**. Cada opção usa uma abordagem diferente para atender aos requisitos de localização. As seções a seguir descrevem as etapas de alto nível para configurar o sistema para os requisitos de localização. Elas também descrevem as vantagens e desvantagens de cada opção.

### <a name="do-local-consolidation"></a>Fazer a consolidação local

A consolidação local é a abordagem recomendada para atender aos requisitos de plano de conta local e aproveitar a funcionalidade do sistema projetada para essa finalidade.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>Configurar a consolidação para um plano de contas local

1. Crie um único gráfico global de contas que inclua todas as contas principais necessárias.
2. Em cada entidade legal, atribua o plano de contas global na página **Razão**.
3. Crie uma entidade legal de consolidação para cada localização necessária.
4. Siga uma destas etapas:

    - Se for necessária apenas uma localização, configure a conta de consolidação na página **Conta principal** ou use as páginas **Grupos de consolidação** e **Contas de consolidação adicionais**.
    - Se mais de uma localização for necessária ou se o número da conta e o nome da conta exigirem tradução, use as páginas **Grupos de consolidação** e **Contas de consolidação adicionais** para representar os requisitos de localização.

5. Execute o processo de consolidação para transformar o valor da entidade legal de origem que usa o gráfico global de contas para a empresa de consolidação que usa o plano de contas local.

#### <a name="advantages"></a>Vantagens

- Essa abordagem oferece uma forma consistente de trabalhar na organização.
- Uma tradução da posição local é feita.
- Essa abordagem oferece suporte à tradução da ID da conta principal e do nome de cada conta principal.
- Ele oferece suporte a várias localizações.

#### <a name="disadvantages"></a>Desvantagens

- Uma empresa de consolidação adicional é criada.
- Um processo de consolidação adicional é concluído.
- Essa abordagem pode relatar o gráfico localizado somente após a conclusão do processo de consolidação.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>Use uma dimensão financeira para rastrear o plano de contas local

Essa abordagem usa uma dimensão financeira na qual os valores de dimensão financeira representam as contas principais locais necessárias para a localização. Ele funcionará bem se apenas uma localização for necessária. No entanto, ele se torna menos utilizável à medida que você adiciona mais localizações e dimensões financeiras.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>Configurar uma dimensão financeira para um plano de contas local

1. Crie um único gráfico global de contas que inclua todas as contas principais necessárias.
2. Em cada entidade legal, atribua o plano de contas global na página **Razão**.
3. Crie uma dimensão financeira que represente o plano de contas local.
4. Crie valores de dimensão financeira que represente as contas principais no plano de contas local.
5. Atualize a estrutura de conta para que ela inclua a dimensão financeira "plano de contas local".
6. Verifique se a dimensão financeira "plano de contas local" sempre tem um valor e se não permite um valor em branco. Considere o uso de dimensões derivadas ou dimensões fixas.
7. Crie um conjunto de dimensões financeiras no qual a dimensão financeira "plano de contas local" é a primeira dimensão financeira selecionada. O conjunto de dimensões financeiras pode ser usado quando o balancete é gerado.

#### <a name="advantages"></a>Vantagens

- As contas principais de planos globais e locais de contas existem no nível da transação. A conta principal é global e o valor da dimensão financeira é local.
- Essa abordagem fornece relatórios e exibições em tempo real da posição financeira global e da posição financeira local.

#### <a name="disadvantages"></a>Desvantagens

- Nos parâmetros da Contabilidade, se o campo **Valores usados para a conta de resumo** estiverem definidos como **Distribuições contábeis**, as dimensões financeiras que representam a conta principal para a despesa/ativo/receita serão usadas incorretamente para a conta de resumo Contas a receber e Contas a pagar. É recomendável definir o campo como um documento de origem para garantir que os valores de dimensão financeira corretos sejam usados.
- Se vários gráficos locais de contas forem necessários e uma dimensão financeira for usada para todas elas, a lista de valores de dimensão financeira que são usados pode ficar longa e difícil de trabalhar.
- Se vários gráficos locais de contas forem necessários e uma dimensão financeira separada for usada para representar cada um, a usabilidade e o desempenho do sistema poderão ser afetados quando as dimensões financeiras e os conjuntos de dimensões financeiras forem adicionados.
- Recomendamos que você considere cuidadosamente o número de dimensões financeiras necessárias, o número de valores em cada um, e o número de conjuntos de dimensões financeiras, pois todos esses fatores podem afetar o desempenho do sistema.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>Criar contas principais locais no plano de contas global

*O que é perguntado ao editor de cópia:* nesta abordagem, as contas principais locais no plano de contas global incluem as contas principais no plano de contas local no plano de contas global.

*Versão original:* as contas principais locais na abordagem do CoA global são as contas principais do CoA locais incluídas no CoA global.

*Neste caso:* nesta abordagem, as contas principais locais no plano de contas local são incluídas no plano de contas global.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>Configurar contas principais locais no plano de contas global

1. Crie um único plano de contas que inclua as contas principais para o plano de contas global e para o plano de contas local.
2. Em cada entidade legal, atribua o plano de contas na página **Razão**.
3. Crie contas de total no plano de contas para somar as contas principais que representam a mesma finalidade.
4. Criar substituições da entidade legal em cada conta local para evitar transações de outras entidades legais para as quais a conta local não foi projetada.
5. Criar substituições da entidade legal em cada conta global para evitar transações das entidades legais de localização.

#### <a name="advantages"></a>Vantagens

- Uma exibição em tempo real da posição financeira global e da posição financeira local está disponível em relatórios específicos e em exibições específicas no sistema, como um relatório financeiro de balanço. Também pode ser acessado usando o botão **Período** na conta de total.
- Você não tem um segmento adicional na conta contábil.

#### <a name="disadvantages"></a>Desvantagens

- A visibilidade e o uso da conta de total são limitados. Por exemplo, as contas de total não são visíveis na página de listagem **Balancete**.
- A manutenção requer esforço adicional.
- A criação de relatórios financeiros requer esforço manual adicional.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>Faça o mapeamento externo para o plano de contas local

A adoção de um gráfico global de contas pressupõe que você esteja gerenciando o mapeamento e as localizações fora do sistema. Nessa abordagem, bastará criar um único plano de contas global do Microsoft Dynamics 365 Finance e manipular os requisitos fora do sistema.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>Configurar mapeamento externo para um plano de contas local

1. Crie um único gráfico global de contas que inclua todas as contas principais necessárias.
2. Em cada entidade legal, atribua o plano de contas global na página **Razão**.
3. Faça o mapeamento para o plano de contas local fora do Finance.

#### <a name="advantages"></a>Vantagens

- Essa abordagem oferece formas unificadas de trabalhar na organização.

#### <a name="disadvantages"></a>Desvantagens

- Nenhum relatório local do sistema está disponível.
- Essa abordagem é sujeita a erros quando relatórios financeiros são criados.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>Plano de contas local atribuído a uma entidade legal

Se a sua organização decidir não usar um plano de contas global entre entidades legais, um plano de contas separado será criado para cada plano de contas local exclusivo. Cada entidade legal é então vinculada ao plano de contas correspondente na página **Razão**.

### <a name="do-global-consolidation"></a>Fazer a consolidação global

Nessa abordagem, uma empresa de consolidação é usada para acumular e combinar os saldos de cada empresa local de origem no plano global de contas combinado na empresa de consolidação. Essa abordagem exige que você mantenha um mapeamento de cada plano de contas local para o plano de contas global na empresa de consolidação.

#### <a name="set-up-global-consolidation"></a>Configurar a consolidação global

1. Crie um plano de contas separado para cada entidade legal que tenha um plano de contas local diferente. Se qualquer entidade legal tiver o mesmo plano de contas local, só será necessário um plano de contas local e ele poderá ser compartilhado.
2. Em cada entidade legal, atribua o plano de contas apropriado na página **Razão**.
3. Opcional: crie um plano de contas para o plano de contas global de cada empresa de consolidação que tenha um plano de contas global diferente.
4. Crie uma entidade legal de consolidação para cada nível de consolidação necessário e atribua o plano de contas apropriado na página **Razão**.
5. Siga uma destas etapas:

    - Se apenas uma consolidação for necessária, configure a conta de consolidação na página **Conta principal**.
    - Se mais de uma consolidação for necessária ou se o número da conta e o nome da conta exigirem tradução, use as páginas **Grupos de consolidação** e **Contas de consolidação adicionais** para representar os requisitos para o plano de contas global.

6. Execute o processo de consolidação para transferir os saldos das entidades legais locais para a entidade legal consolidada. Essa entidade legal consolidada usa as contas de consolidação definidas na etapa 5.

#### <a name="advantages"></a>Vantagens

- O formato de padrões contábeis locais é aplicado nativamente.
- Essa abordagem dá à equipe de finanças local uma forma mais fácil de trabalhar.

#### <a name="disadvantages"></a>Desvantagens

- Nenhuma exibição em tempo real da posição global está disponível.
- O processo de consolidação pode ser executado com mais frequência.

## <a name="additional-resources"></a>Recursos adicionais

- [​Planejar seu plano de contas​](plan-chart-of-accounts.md)
- [Configurar Razões](configure-ledger.md)
- [Dimensões financeiras e lançamento](Default-dimensions.md#balancing-dimension)
- [Conjuntos de dimensões financeiras](financial-dimension-sets.md)
- [Visão geral de consolidação de eliminação](../budgeting/consolidation-elimination-overview.md)
- [Grupos de conta de consolidação e contas de consolidação adicionais](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
