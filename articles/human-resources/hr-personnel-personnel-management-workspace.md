---
title: Espaço de trabalho de gerenciamento de pessoal
description: Este tópico descreve os elementos conceituais do Espaço de trabalho de gerenciamento de pessoal.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a83dea308e3e2eec1edebd5d619f9455e1a2268
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066566"
---
# <a name="personnel-management-workspace"></a>Espaço de trabalho de gerenciamento de pessoal


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

O espaço de trabalho **Gerenciamento de pessoal** inclui uma grande quantidade de conteúdo. Ele contém movimentos de pessoa e controla as alterações de funcionários, as posições em aberto, as alterações de endereço, os registros de vencimento e as análises, além de fornecer links para informações específicas. Este tópico fornece informações detalhadas sobre cada parte do espaço de trabalho.

## <a name="activity-tab"></a>Guia Atividade

A guia **Atividade** contém seções que agrupam trabalhadores com base na fase do processo de emprego:

- **Candidatos a contratar**
- **Inicia em breve**
- **Contratações recentes**
- **Saindo**
- **Demitido**

Quando um trabalhador estiver em um desses estágios, ações específicas ficarão disponíveis na forma de um botão no cartão ou no menu exibido quando você selecionar as reticências (**...**) no canto superior direito. As subseções a seguir descrevem as seções da guia **Atividade** e listam as ações disponíveis.

### <a name="candidates-to-hire"></a>Candidatos a contratar

A seção **Candidatos a contratar** do espaço de trabalho é preenchida em várias fontes:

- Uma entidade de Protocolo Open Data (OData)
- Integração com o LinkedIn
- Os dados inseridos manualmente no produto

Quando os candidatos aparecerem na seção **Candidatos a contratar**, você poderá executar as seguintes ações selecionando as reticências no cartão do candidato:

- **Ignorar o candidato**
- **Não contratar**
- **Contratar**

> [!NOTE]
> Se a lista de candidatos estiver sendo preenchida com base no Microsoft Dataverse, os mesmos candidatos serão exibidos em todas as entidades legais porque uma entidade legal não foi associada ao candidato.

### <a name="starting-soon"></a>Inicia em breve

A seção **Começará em breve** lista os trabalhadores que têm uma data de início no futuro. A lista é classificada por data de início. A data de início mais próxima da data de hoje é listada primeiro.

Se o gerente não aparecer no cartão, significa que uma posição não foi atribuída ao trabalhador.

> [!NOTE] 
> É recomendável atribuir uma posição a um trabalhador antes de aplicar uma lista de verificação. Às vezes, as tarefas de integração são atribuídas a um gerente de funcionário contratado recentemente. No entanto, se nenhuma posição for atribuída, o gerente do novo funcionário não poderá ser determinado. Nesse caso, as tarefas de integração destinadas ao gerente serão atribuídas ao proprietário da lista de verificação.

Quando os trabalhadores aparecerem na seção **Começará em breve**, as seguintes ações ficarão disponíveis para elas:

- Atribuir posição
- Verificar emprego
- Atribuir remuneração fixa
- Atribuir remuneração variável
- Exibir em Hierarquia
- Aplicar lista de verificação\*\*

\*\* Essa ação é a ação padrão. Ela aparece como um botão no cartão.

### <a name="recent-hires"></a>Contratações recentes

A seção **Contratações recentes** lista os trabalhadores que têm uma data de início no passado. A lista é classificada por data de início. A data de início mais próxima da data de hoje é listada primeiro.

Por padrão, a lista mostra os trabalhadores que foram contratados nos últimos sete dias. Para alterar essa configuração, na página **Parâmetros de recursos humanos**, na guia **Geral**, defina um período para **Contratações recentes**. Os dados na seção **Contratações recentes** podem ser mostrados para um número específico de dias, meses ou anos. Por exemplo, para exibir a lista de trabalhadores contratados nos últimos 14 dias, defina o campo **Período** como **14** e o campo **Unidade** como **Dias**.

