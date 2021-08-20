---
title: Configurar revisores de despesas
description: Este tópico descreve como usar os revisores de despesas para selecionar dinamicamente o usuário para o qual uma tarefa de fluxo de trabalho, aprovação ou decisão manual é atribuída.
author: rachel-profitt
ms.date: 06/25/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2021-06-24
ms.openlocfilehash: ceb0a60ccf3d1c989d8663e933faaa5e430d314695e20990c9086cd1b8325ff1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773718"
---
# <a name="configure-expenditure-reviewers"></a>Configurar revisores de despesas
[!include[banner](../includes/banner.md)]

É possível configurar revisores de despesas dinâmicos para as encaminhar despesas para revisão com base no usuário atribuído a uma função de projeto ou na dimensão financeira na qual a despesa está sendo cobrada. O processo de fluxo de trabalho usa a função de projeto ou o proprietário da dimensão financeira especificado para determinar para quem a despesa deverá ser encaminhada.

Você poderá definir uma ou mais configurações de revisor de despesas e selecionar uma configuração ao criar um fluxo de trabalho. Você pode configurar valores de revisor de despesas para cada entidade legal em sua organização. Depois de definir as configurações de revisor de despesas, você atribui a configuração à configuração. Os revisores de despesas podem ser atribuídos a tarefas de fluxo de trabalho, aprovações e decisões manuais.

> [!NOTE]
> Embora os revisores de despesas não sejam obrigatórios, eles podem ajudar a simplificar a configuração do seu fluxo de trabalho. Por exemplo, não é necessário criar uma decisão condicional para verificar cada dimensão de centro de custos e depois criar outro elemento para atribuir a aprovação ou a tarefa a um usuário ou grupos de usuários específicos. Em vez disso, você pode configurar o proprietário da dimensão do centro de custos e usar um revisor de despesas para selecionar dinamicamente o usuário correto. Dessa forma, quando a propriedade ou a atribuição de centros de custo mudarem, basta atualizar o campo **Proprietário** da dimensão financeira.

## <a name="types-of-expenditure-reviewers"></a>Tipos de revisores de despesas

Nem todos os fluxos de trabalho oferecem suporte ao conceito de revisores de despesas. Por padrão, você pode configurar os revisores de despesas para requisições de compra, ordens de compra, faturas de fornecedor e relatórios de despesas. Cada um desses tipos de fluxo de trabalho requer que você configure os revisores de despesas em uma página separada que seja específica para o recurso e o módulo. Para cada documento com suporte, os revisores de despesas podem ser usados com fluxos de trabalho de nível de cabeçalho ou de linha.

A tabela a seguir mostra onde você deve ir para configurar um revisor de despesas para cada documento suportado.

| Documento | Painel de navegação |
|----------|-----------------|
| Relatórios de Despesas | Gerenciamento de despesas \> Configuração \> Políticas \> Revisores de despesas |
| Ordens de Compra | Aquisição e fornecimento \> Configuração \> Políticas \> Revisores de despesas de ordens de compra |
| Requisições de compra | Aquisição e fornecimento \> Configuração \> Políticas \> Revisores de despesas de requisições de compra |
| Faturas de fornecedor | Contas a pagar \> Configuração de política \> Revisores de despesas de faturas de fornecedor |

## <a name="expenditure-reviewer-assignments"></a>Atribuições de revisor de despesas

Dois tipos de atribuição estão disponíveis para cada revisor de despesas: *distribuições do projeto* e *distribuições da organização*. Para a distribuição de um projeto, você pode selecionar entre as autoridades de projeto e as dimensões financeiras. Para uma distribuição da organização, você pode selecionar dimensões financeiras.

As autoridades do projeto incluem o gerente do projeto, o controlador do projeto e o gerente de vendas do projeto. Você define essas autoridades diretamente no seu projeto, selecionando um trabalhador nos campos apropriados.

As dimensões financeiras são controladas pelas estruturas de conta em cada entidade legal. Para cada entidade legal, você pode selecionar quais dimensões financeiras serão usadas com o revisor de despesas. As dimensões podem vir do projeto (nesse caso, você seleciona as dimensões na guia **Distribuições do projeto**) ou do documento (neste caso, você seleciona as dimensões na guia **Distribuições da organização**). No campo **Proprietário** da página **Valores de dimensões financeiras**, você pode selecionar o trabalhador para cada dimensão financeira.

