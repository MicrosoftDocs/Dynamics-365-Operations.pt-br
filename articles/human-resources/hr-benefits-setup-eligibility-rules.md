---
title: Configurar regras e opções de qualificação
description: Este tópico descreve como definir as opções e regras de qualificação no gerenciamento de Benefícios no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e87bef8994fe1eac0089764c8d4f9b18289c13ea
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069621"
---
# <a name="configure-eligibility-rules-and-options"></a>Configurar regras e opções de qualificação 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Depois de configurar os parâmetros necessários para o gerenciamento de benefícios, você poderá criar regras, pacotes, períodos e programas de qualificação que serão associados aos seus planos de benefícios.

As regras de qualificação são usadas para determinar se os funcionários estão qualificados para um plano. Os funcionários devem atender à condição de, pelo menos, uma regra para serem considerados qualificados para o benefício. Por exemplo, você tem duas regras em um plano. A primeira regra (linha 1) informa que o tipo de funcionário deve ser **Funcionário**. A segunda regra (linha 2) informa que o funcionário deve ser um funcionário em tempo integral. Portanto, os funcionários que atendem à regra 1 são qualificados mesmo se estiverem empregados apenas em meio período.

No entanto, você pode configurar uma única regra que tenha várias condições. Nesse caso, os funcionários devem atender a todas as condições da regra para serem considerados qualificados para o benefício. Por exemplo, você tem uma regra chamada **Funcionário em período integral**. Esta regra informa que o tipo de funcionário deve ser **Funcionário** *e* o funcionário deve estar empregado em período integral. Portanto, os funcionários devem atender às duas condições da regra para serem qualificados.

> [!IMPORTANT]
> Pelo menos uma regra de qualificação deve estar associada a cada plano de benefício. É possível associar várias regras a um benefício.

## <a name="create-an-eligibility-rule"></a>Criar um regra de qualificação

As regras de qualificação definem quais funcionários podem se inscrever em cada plano de benefícios. Depois de definir as regras de qualificação, você as atribui aos planos de benefícios. Depois, você poderá processar a qualificação da inscrição para verificar quais funcionários são qualificados para cada plano. 

Durante a inscrição aberta, os funcionários poderão selecionar planos de benefícios. Se eles se tornarem qualificados para um plano de benefícios com base nas regras de qualificação depois de já estarem inscritos, eles não serão inscritos automaticamente. Em geral, quando ocorre um evento de vida que afeta a qualificação do plano, é iniciado um período de inscrição para que o funcionário selecione os planos aos quais está qualificado. 

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Regras e opções de qualificação**.

2. Na guia **Regras de qualificação**, selecione **Novo** para criar uma regra de qualificação. Para ver os planos associados a uma regra de qualificação, selecione **Planos anexados**.

3. Especifique valores para os seguintes campos.

   | Campo | descrição |
   | --- | --- |
   | **Regra de qualificação** | Um identificador exclusivo para a regra de qualificação. |
   | **Descrição** | Uma descrição da regra de qualificação. |
   | **Válido a partir da data e hora** | A data de início da regra de qualificação. | 
   | **Válido até a data e hora** | A data de término da regra de qualificação. |
   | **Tipo de funcionário do usuário** | Especifica se o tipo de funcionário deve ser usado na regra de qualificação do benefício. |
   | **Tipo de trabalhador** | O tipo de trabalhador, se a alternância **Usar tipo de funcionário** estiver definida como **Sim**. |
   | **Usar status do funcionário** | Especifica se o status de emprego do funcionário deve ser usado na regra de qualificação do benefício. |
   | **Status** | O status de emprego, se a alternância **Usar status do funcionário** estiver definida como **Sim**. Se a opção **Usar status do funcionário** estiver definida como **Não**, o campo não será usado. |
   | **Usar categoria de emprego** | Especifica se o valor **Categoria de emprego** do funcionário deve ser usado como parte da regra de qualificação do benefício. | 
   | **Categoria de emprego** | A categoria de emprego do funcionário se a opção **Usar categoria de emprego** estiver definida como **Sim**. |
   | **Usar nova regra de contratação** | Especifica se o valor de um novo período de contratação deve ser usado como parte da regra de qualificação de benefícios. |
   | **Período de inscrição** | O período em que a nova inscrição de contratação é permitida. Se você também defini-lo em parâmetros, a configuração de parâmetros terá prioridade sobre ele. |
   | **Usar status de emprego anterior** | Especifica se deve usar um status de emprego anterior do funcionário como parte da regra de qualificação do benefício. Por exemplo, você pode especificar uma regra de qualificação que renuncia a um período de espera de cobertura para todos os funcionários que fizeram a transição de um status **Demitido** para um **Empregado** em 90 dias de seu emprego anterior. |

