---
title: "Criar planos de remuneração variável"
description: "A remuneração variável compõe o pagamento irregular de um funcionário, como bônus ou prêmios de estoque. Este tópico descreve os componentes a serem configurados para usar a remuneração variável e inserir um funcionário em um plano de remuneração variável."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9397e84f03ee5b340fa2aa0a64e582fc0078526e
ms.openlocfilehash: be156afa73de731e54985485b617bcbae883db3a
ms.lasthandoff: 03/31/2017


---

# <a name="create-variable-compensation-plans"></a>Criar planos de remuneração variável

A remuneração variável compõe o pagamento irregular de um funcionário, como bônus ou prêmios de estoque. Este artigo descreve os componentes que devem ser configurados antes de usar uma remuneração variável e inscrever um funcionário em um plano de remuneração variável.

O cálculo de valores de remuneração variável para os funcionários pode se basear em vários fatores, como o desempenho do funcionário, o nível de remuneração de um funcionário e o desempenho do departamento.

## <a name="variable-compensation-components"></a>Componentes da remuneração variável
### <a name="create-compensation-types"></a>Criar tipos de remuneração

Os **Tipos de remuneração variável **é um componente necessário. Os tipos de remuneração variável permitem descrever os remuneração variável de sua organização. Eles também permitem especificar se a remuneração será à vista ou, de forma não monetária, sobre o estoque.

### <a name="describe-vesting-rules"></a>Descrever regras de titularidade

Como alternativa, as empresas podem configurar **regras de titularidade**. Investindo regras descrevem como prêmio variável deve ser atribuída com o tempo. Por exemplo, uma regra de benefício proporcional diferido poderia indicar que o funcionário receberá 25 por cento do prêmio total para cada ano quatro próximos anos. Investindo as regras são informacionais.

## <a name="variable-compensation-plans"></a>Planos de remuneração variável
O **plano de remuneração variável** contém as regras, os métodos de cálculos e os valores padrão para o cálculo da remuneração variável para os funcionários inscritos. Quando você cria um plano de remuneração variável, você deve definir o tipo de compensação variável. O tipo de compensação variável determina se o sistema calculará um valor monetário ou número de unidades do prêmio. Você também deve definir o método de cálculo:

-   ** ** O ponto – o cálculo do prêmio se baseia variável a partir em remuneração fixa que o funcionário recebeu em uma data específica. A data será especificada no evento de processo aos novos valores de compensação são processados.
-   **Composição** – O valor de um prêmio é calculado para cada taxa de pagamento exclusiva de remuneração fixa que o funcionário recebeu entre a data de início do ciclo e a data final do ciclo do evento de processo. As taxas são adicionadas juntas para determinar no prêmio final. Por exemplo, durante o ciclo, transferido um funcionário a uma posição diferente que tem uma taxa de pagamento diferente. Nesse caso, o prêmio variável será ajustado para o período de tempo em que o funcionário recebeu cada taxa de pagamento.

O valor do prêmio variável pode ser baseado em um percentual do salário base normal do funcionário ou um número de unidades definido.

-   Selecione a opção **Porcentagem de base** para inserir uma porcentagem padrão e especifique se a base deve ser a taxa de pagamento fixa do funcionário ou o ponto de controle para o nível de remuneração. O nível de remuneração é definido no trabalho do funcionário. Os pontos de referência da estrutura de remuneração pode ser definido como o ponto de controle no plano de remuneração fixa. O sistema usará a remuneração em nível de fá-la-á funcionário e remissão recíproca ao ponto de controle a ser listado no plano de remuneração fixa do funcionário para o valor do ponto de controle para o nível de remuneração de um funcionário. O valor do ponto de controle será usado em vez de taxa de pagamento fixa do funcionário como base para a concessão.
-   Selecione a opção** Número de unidades** para inserir um número de unidades padrão, o valor de cada unidade e na moeda do valor unitário se o plano de remuneração não for em dinheiro (por exemplo, 200 unidades do estoque, que são avaliadas em 40 reais) ou apenas o número de unidades caso o plano de remuneração seja um para um prêmio em dinheiro. Para um prêmio em dinheiro, o funcionário receberá o número de unidades especificado na moeda usada para o plano de remuneração fixa (por exemplo, 500 unidades de USD 1). O controle de relacionamento um para um deve ser usado para indicar se há um mapeamento linear direta entre o número de unidades e o valor da unidade. Quando você cria um plano de remuneração variável para um plano a previsão de estoque usando o número de unidades, esta opção estará bloqueada automaticamente ** Sim **, e o valor unitário for ** ** 1.0000.

** Regra de contratação ** configuração permite especificar se todos os funcionários devem receber o mesmo, independentemente aumento de datas em que foram contratados (** regra de contratação ** ** ** = nenhum), ou se os funcionários devem receber uma porcentagem de prêmio baseado no comprimento do emprego durante o ciclo (** regra de contratação ** = ** porcentagem **). 

** Força de alavanca ** permite ajustar o prêmio do funcionário, com base no desempenho de departamento de funcionário. Métricas de desempenho pode ser definido para cada departamento ** departamentos ** na página, formulários relacionados abaixo ** ** &gt; ** remuneração ** &gt; ** ** desempenho. A concessão que os funcionários desse departamento recebem depende de depreciação ** porcentagem da meta atingida ** campos, para indicar o desempenho de departamento:

