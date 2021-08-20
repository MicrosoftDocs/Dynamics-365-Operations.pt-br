---
title: Configurar parâmetros de recursos do Human Resources
description: Este tópico explica como configurar parâmetros específicos da empresa no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 476f44c665adb2918e7cd882d4ea873b4b4f94fa33a74dc96d3eccc74b676ce5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739242"
---
# <a name="configure-human-resources-parameters"></a>Configurar parâmetros de recursos do Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

As configurações de alguns parâmetros do Human Resources são compartilhadas entre empresas, enquanto as configurações de outros parâmetros são específicas da empresa. Este tópico explica como configurar parâmetros específicos da empresa no Human Resources.

Duas páginas são usadas para definir parâmetros de recursos humanos. Para os parâmetros que são compartilhados entre empresas, use a página **Parâmetros compartilhados de recursos humanos**. Para os parâmetros que são específicos da empresa (ou seja, as configurações se aplicam a uma única empresa), use a página **Parâmetros de recursos humanos**.

![Acesse Parâmetros de recursos humanos.](./media/hr-employee-self-service-human-resources-parameters.png)

Na página **Parâmetros de recursos humanos**, as configurações são divididas entre seis guias:

- **Geral**
- **Recrutamento** (esta guia não está incluída no Dynamics 365 Human Resources)
- **Remuneração**
- **Sequências numéricas**
- **FMLA**
- **Autoatendimento para funcionários**
- **Autoatendimento para gerentes**
- **Gerenciamento de benefícios**
- **Licença e ausência**
- **Formas de pagamento**

Cada guia contém informações que pertencem a uma única empresa.

## <a name="general"></a>Geral

As configurações na guia **Geral** definem a aparência das informações sobre ausência, lesões e doenças, e novas contratações. As configurações nessa guia também definem algumas entradas padrão que aparecem enquanto você trabalha. Especificamente, esta guia permite:

- Selecione a cor a ser aplicada a transações de ausência abertas.
- Especificar a folha de estilos a ser usada para relatórios.
- Habilitar a integração entre os cursos de treinamento e o registro de ausência.
- Selecione o código de ausência usado para controlar essa integração.
- Indique por quanto tempo manter incidentes de caso de ferimentos e doenças.
- Especifique o número de identificação padrão mostrado quando um novo trabalhador é contratado.
- Especifique a data usada para calcular anos de serviço. 

