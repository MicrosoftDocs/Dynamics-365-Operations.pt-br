---
title: Visão geral do gerenciamento de benefícios
description: Este artigo fornece uma visão geral do recurso Gerenciamento de benefícios no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/06/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 261d71e955e4cb1a4a461d59725c631248e10b17
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227887"
---
# <a name="benefits-management-overview"></a>Visão geral do gerenciamento de benefícios


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Para permanecer em um mercado competitivo, é necessário oferecer um conjunto amplo de benefícios para atrair e reter os melhores funcionários. Além dos benefícios padrão, como plano de saúde e odontológico, ofereça serviços expandidos, como assistência à adoção, programas de recreação e auxílio-vestimenta. O Gerenciamento de benefícios do Microsoft Dynamics 365 Human Resources oferece uma solução flexível compatível com uma ampla variedade de opções de benefícios. O Human Resources também inclui uma experiência para funcionários fácil de usar e que mostra as ofertas.

- Os planos de benefícios aprimorados permitem criar e gerenciar planos de benefícios exclusivos e oferecem suporte a tabelas de taxas de benefícios complexas e camadas aninhadas. Você pode facilmente criar programas e pacotes de benefícios, além de regras de inscrição automática nos benefícios para facilitar a experiência dos funcionários.
- Os programas de crédito flexível permitem ratear para oferecer suporte à aposentadoria e outros eventos de vida.
- As regras de elegibilidade extensivas garantem a disponibilização dos benefícios apropriados para os funcionários certos.
- A inscrição online nos benefícios permite uma experiência fácil para os funcionários.
- O processamento de eventos de vida útil é compatível com eventos de vida futuros.

Se deseja acessar os dados de demonstração, será necessário implementar novamente o ambiente de área restrita.

