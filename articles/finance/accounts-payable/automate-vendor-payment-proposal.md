---
title: Automatizar propostas de pagamento de fornecedor
description: Este tópico explica como as organizações que pagam fornecedores em uma agenda recorrente podem automatizar o processo de geração de propostas de pagamento de fornecedor.
author: kweekley
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 2b4e6b42326ecbd07efe006afb23931849f5cf58
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4440572"
---
# <a name="automate-vendor-payment-proposals"></a>Automatizar propostas de pagamento de fornecedor

[!include [banner](../includes/banner.md)]

Organizações que pagam fornecedores em uma agenda recorrente agora podem automatizar o processo de geração de propostas de pagamento de fornecedor. As automatizações de proposta de pagamento de fornecedor definem os seguintes detalhes:

- Quando as propostas de pagamento são executadas
- Que critérios são usados para selecionar as faturas a serem pagas
- O diário de pagamentos do fornecedor em que os pagamentos resultantes são salvos

As automatizações de proposta de pagamento não lançam automaticamente os pagamentos. Portanto, você pode continuar a usar qualquer validação e processo de fluxo de trabalho utilizada atualmente para aprovar os pagamentos que são criados.

## <a name="define-the-occurrence-of-vendor-payment-proposals"></a>Definir a ocorrência de propostas de pagamento de fornecedor

Automação de propostas de pagamento de fornecedor usam a estrutura de automação de processo. Processos comerciais diferentes usam essa estrutura para definir a recorrência de um processo selecionado. Para as propostas de pagamento de fornecedor, a automação pode ser acessada em **Contas a pagar \> Configuração de pagamento \> Automação de processo**.

Primeiro, use a opção de automação **Criar novo processo** e selecione **Proposta de pagamento de fornecedor**. Em seguida, um assistente o orienta durante o processo de configuração da proposta de pagamento de fornecedor.

## <a name="general-page"></a>Página Geral

Na página **Geral** do assistente, insira o nome da proposta de pagamento de fornecedor que você está criando. Por exemplo, se você pagar todos os fornecedores nacionais em cheque na segunda-feira, insira um nome descritivo, como **Cheque\_Nacional**. O nome inserido aparece na exibição semanal do processo de automação no espaço de trabalho **Pagamentos do fornecedor**.

Em seguida, defina o proprietário do diário de pagamentos criado. O proprietário geralmente é o auxiliar de pagamento de contas a pagar (AP), que é responsável pelo diário de pagamentos depois de criado.

As configurações restantes na página são genéricas e são usadas para definir o padrão de ocorrência para essa versão da proposta de pagamento de fornecedor. Por exemplo, se uma ocorrência for para pagamentos em cheque na segunda-feira, você poderá defini-la para que seja executada semanalmente e selecionar segunda-feira como o dia da semana em que será executada. Você também pode inserir um tempo de planejamento antecipado, como 2:00, de forma que a automação do processo seja concluída antes do início do dia útil seguinte.

É importante compreender que você está usando o assistente para definir quando a proposta de pagamento de fornecedor é processada. Você não está definindo quando os pagamentos do fornecedor são gerados, impressos e lançados. Na exibição semanal, a automação de processo para propostas de pagamento de fornecedor aparecerá nos dias selecionados no padrão de ocorrência.

Para obter mais informações sobre os outros campos na página **Geral**, consulte a documentação de automação de processo.

## <a name="vendor-payment-proposal-page"></a>Página Proposta de pagamentos do fornecedor

A próxima página do assistente é a página **Proposta de pagamento de fornecedor**. Ela é usada para definir os critérios para a seleção das faturas do fornecedor que devem ser pagas. Em geral, as mesmas opções são encontradas na proposta de pagamento no diário de pagamentos do fornecedor. No entanto, existem algumas exceções. Por exemplo, todas as datas nesta página devem ser definidas como datas relativas porque a data da proposta de pagamento é alterada sempre que a proposta é executada.

### <a name="journal-name"></a>Nome do diário

