---
title: Controle de cabeçalho do trabalhador
description: Este artigo fornece informações sobre o controle de cabeçalho personalizável no autoatendimento para funcionários, no Hub de pessoas e na página Trabalhador da Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
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
ms.openlocfilehash: 2867a952df79161aaee657dbc3df1f3298294dd5
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445940"
---
# <a name="worker-header-control"></a>Controle de cabeçalho do trabalhador

O Microsoft Dynamics 365 Human Resources fornece informações sobre o controle de cabeçalho personalizável no **Autoatendimento para funcionários**, no hub **Pessoas** e na página **Trabalhador**. O cabeçalho contém informações chave sobre o trabalhador e também ações de um único clique, como email, chamada ou mensagens. O cabeçalho pode ser modificado pela remoção de campos ou adição de campos, incluindo campos personalizados, para mostrar informações adicionais. Para usar o novo controle de cabeçalho, vá para **Gerenciamento de recursos** e habilite o recurso **Controle de cabeçalho do trabalhador**.

## <a name="personalization"></a>Personalização

Uma das vantagens principais do controle de cabeçalho do trabalhador é a capacidade de personalizar as informações que aparecem no cabeçalho.

Na parte superior direita do cabeçalho, há um grupo de três campos que mostram dados diferentes, dependendo do status do funcionário. Esse grupo de campos é conhecido como a parte Destaque do cabeçalho. Você pode personalizar a parte Destaque do cabeçalho removendo os campos atuais ou adicionando campos. Os campos que podem ser adicionados à parte de destaque no controle de cabeçalho diferem entre o **Autoatendimento para funcionário** o hub **Pessoas** e a página **Trabalhador**.

## <a name="employee-self-service"></a>Autoatendimento para funcionários

O cabeçalho do trabalhador na página **Autoatendimento para funcionários** contém as seguintes informações:

- Nome do trabalhador
- Número da equipe
- Cargo
- Departamentos
- Tipo de trabalhador
- Entidade legal do emprego
- Anos de serviço
- Subordinado a (gerente)
- Tipo de posição

O cabeçalho também contém uma ação de clique único para editar as informações pessoais do indivíduo. Selecione **Editar detalhes pessoais** para abrir a página **Informações pessoais** no **Autoatendimento para funcionário**.

## <a name="people-hub"></a>Hub de pessoas

O cabeçalho do trabalhador no hub **Pessoas** (a página **Espaço de trabalho Pessoas**) contém as seguintes informações:

- Nome do trabalhador
- Número da equipe
- Cargo
- Departamentos
- Tipo de trabalhador
- Entidade legal do emprego
- Anos de serviço
- Subordinado a (gerente)
- Tipo de posição

O cabeçalho também contém ações de clique único, como email, chamada ou mensagens. Se um usuário estiver exibindo suas próprias informações na página **Espaço de trabalho Pessoas**, a seção Ação de clique único incluirá o botão **Editar detalhes pessoais**. O usuário pode selecionar este botão para abrir a página **Informações pessoais** no **Autoatendimento para funcionário**.

## <a name="streamlined-worker-page"></a>Página Trabalhador simplificada

O cabeçalho do trabalhador na página **Trabalhador** simplificada contém as seguintes informações:

- Nome do trabalhador
- Número da equipe
- Cargo
- Departamentos
- Tipo de trabalhador
- Entidade legal do emprego

Dependendo do status do funcionário, os dados no cabeçalho podem variar. Por exemplo, se o funcionário saiu da empresa, o controle de cabeçalho contém um emblema **Desligado**, a data de término do emprego e a razão do desligamento.

A tabela a seguir mostra os dados que aparecem no cabeçalho para diferentes status do funcionário.

| Status do funcionário | Dados que são mostrados | Observação |
|-----------------|--------------------|------|
| Pendente | <ul><li>Nome</li><li>Número da equipe</li><li>Cargo</li><li>Departamento</li><li>Tipo de trabalhador</li><li>Entidade legal</li><li>Notificação pendente</li><li>Data inicial</li><li>Subordinado a</li><li>Tipo de posição</li></ul> | |
| Contratação recente | <ul><li>Nome</li><li>Número da equipe</li><li>Cargo</li><li>Departamento</li><li>Tipo de trabalhador</li><li>Entidade legal</li><li>Notificação de contratação recente</li><li>Anos de serviço</li><li>Subordinado a</li><li>Tipo de posição</li></ul> | Por padrão, a notificação **Contratação recente** é exibida para funcionários que foram contratados nos últimos sete dias. Para alterar essa configuração, na página **Parâmetros de recursos humanos**, na guia **Geral**, na seção **Intervalo de datas de contratação recente**, digite um período. Por exemplo, para exibir a notificação **Contratação recente** para funcionários contratados nos últimos 14 dias, defina o campo **Período** como **14** e o campo **Unidade** como **Dias**. |
| Funcionário ativo | <ul><li>Nome</li><li>Número da equipe</li><li>Cargo</li><li>Departamento</li><li>Tipo de trabalhador</li><li>Entidade legal</li><li>Data inicial</li><li>Subordinado a</li><li>Tipo de posição</li></ul> | |
| Saindo | <ul><li>Nome</li><li>Número da equipe</li><li>Cargo</li><li>Departamento</li><li>Tipo de trabalhador</li><li>Entidade legal</li><li>Notificação Desligado</li><li>Anos de serviço</li><li>Subordinado a</li><li>Tipo de posição</li></ul> | Por padrão, a notificação **Desligamento** é mostrada para funcionários que se desligarão nos próximos sete dias. Para alterar essa configuração, na página **Parâmetros de recursos humanos**, na guia **Geral**, na seção **Intervalo de datas de desligamento do funcionário**, digite um período. Por exemplo, para exibir a notificação **Desligamento** para funcionários que se desligarão nos próximos 14 dias, defina o campo **Período** como **14** e o campo **Unidade** como **Dias**. |
| Demitido | <ul><li>Notificação Desligou</li><li>Número da equipe</li><li>Data final do emprego</li><li>Código do motivo</li></ul> | Por padrão, a notificação **Desligou** é mostrada para funcionários que se desligaram nos últimos sete dias. Para alterar essa configuração, na página **Parâmetros de recursos humanos**, na guia **Geral**, na seção **Intervalo de datas de funcionários desligados**, digite um período. Por exemplo, para exibir a notificação **Desligou** para funcionários que se desligaram nos últimos 14 dias, defina o campo **Período** como **14** e o campo **Unidade** como **Dias**. |