## <a name="example-1-expenditure-reviewers-based-on-organization-distributions"></a>Exemplo 1: revisores de despesas com base nas distribuições da organização

Você trabalha para a Contoso Appliances, e sua organização tem seis departamentos e 10 centros de custo. Quando uma nova requisição de compra é enviada, a aprovação deve partir primeiro do gerente do departamento e, em seguida, do Gerenciador de custo do centro de custos.

Para este exemplo, você configura dois *revisores de despesas de requisição de compra*:

- Para o primeiro revisor, nomeie o departamento e selecione a dimensão financeira **Departamento** na guia **Distribuições da organização**. 
- Para o segundo revisor, nomeie o centro de custo e selecione a dimensão financeira **Centro de custo** na guia **Distribuições da organização**.

Ao configurar o fluxo de trabalho, você cria duas etapas de aprovação. A primeira é para o departamento e a segunda é para o centro de custos. Para cada elemento de aprovação, selecione **Participante** no campo **Tipo de atribuição** na guia **Baseada em função**, selecione **Participantes de despesas** no campo **Tipo de participante** e depois selecione o participante apropriado no campo **Participante**.

Quando a requisição de compra é criada, as dimensões financeiras departamento e centro de custo são atribuídas às linhas da requisição de compra. Quando o fluxo de trabalho é enviado, o sistema avalia primeiro o departamento na requisição de compra e atribui o elemento de aprovação ao usuário que é relacionado ao trabalhador selecionado para o departamento. Após concluir a primeira etapa de aprovação, o sistema avalia a segunda etapa de aprovação e atribui o segundo elemento de aprovação ao usuário que é relacionado ao trabalhador selecionado para o centro de custos.

## <a name="example-2-expenditure-reviewers-based-on-project-distributions"></a>Exemplo 2: revisores de despesas com base nas distribuições do projeto

Você trabalha na divisão de serviços da Contoso Appliances. A organização requer que o gerente de projeto de cada ordem de compra aprove a despesa. Além disso, o gerente do centro de custos do projeto deve aprová-la. As aprovações podem ser feitas ao mesmo tempo. De qualquer forma, os dois usuários devem aprovar a ordem de compra para que o fluxo de trabalho possa continuar.

Para este exemplo, crie um *revisor de despesas de ordem de compra* chamado **GP e centro de custos**. Você seleciona a caixa de seleção **Gerente do projeto** e define a opção **Dimensão do centro de custos** como **Sim** na guia **Distribuições do projeto** da página **Revisor de despesas da ordem de compra**. Como parte da configuração, você deve garantir que o campo **Gerente de projeto** seja definido para todos os projetos e que um proprietário seja especificado para todos os centros de custos na página **Valores da dimensão financeira**.

Ao configurar o fluxo de trabalho, você precisa de uma etapa de aprovação. Selecione **Participante** no campo **Tipo de atribuição**. Em seguida, na guia **Baseada em função**, selecione **Participantes da despesa** no campo **Tipo de participante** e selecione o gerente do projeto e o centro de custos no campo **Participante**. Para garantir que o fluxo de trabalho não continue até que o gerente do projeto e o proprietário do centro de custos aprovem o fluxo de trabalho, defina o campo **Política de conclusão** como **Todos os aprovadores**.

Quando a ordem de compra for criada, o campo **Projeto** deverá ser especificado. Se não for necessário um projeto para todas as suas ordens de compra, recomendamos adicionar uma decisão condicional ao seu fluxo de trabalho para verificar um projeto antes que a etapa de aprovação seja executada. O sistema então avalia o projeto especificado para a ordem de compra e atribui o elemento de aprovação ao usuário que é relacionado ao trabalhador no campo **Gerente de projeto**. Além disso, o sistema cria uma tarefa e a atribui ao usuário que é relacionado ao trabalhador selecionado no campo **Proprietário** do centro de custos do projeto. Observe que este exemplo usa o centro de custos do projeto, e não o centro de custos da ordem de compra.