4. Em **Critérios adicionais**, selecione as seguintes opções e adicione as informações, conforme necessário.

   | Opção | descrição |
   | --- | --- |
   | **Idade qualificada** | Especifica a faixa etária ou faixas necessárias para satisfazer a regra de qualificação. |
   | **Departamento qualificado** | Especifica o departamento ou departamentos em que um funcionário deve estar para satisfazer a regra de qualificação. |
   | **Tipo de emprego qualificado** | Especifica o tipo ou tipos de emprego que um funcionário deve ser categorizado para satisfazer a regra de qualificação. Por exemplo, período integral ou meio período. |
   | **Trabalho qualificado** | Especifica o trabalho ou trabalhos que satisfazem a regra de qualificação. Os trabalhos são associados a posições, com estas são preenchidas pelos funcionários. |
   | **Função de trabalho qualificada** | Especifica a função ou funções do trabalho que satisfazem uma regra de qualificação. Por exemplo, vendedores ou técnicos. |
   | **Tipo de trabalho qualificado** | Especifica o tipo ou tipos de trabalho que satisfazem a regra de qualificação. Por exemplo, administrativo ou executivo. |
   | **Entidade legal qualificada** | Especifica a entidade legal ou entidades legais válidas para a regra de qualificação. Por exemplo, Contoso Entertainment System USA. |
   | **Região de remuneração qualificada** | Especifica o local do funcionário que satisfaz a regra de qualificação. Por exemplo, EUA central. |
   | **Posição qualificada** | Especifica a posição ou posições que satisfazem a regra de qualificação. Por exemplo, assistente de RH ou gerente de RH. |
   | **Tipo de posição qualificado** | Especifica o tipo ou tipos de posição que satisfazem a regra de qualificação. Por exemplo, período integral. |
   | **Estado qualificado** | Especifica os estados ou províncias que satisfazem a regra de qualificação. Por exemplo, Dakota do Norte (EUA) ou Colúmbia Britânica (Canadá). |
   | **Condições de emprego qualificadas** | Especifica os contratos de trabalho que satisfazem a regra de qualificação. Por exemplo, à vontade ou contrato de grupo. |
   | **Sindicato qualificado** | Especifica as associações sindicais que satisfazem a regra de qualificação. Por exemplo, Forklift Drivers of America.</br></br>Ao usar uma regra de qualificação baseada em sindicato, o registro sindical do trabalhador deve ter a data de término preenchida. Não é possível deixar em branco. |
   | **CEP qualificado/código postal** | Especifica os CEPs/códigos postais que satisfazem a regra de qualificação. Por exemplo, 58104. |

5. Em **Detalhes adicionais**, é possível ver os seguintes detalhes adicionais.

   | Campo | descrição |
   | --- | --- |
   | **Campo de usuário qualificado** | Especifica regras de qualificação adicionais com base nos campos definidos pelo cliente. |
   | **Tipo de qualificação** | Especifica a categoria de critério que você selecionou em **Critérios adicionais**. |
   | **Referência de qualificação** | Especifica os valores que você selecionou em **Critérios adicionais**. |
   | **Descrição** | A descrição que você selecionou em **Critérios adicionais**. |

6. Selecione **Salvar**.

## <a name="using-custom-fields-in-eligibility-rules"></a>Usando campos personalizados nas regras de qualificação

[Campos personalizados](hr-developer-custom-fields.md) podem ser criados em Recursos Humanos para rastrear informações adicionais. Esses campos podem ser adicionados diretamente à interface do usuário, e uma coluna é dinamicamente adicionada à tabela base.  