O campo **Nome do diário** define o nome do diário no qual os pagamentos do fornecedor são criados. Os resultados da automação da proposta de pagamento de fornecedor criarão pagamentos no diário definido, mas o diário não será lançado.

### <a name="from-date-and-to-date"></a>"De" e "Até"

Em vez de definir as datas "de" e "até" para a seleção de faturas com base na data de vencimento ou na data de desconto à vista, você deve usar a opção **Definir como critérios de data** e o **Número de dias de ajuste para a data final** para definir a data "até". Não há conceito de data "de" em automatizações de proposta de pagamento.

Por padrão, a opção **Definir como critérios de data** está definida como **Não**. Se você usar esse valor padrão, o processo selecionará todas as faturas para o pagamento quando ele for executado, pois nenhuma data "até" será definida.

Se você definir a opção **Definir como critérios de data** como **Sim**, use o campo **Número de dias de ajuste para a data final** para definir a data em que as faturas são selecionadas como o número especificado de dias antes ou depois da data em que o processo é executado. O número pode ser positivo, negativo ou 0 (zero). O sistema pagará as faturas em que as datas de vencimento, ou datas de desconto à vista, são o número especificado de dias antes ou depois da data em que o processo é executado. Por exemplo, para todas as faturas que vencem em ou antes de sexta-feira, a série de pagamentos cria pagamentos em cheque para todos os fornecedores na quarta-feira. Nesse caso, defina o campo **Número de dias de ajuste para a data final** como **2**. Quando a ocorrência da proposta de pagamento for executada na quarta-feira, 25 de março, todas as faturas com data de vencimento ou data de desconto à vista em ou antes de 27 de março serão selecionadas para pagamento.

### <a name="minimum-payment-date"></a>Data de pagamento mínimo

A data de pagamento mínimo define primeira data usada quando pagamentos são criados. Primeiro, você deve definir a opção **Definir critérios de data de pagamento mínimo** como **Sim**. Essa configuração permite usar a funcionalidade de data de pagamento mínima. Se esta opção estiver definida como **Sim**, use o campo **Número de dias de ajuste para a data final** para definir a data de pagamento mínimo como o número especificado de dias antes ou depois da data em que o processo é executado. O número pode ser positivo, negativo ou 0 (zero). Por exemplo, a série de pagamentos gera pagamentos na quarta-feira para incluir todos os pagamentos que têm uma data de pagamento mínima da segunda-feira anterior. Nesse caso, defina o campo **Número de dias de ajuste para pagamento mínimo** como **-2**.

Veja um exemplo que mostra como os campos para a data "até" e a data de pagamento mínimo funcionam juntas. A automação da proposta de pagamento está configurada para ser executada na quarta-feira. O campo **Número de dias de ajuste para a data final** é definido como **1** para definir a data "até" com base na data de vencimento. O campo **Número de dias de ajuste para pagamento mínimo** é definido como **-2**. Se a automação do processo de pagamento iniciar na quarta-feira, 25 de março, todas as faturas que vencerem em ou antes de 26 de março serão incluídas na proposta de pagamento. As propostas de pagamento serão geradas da seguinte maneira:

- Todas as faturas que vencerem em ou antes de 23 de março terão uma data de pagamento em 23 de março.
- As faturas que vencerem em 24 de março terão uma data de pagamento em 24 de março.
- As faturas que vencerem em 25 de março terão uma data de pagamento em 25 de março.
- As faturas que vencerem em 26 de março terão uma data de pagamento em 26 de março.

### <a name="summarized-payment-date"></a>Data do pagamento resumido

A data do pagamento resumido é usada somente quando o campo **Período** está definido como **Total** para o método de pagamento das faturas. Se o campo **Período** estiver definido como **Total** para os métodos de pagamento, você deverá definir a opção **Definir critérios de data de pagamento resumido** como **Sim**. Se esta opção estiver definida como **Sim**, use o campo **Número de dias de ajuste para data do pagamento resumido** para definir a data do pagamento resumidos como o número especificado de dias antes ou depois da data em que o processo é executado. O número pode ser positivo, negativo ou 0 (zero). Por exemplo, a série gera pagamentos na quarta-feira e a empresa deseja criar um pagamento resumido na quarta-feira. Nesse caso, defina o campo **Número de dias de ajuste para pagamento resumido** como **0**.

