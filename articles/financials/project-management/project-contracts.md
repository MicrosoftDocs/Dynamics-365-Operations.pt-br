---
title: Contratos do projeto
description: Este tópico fornece exemplos de contratos de projeto que você pode criar para vários tipos de projetos e de fontes de financiamento, e como você pode gerenciar contratos e clientes do projeto de fatura no Microsoft Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0f0fcec64ce03c6e1d877fb1c8d004bb416bd95
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "310360"
---
# <a name="project-contracts"></a>Contratos do projeto

[!include [banner](../includes/banner.md)]

Este artigo fornece exemplos de contratos de projeto que você pode criar para vários tipos de projetos e de fontes de financiamento, e como você pode gerenciar contratos e clientes do projeto de fatura no Microsoft Dynamics 365 for Finance and Operations.

O tipo de projeto que você cria para um contrato de projeto determina o método de faturamento que é usado para os clientes de projeto. Você pode modificar um contrato de projeto e o projeto relacionado, mas não é possível alterar o tipo de projeto. 

Ao usar um contrato de projeto, você pode faturar um ou mais projetos ao mesmo tempo. O contrato de projeto também ajuda a garantir um procedimento de faturamento consistente para cada subprojeto de uma estrutura de projeto. 

Cada projeto que será faturado deve estar associado a um contrato de projeto. As configurações para um contrato de projeto se aplicam a todos os projetos e subprojetos associados ao contrato de projeto. 

Um contrato de projeto pode especificar uma ou mais origens de financiamento. Portanto, é possível dividir a cobrança entre vários financiadores, configurar os limites de financiamento para que não seja cobrado mais do que um valor especificado das fontes de financiamento, e configurar regras de financiamento para cobrar despesas.

## <a name="funding-for-project-contracts"></a>Financiamento para contratos de projeto
Alguns contratos de projeto especificam que diversos participantes compartilhem a responsabilidade pelo financiamento dos custos do projeto. Eis alguns exemplos:

-   Um grande cliente que tem várias divisões solicita que o financiamento de um projeto seja dividido por divisão.
-   A empresa compartilha os custos de um grande projeto com uma organização externa.
-   Um projeto de estrada é refinanciado por duas municipalidades.
-   Um projeto de ponte é patrocinado por um subsídio do governo e por uma empresa privada.

No Finanças e Operações, você pode dividir a cobrança para uma única transação ou um projeto inteiro entre vários clientes, concessões, ou organizações. 

Nos projetos que têm várias financiadoras, todos os participantes que contribuem com o financiamento de um projeto avançado de financiamento são chamadas fontes de financiamento. Depois que um cliente, organização ou concessão é definida como fonte de financiamento, poderá então ser atribuída a um ou mais regras de financiamento. As regras de financiamento contêm os critérios que determinam como os encargos são alocados para as diversas fontes de financiamento de um projeto. 

Como os itens estocados, como aqueles que aparecem em requisições de compra e ordens de compra, não podem ser divididos, o valor de custo não pode ser dividido entre várias fontes de financiamento no momento da distribuição. Portanto, o valor da fonte de financiamento permanece em zero até a saída do estoque ser lançada. Quando a saída de estoque é lançada, o valor de custo é distribuído de acordo com as regras de distribuição da conta para o projeto.

Veja a seguir algumas etapas que você pode executar para facilitar a divisão da cobrança entre várias fontes de financiamento:

-   Especificar se todas as transações que são inseridas para um projeto usam a mesma moeda de venda que o contrato de projeto.
-   Configurar os limites de financiamento de forma que uma fonte de financiamento não seja faturada além do valor especificado para um projeto.
-   Configurar as regras de financiamento e os limites de financiamento para cada trabalhador, item, categoria, grupo de categorias e tipo de transação (ou para todos os tipos de transação).
-   Escolher as datas inicial e final opcionais para definir o período de tempo que cada regra de financiamento ficará válida.
-   Especificar a porcentagem que cada fonte de financiamento ficará responsável.
-   Especificar a fonte de financiamento responsável pelas diferenças de arredondamento causadas pelos cálculos de alocação de financiamento.
-   Configurar as regras que determinam como os custos do projeto serão faturados para clientes externos e cobrados de organizações internas.
-   Registrar transações em uma conta de financiamento em espera até que o financiamento adicional possa ser obtido ou até você decidir carregar internamente o custo.