Os campos personalizados podem ser usados no processo de qualificação. As regras de qualificação podem usar um ou mais valores de campos personalizados para determinar a qualificação de um funcionário.  Para adicionar um campo personalizado a uma regra existente ou para criar uma nova regra, Acesse **Gerenciamento de benefícios > Links > Configuração > Regras de qualificação > Qualificação de campo personalizado**. Nesta página, você pode criar uma regra que usa um ou vários campos personalizados, além de poder definir vários valores para cada campo personalizado, a fim de determinar a qualificação.

As tabelas a seguir dão suporte a campos personalizados que podem ser usados no processamento de qualificação:

- Trabalhador (HcmWorker)  
- Trabalho (HcmJob)  
- Posição (HcmPosition)  
- Detalhes da Posição (HcmPositionDetail)  
- Atribuição do Trabalhador da Posição  
- Emprego (HcmEmployment)  
- EmploymentDetails (HcmEmploymentDetails)  
- Detalhes do Trabalho (HcmJobDetails)  

Os tipos de campo personalizados a seguir são suportados no processamento de qualificação:

- Texto  
- Lista de separação  
- Número  
- Decimal  
- Caixa de seleção  

A tabela a seguir mostra informações do campo de formulário de qualificação para campo personalizado.

| Campo  | descrição |
|--------|-------------|
| Organização | Nome dos critérios que estão sendo criados. |
| Nome da tabela | O nome da tabela que contém o campo personalizado que está sendo usado para a regra de qualificação. |
| Nome do campo | O campo que será usado para a regra de qualificação. |
| Tipo de operador | Exibe o operador usado na configuração de qualificação para o campo personalizado. |
| Alíquota | Exibe o valor usado na configuração de qualificação para o campo personalizado. |

## <a name="eligibility-logic"></a>Lógica de qualificação

As seções a seguir descrevem como a qualificação de benefícios é processada.

### <a name="rules-assigned-to-a-plan"></a>Regras atribuídas a um plano 
Quando várias regras de qualificação são atribuídas a um plano de benefícios, um funcionário deve atender a pelo menos uma regra para ser qualificado para inscrição no plano de benefícios.  No exemplo a seguir, o funcionário deve atender aos requisitos da regra de **Tipo de trabalho** ou da regra **Funcionários ativos**.