### <a name="records-to-include"></a>Registros a serem incluídos

As opções de filtro ainda podem ser definidas para a proposta de pagamento. Se um filtro for definido, os critérios de filtragem não serão mostrados na página do assistente. No entanto, eles podem ser exibidos ao reabrir o filtro.

Os campos restantes para a proposta funcionam da mesma forma que na proposta de pagamento no diário de pagamentos do fornecedor. Para obter informações sobre os outros campos, consulte [Criar pagamentos de fornecedor usando proposta de pagamento](create-vendor-payments-payment-proposal.md).

> [!NOTE]
> Alguns campos específicos do país/região e alguns campos do setor público ainda não estão disponíveis nas automações da proposta de pagamento do fornecedor.

Recomendamos que você avalie se a automação será benéfica para sua organização, de acordo com suas necessidades.

## <a name="view-the-results-of-a-vendor-payment-proposal-automation"></a>Exibir os resultados de uma automação de proposta de pagamento de fornecedor

Depois que a série de automação da proposta de pagamento do fornecedor é criada, as ocorrências para cada pagamento são mostradas na exibição semanal da automação de processo. Para pagamentos de fornecedor, a exibição semanal do processo de automação foi adicionada ao espaço de trabalho **Pagamentos do fornecedor** e à página **Automação de processo**.

[![Exibição semanal da automação do processo no espaço de trabalho de pagamentos de fornecedor](./media/vendor-payment-proposal-1.png)](./media/vendor-payment-proposal-1.png)

A exibição semanal do processo de automação no espaço de trabalho **Pagamentos do fornecedor** mostra somente as automações da proposta de pagamento do fornecedor. Ele mostra todas as ocorrências de pagamentos da semana atual, para todas as entidades legais às quais o usuário conectado tem permissões de segurança. Por exemplo, se o auxiliar de pagamento do AP for responsável por pagamentos nas empresas USMF e USSI, ele verá as ocorrências da automação da proposta de pagamento do fornecedor para essas duas empresas, mas não para outras empresas.

[![Exibição semanal de automação de processos para as empresas USMF e USSI](./media/vendor-payment-proposal-2.png)](./media/vendor-payment-proposal-2.png)

Cada ocorrência mostra a empresa em que o diário de pagamentos foi ou será criado. Se os pagamentos forem criados usando pagamentos centralizados, a empresa que mostrada será a empresa na qual os pagamentos serão criados. A ocorrência não mostra, necessariamente, quais faturas de empresas serão pagas.

O nome de cada ocorrência também é mostrado para ajudar a identificar a proposta de pagamento.

Além disso, o status de cada ocorrência é mostrado. Os seguintes status são usados:

- **Agendado** – a proposta de pagamento está agendada, mas ainda não foi executada.
- **Erro** – a proposta de pagamento foi executada, mas ocorreu um erro. Você pode exibir os erros selecionando o botão **Exibir resultados**.
- **Concluído** – a proposta de pagamento foi executada com êxito. Você pode exibir os pagamentos selecionando o link **Exibir pagamentos**. Este link abre o diário de pagamentos que foi criado pela ocorrência.

Depois que os pagamentos forem criados, você poderá exibir os valores de pagamento no diário. Os valores são mostrados nas moedas da transação. Por exemplo, se o diário de pagamentos contiver pagamentos em dólar americano e em dólar canadense, o total de pagamentos para cada moeda será mostrado. 

O diário de pagamentos pode ser excluído depois de criado por meio da automação do processo. Se um pagamento for excluído completamente, ocorrerão os seguintes eventos:

- O status da automação de processo para a semana permanece **Concluído**.
- O processo remove os totais do pagamento e o link **Exibir pagamentos** é substituído por um botão **Exibir resultados**.
- Ao exibir os resultados, você receberá uma mensagem indicando que o diário original foi excluído.