> [!NOTE]
> As configurações da página **Parâmetros de Recursos Humanos** são específicas a cada empresa. Portanto, o período pelo qual você exibe contratações recentes pode variar conforme a empresa. Por exemplo, na empresa USMF, pode ser interessante exibir todas novas contratações dos últimos sete dias. No entanto, na empresa USSI, pode ser interessante exibir todas novas contratações dos últimos 14 dias. Nesse caso, abra a página **Parâmetros de recursos humanos** em cada empresa e defina os parâmetros, conforme necessário.

Se o gerente não aparecer no cartão, significa que uma posição não foi atribuída ao trabalhador.

Quando os trabalhadores aparecerem na seção **Contratações recentes**, as seguintes ações ficarão disponíveis para elas:

- Atribuir posição
- Verificar emprego
- Remuneração fixa
- Atribuir remuneração variável
- Exibir em hierarquia
- Aplicar lista de verificação\*\*

\*\* Essa ação é a ação padrão. Ela aparece como um botão no cartão.

### <a name="exiting"></a>Saindo

A seção **Desligamento** lista os trabalhadores que têm uma data de término no futuro. A lista é classificada por data de desligamento. A data de desligamento mais próxima da data de hoje é listada primeiro. 

Por padrão, a lista mostra os trabalhadores que têm uma data de desligamento nos próximos sete dias. Para alterar essa configuração, na página **Parâmetros de Recursos Humanos**, na guia **Geral**, defina um período para **Exibir trabalhadores que serão desligados**. Os dados na seção **Desligamento** podem ser mostrados para um número específico de dias, meses ou anos. Por exemplo, para exibir a lista de trabalhadores que serão desligados nos próximo 14 dias, defina o campo **Período** como **14** e o campo **Unidade** como **Dias**.

Quando os trabalhadores aparecerem na seção **Desligamento**, as seguintes ações ficarão disponíveis para elas:

- Aplicar lista de verificação\*\*
- Verificar emprego
- Exibir em Hierarquia

\*\* Essa ação é a ação padrão. Ela aparece como um botão no cartão.

### <a name="exited"></a>Demitido

A seção **Desligados** lista os trabalhadores que têm uma data de desligamento no passado. A lista é classificada por data de desligamento. A data de desligamento mais próxima da data de hoje é listada primeiro.

Por padrão, a lista mostra os trabalhadores que têm uma data de desligamento nos últimos sete dias. Para alterar essa configuração, na página **Parâmetros de Recursos Humanos**, na guia **Geral**, defina um período para **Exibir trabalhadores que foram desligados**. Os dados na seção **Desligados** podem ser mostrados para um número específico de dias, meses ou anos. Por exemplo, para exibir a lista de trabalhadores desligados nos últimos 14 dias, defina o campo **Período** como **14** e o campo **Unidade** como **Dias**.

Quando o trabalhador aparecer na seção **Desligados**, as seguintes ações ficarão disponíveis para elas:

- Aplicar lista de verificação\*\*
- Verificar emprego
- Exibir em hierarquia

\*\* Essa ação é a ação padrão. Ela aparece como um botão no cartão.

## <a name="employee-changes-tab"></a>Guia Alterações do funcionário

A guia **Alterações do funcionário** fornece uma lista de todas as ações de funcionário. Essa lista não está disponível por padrão. Para habilitar a funcionalidade, na página **Parâmetros de recursos humanos compartilhados**, na guia **Ações de pessoal**, defina a opção **Habilitar ações de trabalhadores** como **Sim**.

## <a name="position-changes-tab"></a>Guia Alterações de vaga

A guia **Alterações de vaga** fornece uma lista de todas as ações de vaga. Essa lista não está disponível por padrão. Para habilitar a funcionalidade, na página **Parâmetros de recursos humanos compartilhados**, na guia **Ações de pessoal**, defina a opção **Habilitar ações de vaga** como **Sim**.

