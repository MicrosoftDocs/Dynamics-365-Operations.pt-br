---
title: Criar planos de remuneração fixa.
description: A remuneração fixa se refere ao salário bruto normal ou ao salário de um funcionário. Este artigo descreve os componentes que devem ser configurados antes de criar um plano de remuneração fixa e inserir os funcionários.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 06f4a335adfc1e6f438589613efec02f92bfd756
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417300"
---
# <a name="create-a-fixed-compensation-plans"></a>Criar planos de remuneração fixa

A remuneração fixa se refere ao salário bruto normal ou ao salário de um funcionário. Este artigo descreve os componentes que devem ser configurados antes de criar um plano de remuneração fixa e inserir os funcionários.

Os valores de remuneração fixa podem ser calculados para os funcionários, com base em fatores como o desempenho, região e os aumentos de orçamento. O Dynamics 365 Human Resources dá suporte aos tipos de compensação por etapa, classificação e faixa.

## <a name="fixed-compensation-components"></a>Componentes de remuneração fixa
### <a name="compensation-levels"></a>Níveis de remuneração

Você pode usar **níveis de compensação** para definir a remuneração para vários trabalhos, para ajudar a garantir que os funcionários sejam pagos. Na página **Níveis de remuneração**, você pode configurar níveis de remuneração que são necessários para cada etapa, classificação e plano da faixa. Use os botões **Para cima** e **Para baixo** para colocar os níveis na ordem correta, de acordo com o tipo. Ao definir níveis de remuneração em um trabalho, você ajuda a garantir que todos os funcionários que ocupam o mesmo cargo sejam pagos no mesmo nível.

### <a name="reference-points"></a>Pontos de referência

**Pontos de referência** são as colunas na grade que definem os intervalos de remuneração para cada nível. O nível de remuneração é a linha na grade. Os pontos de referência para um plano do tipo de grade são mínimo, valor médio e máximo. Crie pontos de referência na página **Configurações do ponto de referência**.

### <a name="compensation-grids"></a>Grades de remuneração

Depois de configurar os níveis e pontos de referência, eles podem ser combinados para criar uma **grade de remuneração**. Na página **grades de compensação**, defina as informações sobre a grade. Por exemplo, especifique para que a grade será usada, com qual tipo de plano ela será usada e quais pontos de referência ou colunas são necessários na grade. Depois de concluir a inserção das informações, clique em **estrutura de compensação** para adicionar níveis e valores à grade. 

**Dica:** Use a função **Alterações em massa** na estrutura de remuneração para definir valores iniciais e, em seguida, incrementá-la por porcentagens e valores em seus níveis dos pontos de referência.

### <a name="pay-frequencies"></a>Frequências de pagamento

As **Frequências de pagamento** são usadas para definir como o salário de um funcionário está sendo especificado (por exemplo, $10 por hora e $50.000 por ano), e a conversão entre as taxas por hora, semanais, mensais (12 meses) e anuais. Por exemplo, uma empresa que usa uma semana de trabalho de 38 horas para os funcionários por hora define uma frequência de pagamento que tem uma taxa horária de 1, uma taxa semanal de 38, uma taxa mensal de 164.6666666667, e uma taxa anual de 1.976. Essas conversões são usadas para calcular várias taxas de pagamento que aparecem no registro de remuneração fixa do funcionário.

## <a name="fixed-compensation-plans"></a>Planos de remuneração fixa
Você pode criar o plano de remuneração fixa para combinar todos os componentes configurados. Para criar um plano de compensação fixa, abra a página **Planos de remuneração fixa**. Aqui, você pode inserir um nome e uma descrição ao plano, selecione o tipo de plano (etapa, classificação ou faixa), selecione a frequência de pagamento que será usada para a taxa de pagamento do funcionário (valor por hora, valor por ano, e assim por diante) e defina algumas opções que controlam como a remuneração é processada. 

A configuração **Fora do intervalo de tolerância** permite especificar a restrição para garantir que os valores de remuneração estão entre os valores mínimo e máximo. Uma tolerância **Rígida** exige que a remuneração esteja no intervalo definido para determinado nível. Uma tolerância **Flexível** avisa quando o valor de remuneração estiver fora do intervalo mas permite continuar. Se a tolerância for definida como **Nenhuma**, você poderá inserir um valor de remuneração de um funcionário sem receber mensagens de erro. 

A configuração **Regra de contratação** permite especificar se todos os funcionários devem receber o mesmo aumento, independentemente da data em que foram contratados (**Regra de contratação** = **Nenhum**), ou se os funcionários devem receber uma porcentagem de prêmio, com base no período trabalhado durante o ciclo (**Regra de contratação** = **Percentual**). 

