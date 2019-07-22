---
title: Relatórios de despesas reformulados
description: Este tópico fornece informações sobre a experiência reprojetada e reformulada da entrada do relatório de despesas no Microsoft Dynamics 365 for Finance and Operations. A nova experiência simplifica o processo de preenchimento de relatórios de despesas e diminui o tempo necessário.
author: ryansandness
manager: AnnBe
ms.date: 06/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 9e87a61bd6dd7bc1c7ef569882daf2074c7cade9
ms.sourcegitcommit: 672c94704e9a2b0ec7ee3c111d4ceb1bb8597969
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2019
ms.locfileid: "1631946"
---
# <a name="expense-reports-reimagined"></a>Relatórios de despesas reformulados

[!include[banner](../includes/banner.md)]

A entrada do relatório de despesas foi reprojetada para simplificar o processo de preenchimento de relatórios de despesas e diminuir o tempo necessário. Veja os principais componentes da nova experiência com despesas:

- Um novo espaço de trabalho de gerenciamento de despesas que permite acessar as despesas do seu delegado.
- Uma nova experiência de correspondência de entrada para mostrar melhor os recebimentos no nível de cabeçalho e simplificar o processo de anexação de recebimentos a linhas de despesa.
- Uma nova grade somente leitura que permite exibir muito mais linhas de despesas e colunas adicionais de dados. Agora você pode ver todas as linhas discriminadas e divididas, juntamente com as despesas do pai.
- Um painel simplificado para editar despesas.
- Mensagens de erro, aviso e políticas reprojetadas para ajudar a garantir que você tenha o contexto correto para entender qual é o problema e como resolvê-lo. A Microsoft removeu muitas mensagens que apareceram antes que os usuários tivessem uma oportunidade de concluir suas tarefas e resolver os problemas, como a mensagem de discriminação incompleta.
- Uma nova página para especificar quais campos são requeridos por sua organização, quais campos são opcionais e quais campos não devem ser capturados. Esta página ajudará a reduzir o número de campos que os usuários devem definir.
- Uma nova aparência para relatórios de despesas, para que os relatórios não pareçam mais como se fossem projetados para pessoas de contabilidade.

Para ativar a nova experiência, use o espaço de trabalho **Gerenciamento de recursos** para ativar o recurso **Relatórios de despesas reformulados**. Quando você ativa esse recurso, as seguintes ações ocorrem:

- O espaço de trabalho de despesas existente é substituído pelo novo espaço de trabalho.
- Um novo item de menu para visibilidade do campo de despesa é adicionado.
- Nenhum item de menu existente para os relatórios de despesas (a página existente) ou os campos do relatório de despesas são removidos.
- Fluxos de trabalho e quaisquer aprovações ainda o levam para a página de relatórios de despesas existente.

## <a name="getting-started-video-for-new-users"></a>Vídeo de introdução para novos usuários

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2Y7gO]

O vídeo [Experiência com despesas no Dynamics 365 for Finance and Operations](https://youtu.be/Ocy-MsTvEE0) (mostrado acima) é incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

## <a name="new-features"></a>Novos recursos

| Recurso novo | Descrição |
|---|----|
| Visibilidade do campo de despesas | Uma nova página de configuração permite especificar quais campos devem ser desabilitados para uma organização, quais campos devem ser necessários e quais campos são recomendados. |
| Os campos obrigatórios | A nova configuração simples permite que você faça alguns campos necessários sem precisar usar a estrutura de políticas. |
| Campos opcionais | Uma segunda página para campos opcionais é adicionada. Assim, os funcionários não se sentirão como se tivessem que definir os campos, mas os campos ainda são facilmente acessíveis. |
| Adicionar recibos não anexados | A capacidade de adicionar recibos não anexados ao relatório de despesas é mais visível a partir do espaço de trabalho e do relatório de despesas. |
| Mensagens aprimoradas | Há melhor visibilidade nas linhas de despesas que possuem avisos ou erros. |
| Redução de mensagens na barra de mensagens| O número de mensagens do Log de Informações foi diminuído e foi feito um esforço para evitar que mensagens duplicadas aparecessem em muitos casos. |
| Ações comuns agrupadas em conjunto | A interface foi limpa com a adição de um novo botão de ações para a maioria das ações comuns de nível de linha e a adição de um botão de reticências (...) para cabeçalho e outras ações menos frequentes. |
| Novo espaço de trabalho para aumentar a visibilidade | Um novo espaço de trabalho unifica recursos e links que permitem aos usuários migrar para áreas diferentes. |
| Adicionar despesas e recibos existentes durante a criação da despesa | Ao criar relatórios de despesas, você pode adicionar todas as despesas e recibos selecionados. |
| Calculadora de taxa de câmbio | Foi adicionada uma calculadora de taxa de câmbio que permite calcular a taxa de câmbio para transações do próprio bolso em várias moedas. |
| Salvar e adicionar novas linhas de despesa | Os botões **Salvar** e **Novo** estão disponíveis quando novas despesas são inseridas, para ajudar a inserir rapidamente as linhas de despesas. |
| Melhor visibilidade em linhas divididas e discriminadas | As linhas discriminadas e divididas são adicionadas diretamente à lista de despesas, para aumentar a visibilidade e ajudar a determinar facilmente se há erros de política ou outros erros. |
| Mostrar recibos durante a discriminação | Recibos podem ser exibidos durante a discriminação. |

A versão inicial é focada em cenários de entrada de despesas. Qualquer revisão de relatório de despesas ou cenário de aprovação continuará a usar a página de entrada de despesas existente.

Os recursos a seguir estão presentes na página existente, mas ainda não estão presentes na nova página. Esses recursos serão reintroduzidos nas próximas versões:

- Aprovações
- Aprovação de contas a pagar e a capacidade de editar a contabilidade
- Vários pontos de entrada
- Integração de requisição de viagem
- Entidade de dados para visibilidade do campo de despesas
- Entrada para despesas diárias
- Fluxo de trabalho do nível da linha
- Suporte para aprovadores provisórios
- Discriminação avançada