![O funcionário deve atender aos requisitos da regra de Tipo de trabalho ou da regra Funcionários ativos.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>Critérios em uma regra de qualificação 
Em uma regra, você define os critérios que formam a regra. No exemplo acima, o critério para a regra **Tipo de trabalho** é onde Tipo de trabalho = Diretores. Portanto, o funcionário deve ser um diretor elegível. Esta é uma regra na qual há apenas um critério na regra.

Você pode definir regras que têm vários critérios. Quando você define vários critérios em uma regra de qualificação, um funcionário deve atender a todos os critérios dentro da regra para ser elegível ao plano de benefícios. 

Por exemplo, a regra **Funcionários ativos** acima é composta pelos critérios a seguir. Para que o funcionário seja elegível com base na regra de **Funcionários ativos**, o funcionário deve ser empregado em USMF da entidade legal *e* ter um tipo de posição de tempo integral.  

![Critérios em uma regra de qualificação.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>Várias condições nos critérios

As regras podem ser expandidas para usar várias condições em um único critério. O funcionário deve atender a pelo menos uma condição para ser elegível. Para criar no exemplo acima, a regra **Funcionários ativos** pode ser expandida para incluir funcionários que também são funcionários de meio expediente. Como resultado, agora o funcionário deve ser um funcionário em USMF *e* um funcionário de tempo integral ou de meio período.  

![Várias condições nos critérios.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>Condições de qualificação em um critério de campo personalizado 
Semelhante à acima, os campos personalizados podem ser usados ao criar regras de qualificação e trabalhar da mesma maneira. Por exemplo, você pode querer oferecer reembolso da Internet aos funcionários da Fargo e Copenhague que estão trabalhando em casa, pois os custos da Internet estão mais altos nesses locais. Para isso, crie dois campos personalizados: **Local do escritório** (lista de opções) e **Trabalho em casa** (caixa de seleção). Em seguida, crie uma regra chamada **Funcionários da WFH**. O critério para a regra é onde **Local do Escritório = Fargo** ou **Copenhague** *e*  onde **Trabalhar em casa = Sim**.

As regras de qualificação personalizadas precisam ser configuradas, conforme indicado na imagem a seguir. 

![Condições de qualificação em um critério de campo personalizado.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>Configurar pacotes

Pacotes são um conjunto de planos de benefícios relacionados. Você pode usar pacotes de benefícios para agrupar planos de benefícios que um funcionário deve escolher para se inscrever em determinados planos de benefícios que podem depender de outras inscrições no plano de benefícios. Exemplos de quando você pode querer usar um pacote incluem:

- Um pacote de plano de saúde que inclui seguro de saúde altamente dedutível com uma conta de poupança de saúde (HSA) associada.

- Um plano de seguro de vida com um plano de seguro de vida obrigatório para funcionários fornecido com um plano de vida do dependente. Isso garantiria que um funcionário não pudesse selecionar a cobertura de vida do dependente sem se inscrever na cobertura do funcionário.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Regras e opções de qualificação**.

2. Na guia **Pacotes**, selecione **Novo** para criar um pacote. Para ver os planos associados a um pacote, selecione **Planos anexados**.

3. Especifique valores para os seguintes campos.

   | Campo | descrição |
   | --- | --- |
   | **Pacote** | Um identificador exclusivo para o pacote. |
   | **Descrição** | Uma descrição do pacote. |
   | **Mestre** | Indica se um dos planos no pacote deve ser marcado como plano mestre. O plano mestre deve ser selecionado durante a inscrição aberta como parte do pacote antes que o administrador de benefícios possa confirmar as eleições de benefícios do funcionário. |
   | **Válido a partir da data e hora** | A data e hora em que o pacote fica ativo. |
   | **Válida até** | A data em que o pacote expira. O padrão é 12/31/2154, que representa nunca. |

4. Selecione **Salvar**.

## <a name="configure-periods"></a>Configurar períodos

Os períodos definem quando os benefícios estão em vigor e quando os funcionários podem se inscrever. Você pode criar quantos períodos desejar para manter os benefícios e abrir períodos de inscrição e cobertura de benefícios. Os anos do plano de benefícios podem ou não seguir um ano civil. 

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Regras e opções de qualificação**.

2. Na guia **Períodos**, selecione **Novo** para criar um período. Para executar um processo que anexa todos os planos de benefícios ativos válidos para o período do benefício, selecione **Anexar planos**. Para ver os planos associados a um pacote, selecione **Planos anexados**. 

3. Especifique valores para os seguintes campos.

   | Campo | descrição |
   | --- | --- |
   | **Período** | Um identificador exclusivo do período. |
   | **Válido a partir da data e hora** | A data e hora de início em que o período de benefícios está ativo. |
   | **Válido até a data e hora** | A data e hora em que o período de benefícios fica inativo. |
   | **Início da inscrição** | A data de início da inscrição aberta. A inscrição aberta é quando um funcionário pode fazer eleições de benefícios em benefícios de autoatendimento. |
   | **Fim da inscrição** | A data de término da inscrição aberta. |
   | **Aberta** | Indica se o período está aberto com base na data do sistema e nas datas e horas iniciais e finais válidos. | 
   | **Período anterior** | Especifica o período de benefícios que precede o período de benefícios selecionado. Essas informações são usadas durante a inscrição de qualificação para os benefícios para atribuir planos, opções de cobertura e representantes de um ano anterior. |
 
4. Selecione **Salvar**.

## <a name="use-a-flex-credit-program"></a>Usar um programa de crédito flexível

É possível usar os programas de crédito flexível para inscrever funcionários em benefícios de acordo com um número predeterminado de créditos flexíveis. Os funcionários podem escolher como alocar seus créditos flexíveis. Por exemplo, se um funcionário recebeu cobertura do plano de seguro de saúde de seu cônjuge, ele poderá usar os créditos que usaria na cobertura de saúde para obter outros benefícios.

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Regras e opções de qualificação**.

2. Na guia **Períodos**, selecione **Programas de crédito flexível**.

3. Selecione um programa de crédito flexível para aplicar. Os campos contêm as seguintes informações.

   | Campo | descrição |
   | --- | --- |
   | **ID do crédito do benefício** | O identificador exclusivo do programa de crédito flexível. |
   | **Descrição** | Uma descrição do programa de crédito flexível. | 
   | **Data Inicial** | A data em que o programa de crédito flexível se torna ativo. |
   | **Data Final** | A data final do programa de crédito flexível. Você pode deixar o valor padrão (31/12/2154) para indicar que o programa de crédito flexível não tem uma expiração programada. |
   | **Valor total do crédito** | O número de créditos que cada funcionário precisará usar para seus benefícios. |
   | **Regra de rateio** | A regra a ser usada para ratear créditos flexíveis quando um funcionário é contratado no meio do período do crédito flexível. </br></br><ul><li>**Nenhum** – O funcionário não recebe créditos flexíveis se for contratado após o início do período do programa.</li><li>**Crédito completo** – O funcionário recebe o valor total dos créditos flexíveis, independentemente de quando eles são contratados.</li><li>**Rateio** – O funcionário recebe um valor rateado de créditos flexíveis com base na data de início.</li></ul> |
   | **Fórmula de rateio do crédito flexível** | A regra a ser usada para rateio de créditos flexíveis para funcionários contratados no meio de um período de benefício para o programa de crédito flexível. O rateio é baseado na data de início do emprego. Esse campo é usado apenas se você selecionar **Rateio** no campo **Regra de rateio**. </br></br><ul><li>**Diário** – Rateia o número de créditos flexíveis que um funcionário recebe diariamente. O número total de créditos flexíveis é dividido pelo número de dias no período. Por exemplo, se seu período de benefício for de 400 dias, o sistema dividirá o número total de créditos flexíveis por 400 para calcular o número de créditos flexíveis que os funcionários recebem por dia.</li><li>**Mês atual** – Rateia o número de créditos flexíveis que um funcionário recebe mensalmente, arredondado para o mês atual. O número total de créditos flexíveis é dividido pelo número de meses no período. Por exemplo, se seu período de benefício for de 15 meses, o sistema dividirá o número total de créditos flexíveis por 15 para calcular o número de créditos flexíveis que os funcionários recebem por mês.</li><li>**Mês seguinte** – Rateia o número de créditos flexíveis que um funcionário recebe mensalmente, arredondado para o próximo mês. O número total de créditos flexíveis é dividido pelo número de meses no período. Por exemplo, se seu período de benefício for de 15 meses, o sistema dividirá o número total de créditos flexíveis por 15 para calcular o número de créditos flexíveis que os funcionários recebem por mês.</li></ul> |
   
   Certifique-se de que cada plano de benefício esteja inscrito em apenas um programa de crédito flexível por período de benefício. Caso contrário, o sistema não saberá qual programa de crédito flexível usar para conceder créditos flexíveis, e você encontrará problemas. 

## <a name="configure-programs"></a>Configurar programas

Os programas são um conjunto de planos de benefícios que compartilham um conjunto comum de regras de qualificação. Você pode definir regras de qualificação para todo o programa em vez de para cada plano individual. Por exemplo, um programa FTE da Contoso Canadá ou programa executivo da Contoso Europa. 

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Regras e opções de qualificação**.

2. Na guia **Programas**, selecione **Novo** para criar um programa. Para abrir exceções para funcionários que não atendem aos requisitos da regra de qualificação, selecione **Substituição da regra de qualificação**. Para ver os planos associados a um programa, selecione **Planos anexados**.

3. Especifique valores para os seguintes campos.

   | Campo | descrição |
   | --- | --- |
   | **Programa** | Um identificador exclusivo para o programa. |
   | **Descrição** | Uma descrição do programa. | 
   | **Válido a partir da data e hora** | A data e hora em que o programa fica ativo. |
   | **Válido até a data e hora** | A data e hora em que o programa expira. O padrão é 12/31/2154, que representa nunca. |
   | **Período de espera da cobertura** | O período que um funcionário deve esperar antes do início da cobertura do programa de benefícios. |
   | **Período de espera da dedução** | O período que um funcionário espera antes do início das deduções para o programa de benefícios. |
   | **Regras de qualificação** | Selecione as regras de qualificação a serem aplicadas ao programa de benefícios. Defina as regras de qualificação na guia **Regras de qualificação** nesta página. |
   
4. Selecione **Salvar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