-   Se o desempenho do departamento for 100, o prêmio dos funcionários no departamento será fatorado pela porcentagem que é definida no campo** Pagamento em 100%**.
-   Se o desempenho do departamento tiver mais de 100, o sistema adicionará a porcentagem definida no campo **1% sobre o objetivo** para a porcentagem que é definida no campo **Pagamento em 100%** até que o valor que é definido no campo **Maior pagamento permitido** seja atingido.
-   Se o desempenho do departamento tiver menos de 100, o sistema subtrairá a porcentagem definida no campo **1% abaixo do objetivo** da porcentagem que é definida no campo **Pagamento em 100%** até que o valor que é definido no campo **Menor pagamento permitido** seja atingido.

Você pode definir** níveis de tolerância** em percentuais de limite, de forma que uma mensagem de aviso seja exibida se a aproveitamento fizer com que a porcentagem esteja fora da porcentagem do limite. 

Por padrão, o sistema procura o departamento que é definido na posição do funcionário. Entretanto, o prêmio para alguns funcionários pode depender do desempenho de vários departamentos. Nesse caso, os vários departamentos e a porcentagem de prêmio atribuída ao desempenho de cada departamento podem ser definidos no registro de funcionário em remuneração variável. Para obter informações, consulte “a seção de registro remuneração variável que rastreia”. 

O aproveitamento será usado somente se **Pagamento por desempenho** estiver selecionado quando o processo de remuneração for executado. 

** Substituições níveis ** a guia porcentagem permite substituir o padrão ou o número de unidades do prêmio, com base em um nível de remuneração do funcionário. ** Se permitir substituições ** de níveis será definido como Sim ** ** para os funcionários que estão inscritos no plano de remuneração variável, o sistema são o nível de trabalho de um funcionário, e procura-o na tabela de substituições níveis para determinar a porcentagem ou o número de unidades do nível. Se o nível não for encontrado na tabela das substituições, a porcentagem ou o número de unidades padrão geral ** ** de guia serão usadas. A porcentagem e o número de unidades podem ser substituídos no registro de funcionário no plano de remuneração variável.

## <a name="variable-compensation-enrollment"></a>Inscrição em remuneração variável
### <a name="determine-who-is-eligible-for-the-plan"></a>Determina quem está qualificado para o plano

Quando você estiver pronto para realizar a inscrição dos funcionários em um plano de remuneração variável, a primeira etapa é determinar quem está qualificado para a remuneração que é especificada no plano. Você não pode atribuir um plano para os funcionários, a não ser que você determine a qualificação. Para configurar a qualificação, abra a página **Regras de qualificação** para criar uma nova regra de qualificação para seu plano, e definir os critérios que um funcionário se atingir para o plano de remuneração. Você pode limitar a qualificação por departamento, associação de trabalhadores, região de remuneração (localização), trabalho, função de trabalho, tipo de trabalho e/ou nível de remuneração. Os funcionários podem ser inscritos em um plano de remuneração somente se atenderem **todos** os critérios que são definidos na regra de qualificação. 

**Nota:** As regras de qualificação determinam a qualificação para planos de remuneração fixa variável. As regras de qualificação usam os campos a seguir no registro de trabalho, cargo e funcionários para determinar se um funcionário está qualificado para um plano de remuneração:

-   Na página **Trabalho**:
    -   O campo **Trabalho**.
    -   Os campos **Função** e **Tipo de trabalho** na guia **Classificação do trabalho**
    -   O campo **Nível** na guia **Remuneração**
-   Na página **Posições**: os campos **Departamento** e **Região de remuneração**.
-   ** Funcionários ** página em: Informações sobre associações de trabalhadores associada às associações de trabalhadores de funcionário abaixo ** informações &gt; pessoais ** ** ** na guia do **** de ****

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Habilitar a inscrição para o plano de remuneração variável.

Na página **Planos de remuneração variável**, defina a opção **Habilitar inscrição** para **Sim** para permitir que os funcionários qualificados sejam inscritos no plano.

### <a name="enroll-the-employee"></a>Inscrever o funcionário.

Agora, você pode inscrever funcionários no plano de remuneração variável. Para inscrever um funcionário, vá para a página **Funcionários** e selecione o funcionário. Em seguida, no painel de ações, clique ** remuneração ** &gt; ** inscrição do plano variável **. 

**Nota:** **Inscrição** deve estar definido como **Sim** no plano de remuneração variável. ** Plano ** o campo mostra apenas planos que o funcionário está qualificado para, com base em regras de eligibilidade configuradas para os planos. Se uma regra de qualificação não estiver definida para um plano, nenhum funcionário tiver direito para o plano. 

Verifique se ** data efetiva ** o campo está definida corretamente. Se o plano de remuneração variável usa ** composição ** o método de cálculo, a data de efetivação de registro pode ser considerada durante o cálculo do prêmio do funcionário. 

Você pode usar ** substituições ** guia para substituir valores específicos do funcionário. Por exemplo, se ** regra de contratação ** será definido ** porcentagem ** o plano, e de admissão diferente deve ser usado no cálculo de porcentagem de contratação de funcionário, você pode definir a data de admissão ** contratar a data da regra ** no campo. É possível substituir ** porcentagem de prêmio ** ** o valor ou número de unidades ** o valor para um funcionário específico, dependendo das configurações de plano. Esses valores são fatorados ainda por regra de contratação, por fatoras de desempenho, e por outras configurações do plano. 

** Substituições organizacionais ** são usadas para basear o prêmio de um funcionário no desempenho de um ou vários departamentos. O percentual alocado entre departamentos devem totalizar 100. O desempenho individual do funcionário é considerado também. Essas configurações são usadas apenas se ** pagamento por desempenho ** é selecionado quando o processo de remuneração será executado.

<a name="see-also"></a>Consulte também
--------

[Planos de remuneração](compensation-plans.md)