A **matriz de utilização do intervalo** é útil se você desejar reduzir o tempo que é necessário para que os funcionários alcancem o valor médio do intervalo ou para aumentar o tempo que são necessários para que os funcionários alcancem o ponto de referência máximo no intervalo. Por exemplo, você deseja acrescentar aos funcionários que estão com os menores 25 por cento do intervalo de 110 por cento da meta do prêmio, mas deseja acrescentar aos funcionários com os 25 por cento maiores do intervalo da meta de 80 por cento , para evitar que eles atinjam o máximo com a mesma rapidez. 

Após definir os princípios do plano de remuneração fixa, é possível configurar a estrutura de remuneração para o plano. Clique em **Configurar remuneração**. Um controle deslizante da caixa de diálogo é aberto oferecendo três opções:

-   Crie uma nova grade de remuneração ao selecionar uma configuração do ponto de referência e fornecer um nome para a grade.
-   Crie uma nova grade de compensação fazendo uma cópia de uma grade existente que você possa usar como ponto de partida.
-   Use uma grade de remuneração existente que já foi definida. Todos os planos de remuneração que usam a mesma grade recebem atualizações se essa grade é alterada.

Depois que você seleciona uma opção, a página **Estrutura de remuneração** é aberta e você pode fazer alterações na nova grade de remuneração ou na grade de remuneração existente.

## <a name="fixed-compensation-enrollment"></a>Inscrição na remuneração fixa
### <a name="determine-who-is-eligible-for-the-plan"></a>Determina quem está qualificado para o plano

A primeira etapa na inscrição de funcionários em um plano de remuneração fixa é determinar quem está qualificado para a remuneração que é definida no plano. Até que você determine a qualificação, não poderá atribuir o plano aos funcionários. Para configurar a qualificação, abra a página **Regras de qualificação**. Aqui, você cria uma nova regra de qualificação para seu plano de remuneração e define os critérios que um funcionário deve atender para ser qualificado para um plano. Você pode limitar a qualificação com base no departamento, associação de trabalhadores, região de remuneração (localização), trabalho, função de trabalho, tipo de trabalho ou nível de remuneração. Os funcionários podem ser inscritos em um plano de remuneração somente se atenderem às condições que são definidas na regra de qualificação. 

**Nota:** As regras de qualificação são usadas para determinar a qualificação para os planos de remuneração fixa e variável. 

A regra de qualificação considera o valor de campos específicos no trabalho, no cargo e registros de funcionário para determinar se um funcionário estiver qualificado para o plano de remuneração.

-   Na página **Trabalho**, a regra de qualificação considera os seguintes campos:
    -   O campo **Trabalho**.
    -   Na guia **Classificação do trabalho**, os campos **Função** e **Tipo de trabalho**
    -   Na guia **Compensação**, o campo **Nível**
-   Na página **Posições**, a regra de qualificação considera os campos **Departamento** e **Região de remuneração**.

A regra de qualificação também considera as associações de funcionários que estão associadas ao funcionário (na página **Funcionários**, na guia **Funcionário**, clique em **Informações pessoais** &gt; **Associações de trabalhadores**).

### <a name="define-fixed-compensation-actions"></a>Definir ações de remuneração fixa

As **Ações de remuneração fixa** são usadas quando você define ou aplica alterações a uma remuneração fixa de um funcionário. As ações de remuneração fixa permitem fornecer nomes descritivos para os tipos de ações que a compensação e um gerente de benefícios pode realizar. Os diferentes tipos de ação têm uma lógica especial por trás delas, de modo que eles possam ser usados em hora específicas. 

Por exemplo, quando a remuneração fixa for configurada para um funcionário, apenas as ações com o tipo **Contratar/recontratar** podem ser usadas. Nesse caso, pode ser necessário criar três ações diferentes do tipo **Contratar/recontratar** e nomeá-las como **Contratar**, **Recontratar** e **Transferir**. Você receberá uma explicação mais detalhada sobre a concessão da remuneração fixa de um funcionário ou sobre sua alteração.

### <a name="enroll-the-employee"></a>Inscrever o funcionário.

Agora, você pode atribuir um funcionário a um plano de remuneração fixa. Abra a página **Funcionários** e selecione o funcionário para inscrição no plano de remuneração. No Painel de Ação, clique em **Remuneração** &gt; **Plano fixo**. Agora você pode criar uma nova ação de remuneração fixa do funcionário. 

**Nota:** O campo do plano de remuneração mostra somente os planos que um funcionário estiver qualificado para as regras de qualificação que foram configuradas para cada plano. Se nenhuma regra de qualificação for configurada para um plano, nenhum funcionário será qualificado para o plano. 

O sistema verifica se o valor de remuneração especificado para um plano de remuneração do tipo de classificação ou da faixa está dentro dos pontos de referência mínimo e máximo para o nível de remuneração no trabalho do funcionário. Se o valor de remuneração estiver fora do intervalo permitido, um aviso ou uma mensagem de erro serão exibidas, dependendo do nível de tolerância que é definido no plano de remuneração fixa.



[!INCLUDE[footer-include](../includes/footer-banner.md)]