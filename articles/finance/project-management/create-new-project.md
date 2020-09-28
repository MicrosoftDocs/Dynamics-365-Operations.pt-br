---
title: Criar um novo projeto
description: Este tópico fornece informações sobre como criar um novo projeto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760473"
---
# <a name="create-a-new-project"></a>Criar um novo projeto

[!include [banner](../includes/banner.md)]

Conclua as etapas a seguir para criar um novo projeto.

1. Na página **Gerenciamento de projetos** , selecione **Novo projeto**, e insira os seguintes valores:

    - **Tipo de projeto:** Tempo e material
    - **Nome do projeto:** Fase de atualização 2 de XYZ
    - **Grupo de projetos:** TM\_WIP
    - **ID do contrato do projeto:** 00000002

2. Selecione **Criar projeto**.

## <a name="assign-a-resource-to-a-project"></a>Atribuir um recurso a um projeto

1. Na página **Trabalhadores**, na lista **Trabalhadores**, selecione o registro para o trabalhador para o qual você configurou competências anteriormente e abra o registro do trabalhador.
2. No Painel de Ação, na guia **Projeto**, no grupo **Configuração**, selecione **Atribuir projetos**.
3. Na página **Atribuições de projetos de validação de recursos**, na guia **Projetos**, no campo **Adicionar o projeto aos projetos selecionados**, filtre o projeto **Fase de atualização 2 de XYZ**.
4. No painel **Projetos restantes**, selecione um projeto e selecione o botão de seta para adicioná-lo ao painel **Projetos selecionados**.

Você também pode atribuir categorias para um recurso, conforme necessário. O tipo de categoria é **Custo** ou **Receita**. O tipo de categoria é determinado pela sua organização. Se não houver categorias atribuídas a um recurso, o Finance pesquisará a categoria padrão em preços por hora para custo e receita.

## <a name="set-up-project-resource-and-role-characteristics"></a>Configurar as características de recurso de projeto e de função

Um gerente de projeto pode usar a funcionalidade de recursos do projeto para criar as funções necessárias para um projeto. As funções podem ser usadas se os recursos confirmados ainda forem desconhecidos quando forem reservados. As funções podem ser reservadas temporariamente como recursos planejados, de forma que você possa prosseguir com os estágios de planejamento do projeto.

[![Exemplo de uma função](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Cenário:** Exemplo de função Cenário: a Contoso foi contratado para concluir um projeto por Tempo e material com um estatuto de projeto aprovado. O gerente de projeto júnior ainda está concluindo o escopo do projeto. O gerente de recurso está identificando atualmente recursos específicos que serão reservados ao trabalho no novo projeto. Uma das funções solicitadas pelo patrocinador do projeto, por causa da natureza crítica do projeto, é de gerente de projeto sênior. O gerente de recurso deve adquirir o novo recurso e definir a função no sistema, caso o gerente de projeto júnior exija informações as informações do recurso durante o planejamento do projeto.

As etapas a seguir mostram como o gerente de recurso pode configurar a função de gerente de projeto sênior e associar características de recurso a ela. Posteriormente, a função poderá ser usada para procurar os recursos disponíveis que correspondam às competências necessários de recurso.

1. Na página **Funções de configuração** , selecione **Novo**, e insira os seguintes valores:

    - **ID da Função:** Gerente de projeto sênior
    - **Descrição:** Gerente de projeto sênior

2. Selecione **Criar**.
3. Selecione a função **Gerente de projeto sênior** e depois selecione **Configurar características**.
4. No campo **Tipo de característica**, selecione **Habilidade**.
5. No campo **Características disponíveis**, insira a habilidade que você está procurando.
6. No campo **Tipo de característica**, selecione **Certificado**.
7. No campo **Características disponíveis**, insira o tipo de certificado que você está procurando.

## <a name="assign-a-project-resource-to-a-project"></a>Atribuir um recurso de projeto a um projeto

1. Na página **Todos os projetos** , selecione o projeto **Fase de atualização 2 de XYZ** .
2. Na guia **Equipe do projeto e agendamento**, selecione **Adicionar**.
3. No campo **Função**, selecione **Membro da equipe**.
4. Selecione **Reservar do calendário**.
5. Na página **Disponibilidade de recursos**, selecione **Configurações de exibição**.
6. Na página **Ajustar configurações de exibição**, insira os seguintes valores:

    - **Formato da exibição do intervalo de datas:** Dia
    - **Exibir descrições de disponibilidade:** Sim
    - **Exibir capacidade restante:** Sim

7. Na lista de recursos, selecione um recurso.
8. Selecione **Reserva fixa** e **Capacidade total**.

## <a name="assign-a-resource-to-a-default-role"></a>Atribuir um recurso a uma função padrão

Para ajudar os gerentes de projeto ou de recurso, você pode fazer uma busca detalhada nos recursos que podem ser reservados a um projeto. Você pode associar uma função padrão a um recurso existente ou a um recurso adquirido mais recentemente. Por exemplo, quando Daniel foi contratado, ele tinha a experiência e as habilidades para preencher a função de Analista comercial. O gerente de recurso atribuiu essa função como a função padrão de Daniel. Assim, o gerente de recurso adicionou Daniel a um grupo de analistas comerciais que estão disponíveis para trabalhar nos projetos.

Durante a reserva de recursos, os gerentes de projeto podem filtrar os recursos de função disponíveis para trabalhar em projetos. Eles podem usar essas informações como um critério ao executarem análises de decisão de vários critérios durante o preenchimento de recursos. Também podem adicionar outras características do recurso ao filtro para pesquisar recursos que tenha habilidades, formação educacional e experiência específicas para um determinado projeto.

**Cenário:** Um projeto aprovado foi iniciado, e a função de Gerente de projeto sênior foi reservada como um recurso planejado durante o estágio de planejamento do projeto. O gerente de recurso adquiriu um recurso para preencher a função Gerente de projeto sênior.

1. Na página **Lista de recursos**, selecione **Daniel Goldschmidt**.
2. Na página **Função do recurso**, selecione **Novo** e informe os seguintes valores:

    - **Efetivo:** Informe a data atual.
    - **Expiração:** Informe **Nunca**.
    - **Função:** Informe **Gerente de projeto sênior**.

3. Selecione **Salvar** e feche a página.
4. Na guia **Competências**, adicione a habilidade **ProjectMgmt** e o certificado **PMP**.
