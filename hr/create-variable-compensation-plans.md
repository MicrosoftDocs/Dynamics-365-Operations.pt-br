---
title: "Criar planos de remuneração variável"
description: "A remuneração variável compõe o pagamento irregular de um funcionário, como bônus ou prêmios de estoque. Este tópico descreve os componentes que devem ser configurados antes de usar uma remuneração variável e inscrever um funcionário em um plano de remuneração variável."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 917771596a0c56561bf302ae990d95a987f442e0
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="create-variable-compensation-plans"></a>Criar planos de remuneração variável

[!include[banner](includes/banner.md)]


A remuneração variável compõe o pagamento irregular de um funcionário, como bônus ou prêmios de estoque. Este artigo descreve os componentes que devem ser configurados antes de usar uma remuneração variável e inscrever um funcionário em um plano de remuneração variável.

O cálculo de valores de remuneração variável para os funcionários pode se basear em vários fatores, como o desempenho do funcionário, o nível de remuneração de um funcionário e o desempenho do departamento.

## <a name="variable-compensation-components"></a>Componentes da remuneração variável
### <a name="create-compensation-types"></a>Criar tipos de remuneração

Os **Tipos de remuneração variável**é um componente necessário. Os tipos de remuneração variável permitem descrever os remuneração variável de sua organização. Eles também permitem especificar se a remuneração será à vista ou, de forma não monetária, sobre o estoque.

### <a name="describe-vesting-rules"></a>Descrever regras de titularidade

Como alternativa, as empresas podem configurar **regras de titularidade**. Regras de benefício proporcional diferido descrevem como o prêmio variável deve ser alocado com o tempo. Por exemplo, uma regra de benefício proporcional diferido pode indicar que o funcionário receberá 25% do seu prêmio total a cada ano nos próximos quatro anos. Regras de benefício proporcional diferido são apenas informações.

## <a name="variable-compensation-plans"></a>Planos de remuneração variável
O **plano de remuneração variável** contém as regras, os métodos de cálculos e os valores padrão para o cálculo da remuneração variável para os funcionários inscritos. Ao criar um plano de remuneração variável, você deve definir o tipo de remuneração variável. O tipo de remuneração variável determina se o sistema calcula um valor monetário ou um número de unidades como prêmio. Você também deve definir o método de cálculo:

-   **Pontual** – O cálculo do prêmio variável é baseado na remuneração fixa que o funcionário recebeu em uma data específica. A data é especificada no evento de processo quando novos valores de remuneração são processados.
-   **Composição** – O valor de um prêmio é calculado para cada taxa de pagamento exclusiva de remuneração fixa que o funcionário recebeu entre a data de início do ciclo e a data final do ciclo do evento de processo. As taxas são então adicionadas conjuntamente para determinar o prêmio final. Por exemplo, durante o ciclo, um funcionário transferido para uma posição diferente que recebeu uma taxa de pagamento diferente. Nesse caso, o prêmio variável será ajustado para o período de tempo em que o funcionário recebeu cada taxa de pagamento.

O valor do prêmio variável pode ser baseado em um percentual do salário base normal do funcionário ou um número de unidades definido.

-   Selecione a opção **Porcentagem de base** para inserir uma porcentagem padrão e especifique se a base deve ser a taxa de pagamento fixa do funcionário ou o ponto de controle para o nível de remuneração. O nível de remuneração é definido no trabalho do funcionário. Um dos pontos de referência da estrutura de remuneração pode ser definido como o ponto de controle no plano de remuneração fixa. O sistema usará o nível de remuneração no trabalho do funcionário e estabelecerá uma referência cruzada com o ponto de controle listado no plano de remuneração fixa do funcionário para localizar o valor do ponto de controle do nível de remuneração de um funcionário. O valor de ponto de controle será usado no lugar da taxa de pagamento fixo do funcionário como base do prêmio.
-   Selecione a opção**Número de unidades** para inserir um número de unidades padrão, o valor de cada unidade e na moeda do valor unitário se o plano de remuneração não for em dinheiro (por exemplo, 200 unidades do estoque, que são avaliadas em 40 reais) ou apenas o número de unidades caso o plano de remuneração seja um para um prêmio em dinheiro. Para um prêmio em dinheiro, o funcionário receberá o número especificado de unidades da moeda usada para o plano de remuneração fixa (por exemplo, 500 unidades de 1 real). O controle de relação de um para um pode ser usado para indicar se há um mapeamento de um para um entre o número de unidades e o valor da unidade. Ao criar um plano de remuneração variável para um plano com pagamentos em dinheiro usando o número de unidades, essa opção é automaticamente bloqueada como **Sim**, e a unidade de valor é **1.0000**.

A configuração **Regra de contratação** permite especificar se todos os funcionários devem receber o mesmo aumento, independentemente da data em que foram contratados (**Regra de contratação** = **Nenhum**), ou se os funcionários devem receber uma porcentagem de prêmio que se baseia no período de contratação durante o ciclo (**Regra de contratação** = **Percentual**). 

O **Aproveitamento** permite que você ajuste o prêmio de um funcionário com base no desempenho do departamento do funcionário. As métricas de desempenho podem ser definidas para cada departamento na página **Departamentos**, em **Formulários relacionados** &gt; **Remuneração** &gt; **Desempenho**. O prêmio que os funcionários nesse departamento recebem depende do valor do campo **Porcentagem da meta alcançada**, que indica o desempenho do departamento:

-   Se o desempenho do departamento for 100, o prêmio dos funcionários no departamento será fatorado pela porcentagem que é definida no campo**Pagamento em 100%**.
-   Se o desempenho do departamento tiver mais de 100, o sistema adicionará a porcentagem definida no campo **1% sobre o objetivo** para a porcentagem que é definida no campo **Pagamento em 100%** até que o valor que é definido no campo **Maior pagamento permitido** seja atingido.
-   Se o desempenho do departamento tiver menos de 100, o sistema subtrairá a porcentagem definida no campo **1% abaixo do objetivo** da porcentagem que é definida no campo **Pagamento em 100%** até que o valor que é definido no campo **Menor pagamento permitido** seja atingido.

Você pode definir**níveis de tolerância** em percentuais de limite, de forma que uma mensagem de aviso seja exibida se a aproveitamento fizer com que a porcentagem esteja fora da porcentagem do limite. 

Por padrão, o sistema procura o departamento definido na posição do funcionário. No entanto, o prêmio de alguns funcionários pode depender do desempenho de vários departamentos. Neste caso, os vários departamentos e a porcentagem do prêmio alocada ao desempenho de cada departamento podem ser definidos na inscrição de remuneração variável do funcionário. Para obter mais informações, consulte a seção “Inscrição de remuneração variável”. 

O aproveitamento será usado somente se **Pagamento por desempenho** estiver selecionado quando o processo de remuneração for executado. 

A guia **Substituições de níveis** permite que você substitua a porcentagem padrão do prêmio ou o número de unidades, com base no nível de remuneração do funcionário. Se **Habilitar substituições nos níveis** for definido como **Sim** para os funcionários que estão inscritos no plano de remuneração variável, o sistema obtém o nível do trabalho de um funcionário e procura-o na tabela de substituições para determinar a porcentagem ou o número de unidades para o nível. Se o nível não for encontrado na tabela de substituições, a porcentagem ou o número de unidades padrão na guia **General** serão usadas. A porcentagem e o número de unidades também podem ser substituídos na inscrição de funcionários no plano de remuneração variável.

## <a name="variable-compensation-enrollment"></a>Inscrição em remuneração variável
### <a name="determine-who-is-eligible-for-the-plan"></a>Determina quem está qualificado para o plano

Quando você estiver pronto para realizar a inscrição dos funcionários em um plano de remuneração variável, a primeira etapa é determinar quem está qualificado para a remuneração que é especificada no plano. Você não pode atribuir um plano para os funcionários, a não ser que você determine a qualificação. Para configurar a qualificação, abra a página **Regras de qualificação** para criar uma nova regra de qualificação para seu plano, e definir os critérios que um funcionário se atingir para o plano de remuneração. Você pode limitar a qualificação por departamento, associação de trabalhadores, região de remuneração (localização), trabalho, função de trabalho, tipo de trabalho e/ou nível de remuneração. Os funcionários podem ser inscritos em um plano de remuneração somente se atenderem **todos** os critérios que são definidos na regra de qualificação. 

**Nota:** As regras de qualificação determinam a qualificação para planos de remuneração fixa variável. As regras de qualificação usam os campos a seguir no registro de trabalho, cargo e funcionários para determinar se um funcionário está qualificado para um plano de remuneração:

-   Na página **Trabalho**:
    -   O campo **Trabalho**.
    -   Os campos **Função** e **Tipo de trabalho** na guia **Classificação do trabalho**
    -   O campo **Nível** na guia **Remuneração**
-   Na página **Posições**: os campos **Departamento** e **Região de remuneração**.
-   Na página **Funcionários**: as informações sobre as associações de funcionários que estão associadas ao funcionário em **Informações pessoais** &gt; **Associações de funcionários** na guia ****Funcionário****

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a>Habilitar a inscrição para o plano de remuneração variável.

Na página **Planos de remuneração variável**, defina a opção **Habilitar inscrição** para **Sim** para permitir que os funcionários qualificados sejam inscritos no plano.

### <a name="enroll-the-employee"></a>Inscrever o funcionário.

Agora, você pode inscrever funcionários no plano de remuneração variável. Para inscrever um funcionário, vá para a página **Funcionários** e selecione o funcionário. Em seguida, no Painel de Ação, clique em **Remuneração** &gt; **Inscrição do plano variável**. 

**Nota:** **Inscrição** deve estar definido como **Sim** no plano de remuneração variável. O campo **Plano** mostra somente os planos para os quais o funcionário estiver qualificado com base nas regras de qualificação que estão configuradas para esses planos. Se nenhuma regra de qualificação for configurada para um plano, nenhum funcionário será qualificado para o plano. 

Verifique se o campo **Data efetiva** está definido corretamente. Se o plano de remuneração variável usa o método de cálculo **Composição**, a data efetiva de registro pode ser considerada durante o cálculo do prêmio do funcionário. 

Você pode usar a guia **Substituições** para substituir os valores específicos para o funcionário. Por exemplo, se a **Regra de contratação** estiver definida como **Percentual** no plano e uma data de contratação diferente deve ser usado durante o cálculo da porcentagem de contratação do funcionário, você pode definir a data de contratação no campo **Data da regra de contratação**. Também é possível substituir o valor **Porcentagem do prêmio** ou o valor **Número de unidades** para um funcionário específico, dependendo das configurações do plano. Esses valores ainda são fatorados pela regra de contratação, por fatores de desempenho e por outras configurações do plano. 

**Substituições da organização** são usadas para basear o prêmio de um funcionário no desempenho de um ou vários departamentos. A porcentagem que está alocada entre departamentos deve totalizar 100 por cento. O desempenho individual do funcionário também é considerado. Essas configurações são usadas apenas se o **Pagamento por desempenho** estiver selecionado quando o processo de remuneração é executado.

<a name="see-also"></a>Consulte também
--------

[Planos de remuneração](compensation-plans.md)