Depois que um pagamento for excluído, as faturas serão abertas novamente para pagamento. Uma nova ocorrência pode, então, ser criada para pagar as faturas novamente.

## <a name="edit-a-vendor-payment-proposal-automation"></a>Editar uma automação de proposta de pagamento de fornecedor

A estrutura de automação de processos permite editar o pagamento, a série e as ocorrências criadas para a proposta de pagamento. A série pode ser editada na página **Automação de processo** ou na exibição semanal de automação de processo. Por exemplo, se o gerente de AP decidir gerar todas as verificações para fornecedores nacionais na quarta-feira em vez de segunda-feira, ele poderá encontrar uma ocorrência na exibição semanal e selecionar **Exibir/Editar – Série**. Se você editar uma série, o sistema solicitará que especifique se a alteração deve ser feita em todas as ocorrências existentes ou somente em novas ocorrências. As ocorrências históricas que já têm o status **Concluído** ou que foram concluídas com status **Erro** não serão alteradas.

Você também pode adicionar uma nova ocorrência ou alterar uma ocorrência existente. Por exemplo, a próxima ocorrência da proposta de pagamento está agendada para execução na quarta-feira, 1º de janeiro, mas essa data é um feriado. Você pode alterar a ocorrência na exibição semanal de automação de processo ou na página **Automação de processo**. Uma página aberta que mostra os detalhes da agenda e os critérios de proposta de pagamento. Aqui, você pode editar a data e a hora agendadas. Também é possível editar os critérios da proposta de pagamento caso sejam necessárias alterações. Por exemplo, se você alterar a data agendada da ocorrência do pagamento de 1º de Janeiro para 2 de Janeiro, talvez também queira alterar as datas relativas da data "até".

Você também pode desabilitar uma ocorrência ou uma série. Para desabilitar uma ocorrência e suspender o processamento dela, selecione-a na exibição de automação de processo semanal e, depois, selecione **Desabilitar**. Você pode desabilitar uma série na página **Automação de processos**.

## <a name="security-for-payment-proposal-automations"></a>Segurança em automações de propostas de pagamento

Os direitos e privilégios a seguir foram adicionados para automações de propostas de pagamento de fornecedor. Esses direitos e privilégios são as configurações de segurança padrão, mas podem ser alterados com base nas necessidades da sua organização. Por exemplo, se o gerente do AP e o auxiliar de pagamento do AP puderem editar e criar a recorrência da agenda, atribua o direito **Manter ocorrências de agenda** à pessoa na função de auxiliar de pagamento do AP.

| Imposto                              | Função                                                                       | Privilégios |
|-----------------------------------|----------------------------------------------------------------------------|------------|
| Manter série de agenda          | Gerente de contas a pagar                                                   | Esse direito concede os direitos de criar e manter séries e ocorrências de automação da proposta de pagamento por meio dos seguintes privilégios:<ul><li>Manter ocorrências da agenda</li><li>Manter série de agenda</li><li>ProcessScheduleOccurrenceListMaintain</li><li>Visualizar a exibição semanal de ocorrências</li></ul> |
| Consultar ocorrências da agenda | Auxiliar de pagamento de contas a pagar, assistente de pagamento centralizado de contas a pagar | Esse direito concede os direitos de visualizar as ocorrências de automação da proposta de pagamento por meio dos seguintes privilégios:<ul><li>Visualizar ocorrências da agenda</li><li>Visualizar a exibição semanal de ocorrências</li></ul> |
| Consultar séries da agenda      | Nemhum(a)                                                                       | Esse direito concede os direitos de visualizar as configurações da série e ocorrências por meio dos seguintes privilégios:<ul><li>Visualizar ocorrências da agenda</li><li>Visualizar a página de listagem de ocorrências</li><li>Visualizar a exibição semanal de ocorrências</li></ul>|
| Manter ocorrências da agenda     | Nemhum(a)                                                                       | Esse direito concede os direitos de criar e manter uma ocorrência por meio dos seguintes privilégios:<ul><li>Manter ocorrências da agenda</li><li>Visualizar a exibição semanal de ocorrências</li></ul> |