![Guia Geral.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>Recrutamento

As configurações na guia **Recrutamento** definem os tipos de documento usados para correspondência enviados automaticamente aos candidatos. Você também pode indicar o projeto de recrutamento usado para solicitações de emprego não solicitadas.

O período definido para o vencimento do projeto de recrutamento determina os projetos de recrutamento incluídos no bloco **Projetos de vencimento** no espaço de trabalho **Gerenciamento de recrutamento**. O período definido para o aviso de prazo da solicitação de emprego é usado para exibir projetos de recrutamento que estão se aproximando do prazo final para solicitação de emprego no bloco **Prazo final para solicitação de emprego se aproximando** no espaço de trabalho **Recrutamento**.

Para obter mais informações sobre recrutamento, consulte [Recrutar candidatos ao trabalho](hr-personnel-recruit.md).

## <a name="compensation"></a>Remuneração

No Dynamics 365 Finance, as configurações na guia **Remuneração** definem se os usuários devem confirmar que desejam salvar informações para um plano de remuneração fixo ou variável. Se você selecionar **Permitir salvar validação**, quando os usuários fecharem uma página relacionada à remuneração, eles receberão uma mensagem que pergunta se eles desejam salvar o registro. Algumas páginas no Gerenciamento de remuneração não permitem que usuários excluam informações. Ao solicitar que os usuários verifiquem se desejam salvar informações, é possível limitar a quantidade de informações que serão salvas, mas não poderão ser excluídas posteriormente. Se você desmarcar **Permitir salvar validação**, os registros serão salvos imediatamente, possivelmente antes que o usuário esteja pronto. Se você estiver usando o Gerenciamento de desempenho, a guia **Remuneração** também permitirá que você selecione um modelo de avaliação a ser usado em vez do modelo atribuído aos planos de remuneração ao avaliar o desempenho.

No Human Resources, você pode usar a guia **Remuneração** para optar por restringir o acesso aos planos de remuneração e definir uma moeda padrão.

Para obter mais informações sobre remuneração, consulte [Visão geral de planos de remuneração](hr-compensation-overview.md).

![Guia Remuneração.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>Sequências numéricas

As configurações na guia **Sequência numérica** determinam as sequências usadas para atribuir IDs automaticamente a itens no Human Resources, como:

- Solicitações de emprego
- Registros de Ausência
- Resultados do processo de remuneração
- Números de caso
- Cursos
- Agendas do curso

Para manter referências e códigos de sequência numérica, use a página de lista **Sequências numéricas** (selecione **Administração organizacional > Sequências numéricas > Sequências numéricas**).

Para obter mais informações, consulte [Visão geral de sequências numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

> [!NOTE]
> O número de horas que será trabalhado não pode exceder 1.250 e o tempo de emprego não pode exceder 12 meses. Esses valores máximos estão de acordo com a legislação federal dos Estados Unidos.

![Guia Sequências numéricas.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

Na guia FMLA, defina requisitos de direito FMLA e horas de direito FMLA. Para obter mais informações, consulte [Configurar parâmetros de licença e ausência](hr-leave-and-absence-parameters.md).

![Guia FMLA.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Autoatendimento para funcionários

As configurações na guia **Autoatendimento para funcionários** afetam como o Autoatendimento para funcionários aparece para funcionários. Nesta guia, você pode:

- Inserir um nome para o espaço de trabalho de Autoatendimento para funcionários
- Selecionar as informações que um gerente pode inserir para funcionários
- Adicionar links úteis para funcionários
- Restringir a adição ou edição de detalhes de contato comercial por funcionários. Para obter mais informações, consulte [Restringir a edição de informações pessoais](hr-employee-self-service-restrict-editing.md).

Para obter mais informações sobre como configurar o Autoatendimento para funcionários, consulte [Visão geral de autoatendimento para funcionários e gerentes](hr-employee-manager-self-service-overview.md).

![Guia Autoatendimento para funcionários.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Autoatendimento para gerentes

As configurações na guia **Autoatendimento para gerentes** afetam o que gerentes visualizam em Autoatendimento para gerentes. Nessa guia, você pode configurar as seguintes opções:

- O intervalo de registros em vencimento
- Os gerentes de informações podem ver em registros em vencimento
- Se os gerentes podem exibir posições abertas para relatórios estendidos
- Exibições de trabalhadores saindo da empresa
- Links úteis para gerentes

Para obter mais informações sobre como configurar o Autoatendimento para gerentes, consulte [Visão geral de autoatendimento para funcionários e gerentes](hr-employee-manager-self-service-overview.md).

![Guia Autoatendimento para gerentes.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>Gerenciamento de benefícios

Na guia Gerenciamento de benefícios, você pode configurar opções de email para o Gerenciamento de benefícios. Para obter mais informações sobre como configurar e usar o Gerenciamento de benefícios, consulte [Visão geral do Gerenciamento de benefícios](hr-benefits-management-overview.md).

![Guia Gerenciamento de benefícios.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>Licença e ausência

Para obter informações sobre como configurar e usar licenças e ausências, consulte [Visão geral de licença e ausência](hr-leave-and-absence-overview.md).

## <a name="payment-methods"></a>Formas de pagamento

Na guia **Métodos de pagamento**, você pode selecionar os métodos de pagamento com suporte da sua organização. Para obter mais informações sobre como configurar a remuneração, consulte [Visão geral de planos de remuneração](hr-compensation-overview.md).

![Guia Métodos de pagamento.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