## <a name="open-positions-tab"></a>Guia Vagas

A guia **Vagas** lista todas as vagas disponíveis. Para que a vaga apareça na lista, a data de ativação da vaga deve ser a de hoje ou anterior, e a vaga não pode ter atribuição de trabalho atual.

> [!NOTE]
> A lista considera a atribuição de trabalhador a partir de hoje. Qualquer vaga que tenha uma atribuição de trabalhador com data futura continuará aparecendo na lista. No entanto, depois que a data efetiva da atribuição do trabalhador for atingida, a vaga será removida da lista.

## <a name="expiring-records-tab"></a>Guia Registros que estão vencendo

A guia **Registros que estão vencendo** lista todos os itens vencidos ou que estão vencendo para os trabalhadores na empresa à qual o usuário está conectado. Os seguintes itens aparecem na lista:

- **Certificados**
- **Identificação**
- **Períodos de experiência**
- **Triagens**
- **Testes**

Para especificar se a lista deve mostrar registros vencidos ou que estão vencendo, na página **Parâmetros de recursos humanos**, na guia **Geral**, defina um período para os **Registros que estão vencendo** ou **Registros vencidos**. Os dados na guia **Registros que estão vencendo** podem ser mostrados para um número específico de dias. Por exemplo, para exibir a lista de registros que vão expirar nos próximos 14 dias, defina o campo **Número de dias** como **14**.

> [!NOTE] 
> Se você definir o intervalo de tempo como **Registros vencidos** ou **Registros que estão vencendo** como **0** na página **Parâmetros de recursos humanos**, a lista não mostrará nenhum desses registros.

## <a name="employees-tile"></a>Bloco Funcionários

O bloco **Funcionário** fornece uma contagem de todos os funcionários empregados na empresa à qual o usuário está conectado no momento. Quando você seleciona o bloco **Funcionários**, uma nova página mostra os detalhes dos funcionários.

## <a name="contractors-tile"></a>Bloco Prestadores de serviço

O bloco **Prestadores de serviços** fornece uma contagem de todos os prestadores de serviços empregados na empresa à qual o usuário está conectado no momento. Quando você seleciona o bloco **Prestadores de serviços**, uma nova página mostra os detalhes dos prestadores de serviços.

## <a name="open-positions-tile"></a>Bloco Vagas

O bloco **Vagas** fornece uma contagem de todas as vagas abertas. Quando você seleciona o bloco **Vagas**, uma nova página mostra os detalhes das vagas. Para que a vaga seja incluída na contagem, a data de ativação da vaga deve ser a de hoje ou anterior, e a vaga não pode ter atribuição de trabalho atual.

> [!NOTE]
> O bloco considera a atribuição de trabalhador a partir de hoje. cQualquer vaga que tenha uma atribuição de trabalhador com data futura continuará sendo incluída na contagem. No entanto, depois que a data efetiva da atribuição do trabalhador for atingida, a vaga será excluída da contagem.

## <a name="approvals-tile"></a>Bloco Aprovações

O bloco **Aprovações** fornece uma contagem de todos os itens de fluxo de trabalho pendentes da aprovação do usuário atual. Quando você seleciona o bloco **Aprovações**, uma nova página mostra os detalhes dos itens do fluxo de trabalho que requerem sua aprovação.

## <a name="address-changes-tile"></a>Bloco Alterações de endereço

O bloco **Alterações de endereço** fornece uma contagem de todas as alterações de endereço que ocorreram durante o número de dias especificado na página **Parâmetros de Recursos Humanos**. Quando você seleciona o bloco **Alterações de endereço**, uma nova página exibe os detalhes das alterações de endereço. No canto direito superior da página, você pode selecionar **Incluir alterações de endereço futuro** para exibir alterações de endereço com uma data futura.

Para obter mais informações sobre como exibir e gerenciar alterações de endereço, consulte [Exibir e gerenciar alterações de endereço](hr-personnel-view-address-changes.md).