Para determinar o grupo de impostos para associar uma transação, o projeto é pesquisado por uma atribuição do grupo de impostos. Se nenhuma atribuição do grupo de impostos foi feita no nível do projeto, o contrato de projeto é pesquisado.

### <a name="example-multiple-funding-sources-simple"></a>Exemplo: diversas fontes de financiamento (simples)

A tabela a seguir fornece cenários para gerenciar a alocação de financiamento entre várias fontes de financiamento. Estes cenários baseiam-se nas seguintes suposições:

-   As configurações de prioridade são fatoradas na alocação de fundos antes que outros critérios da regra de financiamento sejam aplicados.
-   Nenhum intervalo de datas foi especificado para definir o período d quando a regra de financiamento é válida.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Cenário</strong></td>
<td><strong>Fonte de financiamento </strong></td>
<td><strong>Porcentagem de alocação </strong></td>
<td><strong>Prioridade de alocação </strong></td>
</tr>
<tr class="even">
<td>Você deseja alocar custos para uma fonte de financiamento até que os fundos sejam esgotados, alocar custos para uma segunda fonte de financiamento até que os fundos sejam esgotados e, por fim, alocar os custos restantes para uma terceira fonte de financiamento.</td>
<td><ul>
<li>Fonte de financiamento 1</li>
<li>Fonte de financiamento 2</li>
<li>Fonte de financiamento 3</li>
</ul></td>
<td><ul>
<li>100%</li>
<li>100%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
<li>3</li>
</ul></td>
</tr>
<tr class="odd">
<td>Você deseja alocar 75% dos custos para uma fonte de financiamento e 25% para uma segunda fonte de financiamento. Quando qualquer uma dessas fontes de financiamento for esgotada, você desejará pagar os custos restantes de uma terceira fonte de financiamento.</td>
<td><ul>
<li>Fonte de financiamento 1</li>
<li>Fonte de financiamento 2</li>
<li>Fonte de financiamento 3</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
<tr class="even">
<td>Você deseja alocar 75% dos custos para uma fonte de financiamento e 25% para uma segunda fonte de financiamento. Quando qualquer uma das fontes de financiamento for esgotada, você desejará dividir os custos restantes entre uma terceira e quarta fonte de financiamento.</td>
<td><ul>
<li>Fonte de financiamento 1</li>
<li>Fonte de financiamento 2</li>
<li>Fonte de financiamento 3</li>
<li>Fonte de financiamento 4</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>50%</li>
<li>50%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
<li>2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Você deseja alocar os primeiros 25% dos custos a uma fonte de financiamento e o restante a uma segunda fonte.</td>
<td><ul>
<li>Fonte de financiamento 1</li>
<li>Fonte de financiamento 2</li>
</ul></td>
<td><ul>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a>Exemplo: Diversas fontes de financiamento (complexo)

Há três fontes de financiamento que você deseja usar na seguinte ordem:

1.  Usar a fonte de financiamento 2 e a fonte de financiamento 3 igualmente até que a fonte de financiamento 2 seja esgotada.
2.  Continuar usando a fonte de financiamento 3 até que seja esgotada.
3.  Usar a fonte de financiamento 1 depois que a fonte de financiamento 3 for esgotada.

Para atingir esse meta, siga este procedimento:

-   Configure os limites de financiamento para a fonte de financiamento 2 e a fonte de financiamento 3 para seus respectivos valores.
-   Crie as seguintes regras de financiamento:
    -   Regra 1 (Prioridade 1): alocar 50% das transações para a fonte de financiamento 2 e 50% para a fonte de financiamento 3.
    -   Regra 2 (Prioridade 2): alocar 100% das transações para a fonte de financiamento 3.
    -   Regra 3 (Prioridade 3): alocar 100% das transações para a fonte de financiamento 1.

Essa configuração verifica as transações em relação às regras e aos limites para determinar se alguma delas se aplica à transação. Se nenhuma regra ou limite específico se aplicar à transação, será aplicada a regra Todas as transações. A regra Todas as transações corresponde a todas as transações. 