> [!NOTE]
> Agora você pode personalizar as páginas de gerenciamento de Benefícios. Campos personalizados relacionados a taxas de cobertura podem ser adicionados à página **Opção de cobertura** para planos de benefício. Para obter mais informações sobre como trabalhar com campos personalizados, consulte [Campos personalizados](hr-developer-custom-fields.md).
>
> ![Campos personalizados de gerenciamento de benefícios](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Habilitar o Gerenciamento de benefícios

Este artigo descreve como acionar os recursos no Human Resources. Ele também explica quais recursos existentes no Human Resources são substituídos pelo Gerenciamento de benefícios e quais recursos são desabilitados após ativar o Gerenciamento de benefícios.

> [!IMPORTANT]
> Depois de habilitar o gerenciamento de benefícios em um ambiente de **Produção** você pode desativá-lo. É recomendável habilitar e testar o gerenciamento de benefícios em um ambiente de **Área restrita** antes de ativá-lo em um ambiente de **Produção**. Há diferenças significativas entre a funcionalidade de benefício herdada e a nova funcionalidade de gerenciamento de benefícios que exigem configuração adicional e devem ser testadas antes de serem colocadas em produção.

Para obter mais informações, consulte [Gerenciar recursos](hr-admin-manage-features.md).

## <a name="process-overview"></a>Visão geral do processo

O processo de configuração de benefícios envolve as seguintes tarefas:

1.  Configurar as informações de benefícios obrigatórias.
2.  Configurar as informações de benefícios opcionais.
3.  Configurar planos de benefícios.
4.  Configurar programas de crédito flexível (opcional).
5.  Configurar informações de funcionário obrigatórias.
6.  Configurar informações de funcionário opcionais.
7.  Processar funcionários para determinar a qualificação.
8.  Os funcionários selecionam planos por meio do auto-atendimento para funcionários (opcional).
9.  Confirmar seleções de plano de funcionário.
10. Processamento de eventos de vida (opcional).
11. Atualizações de taxa (opcional).

## <a name="set-up-required-benefit-information"></a>Configurar as informações de benefícios obrigatórias

Antes que os funcionários possam estar inscritos nos planos, vários componentes devem ser configurados:

- **Parâmetros de gerenciamento de benefícios** – essas configurações são compartilhadas entre as empresas. Você pode definir códigos de motivo padrão, habilitar a opção **Salário anual de benefícios**, definir uma frequência de pagamento padrão para novos contratados e habilitar eventos de vida. Para obter mais informações, consulte [Definir parâmetros de gerenciamento de benefícios](hr-benefits-setup-parameters.md).
- **Opções de qualificação para contato pessoal** – contatos pessoais são as pessoas que serão dependentes ou beneficiários dos planos configurados. Normalmente, são crianças, cônjuges ou organizações confiáveis. Para obter mais informações, consulte [Configurar opções de qualificação para contato pessoal](hr-benefits-setup-contact-eligibility-options.md).
- **Opções de cobertura** – configura os tipos de cobertura que estarão disponíveis para um plano. Especificamente, defina quem deve estar dentro do escopo de cobertura ou a quantidade de cobertura disponível. Para obter mais informações, consulte [Criar opções de cobertura](hr-benefits-setup-coverage-options.md).
- **Tipos de plano** – definem os tipos de planos que estarão disponíveis quando você criar um plano de benefícios. Exemplos de tipos de plano incluem **Odontológico**, **Oftalmológico** e **Poupança**. Algumas configurações importantes no tipo de plano determinam as configurações disponíveis no plano de benefícios. Para obter mais informações, consulte [Criar tipos de plano](hr-benefits-setup-plan-types.md).
- **Regras de qualificação** – as regras de qualificação são usadas para determinar se um funcionário está qualificado para um plano. Pelo menos uma regra de qualificação deve estar associada a cada plano de benefício. Para obter mais informações, consulte [Configurar opções e regras de qualificação](hr-benefits-setup-eligibility-rules.md).
- **Frequências de pagamento** – as frequências de pagamento são necessárias quando as taxas de benefício são configuradas. A frequência de pagamento usada em uma taxa ajuda a identificar o valor que o funcionário e/ou empregador deve ter em uma base semanal, mensal ou anual. Para obter mais informações, consulte [Configurar frequências de pagamento](hr-benefits-setup-payment-frequencies.md).
- **Taxas** – as taxas definem o valor que o funcionário ou o empregador deverão pagar pelo benefício. Se o dinheiro tiver que ser devolvido a um funcionário (por exemplo, um crédito em relação a uma associação na academia), será inserida uma taxa negativa. Para obter mais informações, consulte [Configurar taxas](hr-benefits-setup-rates.md).
- **Taxas de nível** – as taxas de nível são aplicadas quando uma taxa tiver que ser alterada com base em alguns critérios. A taxa de nível mais comum é um nível único baseado na idade. No entanto, as taxas de nível duplas também podem ser configuradas, em que a taxa pode ser alterada com base no gênero, na idade ou em outros critérios.
- **Deduções** – as deduções são basicamente as informações de cabeçalho/códigos que serão passadas para o sistema de folha de pagamento para identificar a dedução do benefício. Você deve configurar essas deduções, pois elas serão necessárias no plano de benefícios. Para obter mais informações, consulte [Configurar deduções](hr-benefits-setup-deductions.md).
- **Períodos de benefícios** – um período de benefício é o período em que os funcionários terão cobertura de benefícios. Também é conhecido como um ano de planejamento. Os períodos de registro abertos também são configurados aqui.

## <a name="set-up-optional-benefit-information"></a>Configurar as informações de benefícios opcionais

Os componentes abaixo não precisam ser configurados para criar um plano de benefícios:

- **Programas** – um programa é um conjunto de benefícios regidos pelas mesmas regras de qualificação. Por exemplo, todos os usuários do departamento de vendas podem obter um celular.
- **Pacotes** – um pacote é um grupo de benefícios, no qual um plano deve ser selecionado antes que a opção para selecionar planos adicionais esteja disponível. Por exemplo, um plano médico altamente dedutível pode ser combinado com um plano de conta poupança de saúde (HSA).
- **Tipos de eventos de vida** – os eventos de vida são eventos que permitem uma alteração na cobertura de um funcionário. Os tipos de eventos de vida são vinculados a um tipo de plano. Por exemplo, um tipo de plano médico pode permitir alterações nos planos devido a um nascimento ou adoção ou por conta de uma alteração no estado civil. No entanto, um tipo de seguro pode não permitir alterações por conta de eventos de vida. Para obter mais informações, consulte [Configurar tipos de eventos de vida](hr-benefits-setup-life-event-types.md).
- **Dias de espera e períodos de espera** – uma cobertura de um período de espera pode ser definida em um plano de benefícios. Por exemplo, um funcionário recém contratado pode ser capaz de se inscrever em um 401 (k) somente após três meses de trabalho. Nesse caso, o período de espera é de três meses. Os dias de espera são usados no período de espera se novas registradoras podem ser processadas e enviadas ao provedor somente em um dia específico do mês. Por exemplo, se as inscrições 401 (k) só puderem ser processadas no décimo quinto dia do mês, após três meses de trabalho, o período de espera configurado será de três meses e o dia de espera será o décimo quinto dia. Para obter mais informações, consulte [Configurar dias de espera](hr-benefits-setup-waiting-days.md) e [Configurar períodos de espera](hr-benefits-setup-waiting-periods.md).
- **Códigos de motivo** – os códigos de motivo são usados para explicar por que um benefício pode ser alterado para um funcionário. Para obter mais informações, consulte [Configurar códigos de motivo](hr-benefits-setup-reason-codes.md).

## <a name="set-up-benefit-plans"></a>Configurar planos de benefícios

Ao configurar um plano de benefícios, você deve concluir as seguintes etapas para que os funcionários possam se inscrever:

- Atribuir um período de benefício.
- Anexar opções de cobertura.
- Defina uma validade de atribuição e uma data de validade máxima na guia **Geral**.
- Atribua pelo menos uma regra de qualificação.
- Defina o campo **Permitir/continuar inscrição** na guia **Configuração**.

Para obter mais informações sobre como configurar os planos de benefícios, consulte [Configurar planos de benefícios](hr-benefits-plans-setup.md).

## <a name="set-up-flex-credit-programs-optional"></a>Configurar programas de crédito flexível (opcional)

É possível usar os programas de crédito flexível para inscrever funcionários em benefícios de acordo com um número predeterminado de créditos flexíveis. Os funcionários podem escolher como alocar seus créditos flexíveis. Por exemplo, se os funcionários já estiverem cobertos pelo seguro de saúde de seu cônjuge, eles não precisarão usar os créditos para a cobertura de saúde. Portanto, eles podem querer usá-los para outros benefícios. Para obter mais informações sobre programas de crédito flexível, consulte [Configurar programas de crédito flexível](hr-benefits-plans-flex-credit-programs.md).

## <a name="configure-required-employee-information"></a>Configurar informações de funcionário obrigatórias

Para poder inscrever funcionários em benefícios, você deve fornecer as informações. 

O funcionário deve ter uma **Posição** atribuída a ele. Uma **Posição** pode ser atribuída ao funcionário nas páginas **Trabalhador** ou **Posição**, atualizando a **Atribuição do trabalhador**. 

Depois disso, os funcionários serão inscritos em um plano de compensação fixo na data de início ou deve ter um valor de **Valor do salário de benefícios anual**. Antes de atribuir **Remuneração fixa** a um funcionário, uma **Posição** deve ser atribuída. 

> [!NOTE] 
> A **Data de início de remuneração fixa** não pode ser anterior à **Data de atribuição da posição**.

Como alternativa, se você tem um funcionário que recebe remuneração suplementar, como comissões, é possível adicionar um valor de **Salário de benefícios anual** do registro do funcionário. O Human Resources usará o valor do **Salário de benefícios anual** para determinar valores de cobertura em vez do valor de **Remuneração fixa anual**. O **Salário de benefícios anual** deve ser válido a partir da data de início do funcionário ou do início do período de benefício, o que for mais recente. No entanto, não é necessário uma posição para atribuir o **Salário de benefícios anual**. Para habilitar o recurso **Salário de benefícios anual**, acesse a página **Parâmetros compartilhados do Human Resources**, na guia **Gerenciamento de benefícios** . Esse recurso está desativado por padrão.

> [!IMPORTANT]
> Se um valor de **Remuneração fixa** e um valor de **Salário de benefícios anual** é inserido para um funcionário, o **Salário de benefícios anual** será usado para determinar os valores de cobertura. Na seção **Detalhes do emprego** da página **Trabalhador**, você deve selecionar um valor no campo **Frequência de pagamento de benefício**.

## <a name="configure-optional-employee-information"></a>Configurar informações opcionais de funcionário
Quando você cria um plano de benefícios que usa taxas baseadas em sexo ou idade, você deve inserir uma data de nascimento e um sexo para que o funcionário calcule o custo de benefício.

## <a name="process-employees-to-determine-eligibility"></a>Processar funcionários para determinar a qualificação
Antes que os funcionários possam se inscrever nos planos, o processamento de elegibilidade é executado para determinar para quais planos eles estão qualificados. Você pode visualizar os resultados do processo de elegibilidade no **Visualizador de resultados do processo**. Para obter mais informações, consulte [Processar elegibilidade de inscrição](hr-benefits-process-enrollment-eligibility.md).

## <a name="employees-select-plans-using-employee-self-service-optional"></a>Os funcionários selecionam planos usando o **Autoatendimento para funcionários** (opcional)

Quando ocorre a inscrição aberta, os funcionários são recém-contratados, ou ocorre um evento de vida, os funcionários podem selecionar ou atualizar seus benefícios usando o **Autoatendimento para funcionários**. Para obter mais informações, consulte [Configurar o autoatendimento do funcionário](hr-benefits-setup-employee-self-service.md).

## <a name="confirm-employee-plan-selections"></a>Confirmar seleções de plano de funcionário

Os benefícios que os funcionários selecionam devem ser confirmados antes que os funcionários sejam considerados inscritos neles. Os benefícios também podem ser selecionados em nome de um funcionário. Para selecionar ou confirmar benefícios, na página **Funcionário**, na guia **Benefícios**, selecione **Planos de benefícios de trabalhadores**. Para selecionar ou confirmar benefícios para vários funcionários, use a página **Atualização em massa dos planos de benefícios do trabalhador**.

## <a name="life-event-processing-optional"></a>Processamento de eventos de vida (opcional)

Durante a vida de um funcionário, ele pode vivenciar vários eventos de vida, como casamento, mudanças de emprego ou mudanças em dependentes ou beneficiários. Para usar eventos de vida, você deve habilitá-los na página **Parâmetros compartilhados de recursos humanos**. Configure tipos de eventos de vida e opções de eventos de vida para tipos de planos.

Antes de poder processar eventos de vida, você já deve ter executado a inscrição aberta pelo menos uma vez durante um período de contratação. Nos Estados Unidos, a inscrição aberta costuma ocorrer uma vez por ano. Fora dos Estados Unidos, a inscrição aberta pode ser realizada no momento da contratação. O processamento de eventos de vida não exige que os trabalhadores selecionem um plano de benefícios. No entanto, os trabalhadores devem ter sido incluídos no processamento de inscrições abertas. Para obter mais informações, consulte os seguintes tópicos:

- [Processar eventos de vida](hr-benefits-process-life-events.md)
- [Processar alterações de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Processar qualificação para eventos de vida](hr-benefits-process-life-event-eligibility.md)

Depois que o processamento de eventos da vida for concluído e por enquanto o período de inscrição de evento da vida estiver aberto, os funcionários poderão fazer alterações nas opções de plano afetadas pelo evento da vida. Os administradores podem fazer as alterações em nome dos funcionários. Depois que o período de inscrição terminar e nenhum tipo de plano não confirmado estiver relacionado à transação de evento da vida, a transação será fechada.

Todos os planos afetados pelo evento da vida devem ser selecionados ou renunciados e confirmados. Se um plano não estiver selecionado, não estiver renunciado e, portanto, não estiver confirmado, a transação do evento da vida não será fechada.

Os administradores podem fechar manualmente uma transação de evento da vida conforme necessário, selecionando-a e selecionando **Fechar**. Se houver planos não confirmados na transação e um administrador quiser fechá-lo, o fechamento do evento da vida poderá restringir as modificações a esses planos.

Não é possível excluir eventos da vida fechados.

Os administradores podem reabri uma transação de evento da vida conforme necessário, selecionando-a e selecionando **Reabrir**.

## <a name="rate-updates-optional"></a>Atualizações de taxa (opcional)

Às vezes, a taxa de um benefício muda durante o período do plano. Para atualizar as taxas para os funcionários que já estão inscritos no plano, você deve processar as mudanças de taxa. Para obter mais informações, consulte [Processar mudanças de taxa](hr-benefits-process-rate-changes.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