## <a name="set-up-expenditure-reviewers"></a>Configurar revisores de despesas

Este exemplo mostra como você configura um revisor de despesas de requisição de ordem. Para configurar outros tipos de revisores de despesas, substitua o caminho de navegação da etapa 1 pelo caminho apropriado da tabela na seção [Tipos de revisores de despesas](configure-expenditure-reviewers.md#types-of-expenditure-reviewers), anterior a este tópico.

1. Acesse **Aquisição e fornecimento \> Configuração \> Políticas \> Revisores de despesas de requisições de compra**.
2. Na página **Revisores de despesas de requisições de compra**, selecione **Novo**.
3. No campo **Nome**, insira um nome para a configuração do revisor de despesas, como o **centro de custos**.
4. Na guia rápida **Revisores de despesas por entidade legal**, selecione a entidade legal a ser configurada.
5. Para uma distribuição de projeto, marque a caixa de seleção de cada autoridade de projeto e selecione **Sim** para cada dimensão financeira que deseja habilitar. 
6. Para uma distribuição da organização, na guia **Distribuições da organização**, selecione **Sim** para cada dimensão financeira que você deseja habilitar.
7. Repita as etapas 4 a 6 para cada entidade legal adicional.

## <a name="assign-owners-to-financial-dimensions"></a>Atribuir proprietários a dimensões financeiras

Para atribuir um proprietário a uma dimensão financeira, siga estas etapas.

1. Acesse **Contabilidade \> Plano de contas \> Dimensões \> Dimensões financeiras**.
2. Na lista, selecione a dimensão financeira para a qual os proprietários serão atribuídos.
3. Selecione **Valores de dimensão**.
4. Selecione **Editar** para fazer alterações nos valores de dimensão.
5. Na lista, selecione o valor da dimensão para o qual um proprietário será atribuído.
6. No campo **Proprietário**, selecione o trabalhador para a qual o valor da dimensão será atribuído.

## <a name="configure-project-distributions"></a>Configurar distribuições de projetos

Para atribuir autoridades de projeto a um projeto, siga estas etapas.

1. Acesse **Gerenciamento e contabilidade de projeto \> Projetos \> Todos os projetos**.
2. Selecione o projeto para o qual serão atribuídas as autoridades.
3. Selecione **Editar** para fazer alterações no projeto.
4. Na guia rápida **Geral**, na seção **Responsável**, selecione um trabalhador para os campos **Gerente de vendas**, **Gerente do projeto** e **Controlador do projeto**, conforme necessário.
5. Na guia rápida **Dimensões financeiras**, selecione as dimensões financeiras necessárias para o seu projeto.

## <a name="assign-expenditure-reviewers-to-a-workflow-task"></a>Atribuir revisores de despesas a uma tarefa de fluxo de trabalho

Este exemplo mostra como configurar um fluxo de trabalho de requisição de compra para que ele use um revisor de despesas de requisição de compra. Para configurar outros tipos de fluxos de trabalho, a página do fluxo de trabalho que deve ser aberta na etapa 1 pode estar no módulo **Gerenciamento de despesas** ou **Contas a pagar**, e não no **Módulo de compras**.

Para atribuir revisores de despesas de requisição de compra a uma tarefa de fluxo de trabalho, siga estas etapas.

1. Acesse **Compras e fornecimento \> Configuração \> Fluxos de trabalho de compras e fornecimento**.
2. Toque duas vezes (ou clique duas vezes) em um fluxo de trabalho existente ou crie um novo fluxo de trabalho.
3. No editor de fluxo de trabalho, no painel **Fluxo de trabalho**, selecione a tarefa à qual a configuração do revisor de despesas será atribuída. No **Painel de Ações**, no grupo **Exibir**, selecione **Propriedades**.
4. No painel esquerdo da página **Propriedades**, selecione **Atribuição**.
5. Na guia **Tipo de atribuição**, selecione **Participante**.
6. Na guia **Baseada em função**, no campo **Tipo de participante**, selecione **Participantes da despesa**. Em seguida, no campo **Participante**, selecione a configuração de revisor de despesas que você deseja usar para a tarefa de fluxo de trabalho.