Se o sistema localizar uma regra que corresponda a uma transação, a porcentagem que foi alocada nessa regra será aplicada primeiro, mas somente depois que as correspondências forem verificadas em relação aos limites que foram configurados. Se um limite for correspondido e os fundos de uma fonte de financiamento forem esgotados, a regra de financiamento associada ao limite de financiamento será desconsiderada e o programa verificará a próxima regra que se aplica. 

Em alguns casos, somente parte de uma transação poderá ser alocada sob uma regra. Isso pode acontecer porque um limite é atingido quando a transação é alocada. Nesse caso, somente um determinado valor é alocado de acordo com a regra, como 50% para cada fonte de financiamento. Esse é o caso na regra 1, descrita mais acima nesta seção. O restante é alocado de acordo com a próxima regra na sequência. 

A tabela a seguir examina esse cenário detalhadamente.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Foco </strong></td>
<td><strong>Detalhes</strong></td>
</tr>
<tr class="even">
<td>Regras de financiamento</td>
<td><ul>
<li>Regra 1 (Prioridade 1): Todas as transações. Alocar 50% para a fonte de financiamento 2 e 50% para a fonte de financiamento 3.</li>
<li>Regra 2 (Prioridade 2): Todas as transações. Alocar 100% para a fonte de financiamento 3.</li>
<li>Regra 3 (Prioridade 2): Todas as transações. Alocar 100% para a fonte de financiamento 1.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Limites de financiamento</td>
<td><ul>
<li>Limite da fonte de financiamento 1 = 10.000,00</li>
<li>Limite da fonte de financiamento 2 = 500,00</li>
<li>Limite da fonte de financiamento 3 = 750,00</li>
</ul></td>
</tr>
<tr class="even">
<td>Transação 1</td>
<td><strong>Valor da transação:</strong> 100.00<strong>Financiamento:</strong> A transação é paga somente de acordo com a regra 1, porque a transação é totalmente paga depois que a regra 1 é aplicada. A transação é financiada igualmente entre a fonte de financiamento 2 e a fonte de financiamento 3.
<ul>
<li>Fonte de financiamento 2: 50,00</li>
<li>Fonte de financiamento 3: 50,00</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transação 2</td>
<td><strong>Valor da transação:</strong> 5.000,00<strong>Financiamento:</strong> A transação é paga de acordo com as três regras. <strong>Regra 1</strong>
<ul>
<li>Fonte de financiamento 2: 450,00</li>
<li>Fonte de financiamento 3: 450,00</li>
</ul>
<strong>Regra 2</strong>
<ul>
<li>Fonte de financiamento 3: 250,00 (= 750,00 – 50,00 – 450,00)</li>
</ul>
<strong>Regra 3</strong>
<ul>
<li>Fonte de financiamento 1: 3.850,00 (= 5.000,00 – 450,00 – 450,00 – 250,00)</li>
</ul></td>
</tr>
<tr class="even">
<td>Total de fundos distribuído para cada fonte de financiamento</td>
<td><ul>
<li>Fonte de financiamento 1: 3.850,00</li>
<li>Fonte de financiamento 2: 500,00</li>
<li>Fonte de financiamento 3: 750,00</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a>Regras de cobrança
Ao negociar o contrato do projeto com um cliente, você define como e quando você pode faturar o cliente pelo trabalho no projeto. Depois que você configurar o contrato de projeto e o projeto, você pode configurar regras de cobrança para o projeto. As regras de cobrança são baseadas em termos do projeto que são especificados no contrato de projeto. As regras de cobrança que podem ser criadas dependem das condições no contrato de projeto e do tipo de projeto, como tempo e material ou preço fixo, que você associa à regra de cobrança. Você pode criar mais de uma regra de cobrança para um contrato de projeto. Também é possível atribuir uma regra de cobrança para vários projetos associados ao mesmo contrato de projeto e que têm condições semelhantes de cobrança. 

Você pode configurar os seguintes tipos de regra de cobrança:

-   **Unidade de entrega** – Faturar um cliente ao concluir uma unidade de entrega. Você define as unidades de entrega no contrato.
-   **Progresso** – Faturar um cliente ao concluir uma porcentagem especificada do projeto. Você pode configurar uma regra de cobrança para calcular automaticamente a porcentagem de trabalho concluída ou calcular manualmente a porcentagem trabalho concluída e o valor para faturar o cliente.
-   **Etapa** – Faturar um cliente pelo valor total de uma etapa de projeto quando a etapa for atingida.
-   **Taxa** – Faturar um cliente pelos seus serviços mais uma taxa de gerenciamento, normalmente uma porcentagem do custo dos serviços.
-   **Tempo e material** – Faturar um cliente pelo valor de tempo e de materiais usados em um projeto.

Para todos os tipos de regras de cobrança, você pode especificar uma porcentagem de retenção que é deduzida de uma fatura de cliente enquanto um projeto alcança uma fase combinada. A porcentagem da retenção de pagamento é especificada no contrato de projeto. O valor é calculado com base em e subtraído do valor total das linhas em uma fatura do cliente. 

Para as regras de cobrança **Tempo e material** e **Andamento**, você pode atribuir categorias passíveis de cobrança. As categorias passíveis de cobrança indicam as transações que devem ser incluídas nas faturas do cliente. 

Quando você estiver pronto para faturar o cliente, o valor da fatura do projeto será calculado com base nas regras de cobrança, e uma proposta de fatura de projeto será gerada. 

As seções a seguir fornecem exemplos que ilustram como configurar e gerenciar regras de cobrança para um projeto.

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a>Exemplo: Criar uma regra de cobrança com base no número de unidades entregues

Sua empresa participa de um contrato para fornecer um total de cinco sessões de treinamento aos funcionários de um cliente ao custo de 10.000 por sessão de treinamento. Você fatura o cliente ao final de cada sessão de treinamento. 

Ao configurar as regras de cobrança do contrato, use os seguintes valores:

-   A unidade de entrega é uma sessão de treinamento.
-   O preço unitário é de 10.000 por sessão de treinamento.
-   O número total de unidades é cinco sessões de treinamento.

Quando você concluir uma sessão de treinamento, poderá criar uma fatura de 10.000 para a primeira unidade entregue, e enviar a fatura ao cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a>Exemplo: Criar uma regra de cobrança com base em uma porcentagem especificada de conclusão do projeto (calculada manualmente)

Sua organização, uma empresa de consultoria de software, fecha um contrato com um cliente para desenvolver parte de um produto que o cliente está desenvolvendo. Sua organização concorda em entregar o código do software por um período de seis meses. O cliente concorda em pagar à sua organização um total de R$ 100.000 pelo trabalho. Você cria uma regra de cobrança para faturar o cliente com base em uma porcentagem de trabalho concluído no projeto, conforme especificado no contrato.

-   No final do primeiro mês, você se reunirá com o cliente para determinar a porcentagem de trabalho concluído. Após você e o cliente revisarem o projeto, vocês decidem que o projeto está 15 por cento concluído.
-   Você cria uma fatura no valor de R$ 15.000 (15% de R$ 100.000) e a envia para o cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a>Exemplo: Criar uma regra de cobrança com base em uma porcentagem especificada de conclusão do projeto (calculada automaticamente)

Sua organização, uma empresa de programação de software, aceita desenvolver um pacote de contabilidade de folha de pagamento para um cliente por 30.000. O cliente concorda em pagar sua organização com base na porcentagem de trabalho concluído. Você estima que os custos do projeto serão de 20.000. O contrato de projeto especifica as categorias de trabalho que você usa no processo de cobrança. Você configura regras de cobrança que calculam automaticamente os valores da fatura pelo percentual de trabalho que é concluído em cada categoria. Você configura um orçamento para cada categoria:

-   **Desenvolvimento** – Custo de 15.000 e receita de 20.000
-   **Instalação** – Custo de 5.000 e receita de 10.000.

Quando você cria uma fatura de cliente pela primeira vez, o valor da fatura é calculado automaticamente com base nas seguintes informações:

-   Depois de um mês, o trabalhador no projeto envia uma folha de ponto para o projeto. O custo das horas do trabalhador é de 5.000 pelo desenvolvimento e de 1.000 pela instalação. O trabalho de desenvolvimento está 33 por cento concluído (5.000 custo real/15.000 custo do orçamento) e o trabalho de instalação está 20 por cento concluído (1.000 custo real/5.000 custo do orçamento).
-   O valor da fatura de 8.667 é calculado automaticamente (33 por cento de 20.000 mais 20 por cento mais de 10.000).
-   Você cria uma fatura no valor de 8.667 e a envia para o cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a>Exemplo: Criar uma regra de cobrança com base nas etapas combinadas

Sua organização, uma empresa de consultoria gerencial, aceita conduzir uma pesquisa de mercado para um produto de consumo que o cliente planeja vender. O cliente concorda em usar seus serviços por um período de três meses, iniciando em março e concorda em pagar à sua organização 50.000. O projeto tem três etapas:

-   Etapa 1: coletar dados de consumo - 31 de março
-   Etapa 2: analisar os dados de consumo - 30 de abril
-   Etapa 3: apresentar uma proposta de viabilidade do produto - 31 de maio

O cliente concorda em pagar à sua organização 10.000 pela primeira etapa, 20.000 pela segunda e 20.000 pela terceira. 

Quando você configura o contrato de projeto, você concorda em cobrar o cliente com base na etapa concluída. A configuração da regra de cobrança inclui as seguintes etapas:

-   Defina as etapas do projeto.
-   Defina o valor a ser faturado ao cliente quando cada etapa for concluída.

Quando a primeira etapa for concluída em 31 de março, marque a etapa como concluída e, em seguida, crie uma fatura no valor de 10.000,00 para ser enviada ao cliente. Não é possível criar uma fatura para uma etapa até que você marque a etapa como concluída.

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a>Exemplo: Criar uma regra de cobrança com base nos serviços, mais uma taxa de gerenciamento

Sua organização, uma empresa de consultoria de gerenciamento, aceita conduzir uma pesquisa de mercado para avaliar a viabilidade de um produto que o cliente, uma empresa de varejo, está desenvolvendo. Os termos do contrato especificam que você fornecerá os serviços de seus três principais consultores de gerenciamento, que irão conduzir a pesquisa com base em tempo e material. O cliente concorda em pagar 100 por hora mais uma taxa de gerenciamento de 10 por cento para as horas de consultoria que são cobradas no projeto. 

Quando você configurar o contrato de projeto, crie uma regra de cobrança para adicionar uma taxa de gerenciamento de 10% às horas de consultoria cobradas no projeto. 

Quando você cria uma fatura para o cliente, uma taxa de gerenciamento de 10% é cobrada, mais o custo das horas de consultoria. Por exemplo, se os três consultores trabalharam um total de 200 horas no projeto, uma fatura será criada no valor de 22.000, usando o seguinte cálculo:

-   200 horas à 100 por hora = 20.000
-   taxa de gerenciamento de 10 por cento = 2.000
-   Valor total da fatura = 22.000

Se as taxas forem passíveis de imposto a um cliente, e você selecionar um grupo de impostos sobre vendas no contrato de projeto, o grupo de impostos sobre vendas será inserido automaticamente em uma regra de cobrança para taxas.

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a>Exemplo: Criar uma regra de cobrança para o valor do tempo e de materiais

Sua organização, uma empresa de consultoria de software, concorda em fornecer cinco consultores técnicos para trabalhar em um projeto de desenvolvimento de software para um cliente pelos próximos seis meses. O cliente concorda em pagar 150 por cada hora de consultoria e o custo dos materiais de escritório. Sua organização envia uma fatura para o cliente no final de cada mês. 

Quando você configura o contrato de projeto, você concorda em cobrar o cliente mensalmente pelo tempo e material usados no projeto. Você cria uma regra de cobrança que inclui as seguintes informações:

-   O período de contrato é de seis meses.
-   O tempo de consultoria é calculado a uma taxa de 150 por hora.
-   Os materiais de escritório são faturados pelo custo e não devem exceder o valor de 10.000 para o projeto.
-   Você cria uma fatura de cliente no final de cada mês do calendário durante o projeto.

Durante o primeiro mês, um total de 800 horas são registradas pelos consultores no projeto. O custo dos materiais de escritório cobrados no projeto é de 2.000. Sendo assim, no final do mês, você cria uma fatura para 122.000, calculado como 800 horas a 150 por hora mais 2.000 para suprimentos de escritório.



