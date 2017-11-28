---
title: "Ações de pessoal [Perguntas frequentes]"
description: "Este tópico contém respostas para as perguntas que você pode ter se a sua organização utilizar ações de pessoal. As ações de pessoal são etapas adicionais que devem ser concluídas quando você executa algumas tarefas relacionadas a pessoal."
author: shielas
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 93004f45189d16e991a3962ef16b4a102caf07bd
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="personnel-actions-faq"></a>Ações de pessoal [Perguntas frequentes]
Este tópico contém respostas para as perguntas que você pode ter se a sua organização utilizar ações de pessoal. As ações de pessoal são etapas adicionais que devem ser concluídas quando você executa algumas tarefas relacionadas a pessoal. Exemplos de tarefas que podem exigir ações de pessoal são quando você cria novas posições, altera valores existentes de posição, contrata novos trabalhadores, transfere trabalhadores, altera a remuneração do trabalhador, altera as atribuições de posição, ou demite trabalhadores.

**Observação:** As ações de pessoal só estão disponíveis se os campos **Habilitar ações do trabalhador** e **Habilitar ações de posição** forem definidos como **Sim**, na guia **Ações de pessoal** na página **Parâmetros compartilhados de recursos humanos**. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>Como posso saber se minha organização requer ações de pessoal?
As ações de pessoal são necessárias pela organização se for solicitado que você selecione uma ação de pessoal ao criar novas posições, alterar posições existentes, contratar novos trabalhadores, transferir trabalhadores, alterar a remuneração do trabalhador, alterar as atribuições de posição, demitir trabalhadores, ou inserir licença para trabalhadores. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>Que é a diferença entre uma ação de posição e uma ação de trabalhador?
Há dois tipos de ações de pessoal:

- Ação da posição – uma ação de posição é executada em posições existentes ou em novas posições. Por exemplo, uma ação de posição pode ser necessária se você alterar o valor em uma posição existente se você criar uma nova posição sazonal. Para obter informações detalhadas sobre como usar ações de posição, consulte Tarefas principais: Posições existentes do trabalhador de tarefas, ou Tarefas principais: Novas posições do trabalhador.

- Ação do trabalhador – uma ação de trabalhador é executada nos funcionários existentes ou nos funcionários novos. Por exemplo, uma ação de trabalhador pode ser necessária quando um novo funcionário é contratado ou quando um funcionário existente é promovido. Para obter informações detalhadas sobre como usar ações do trabalhador, consulte Atribuir ações de pessoal a trabalhadores.

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>O que os status das ações de pessoal significam?
As ações de pessoal podem ter os seguintes status:

- **Rascunho** – se o fluxo de trabalho for usado, a ação não foi enviada. Se o fluxo de trabalho não for usado, a ação não foi concluída.
- **Em revisão** – a ação de pessoal foi enviada ao fluxo de trabalho, mas o fluxo de trabalho não está concluído.
- **Aguardando aprovação** – o fluxo de trabalho está concluído, mas as alterações ainda estão em andamento. Cancelado – o fluxo de trabalho foi cancelado ou a ação de pessoal foi chamada novamente. Rejeitada – a solicitação de ação foi rejeitada pelo aprovador.
- **Processando ação** – a solicitação de ação foi aprovada e as alterações estão sendo processadas.
- **Fluxo de trabalho concluído** – o fluxo de trabalho está concluído e as alterações foram processadas. Falha – o fluxo de trabalho falhou porque as informações estão desatualizadas. Clique em Reativar para exibir as informações mais recentes e para continuar.
- **Concluído** – a posição foi criada ou alterada com êxito, ou o funcionário foi contratado, transferido, demitido ou teve sua remuneração alterada com êxito. Erro – ocorreu um problema diferente do problema causado pelas informações desatualizadas. Abra o Log de mensagens de ações de pessoal para determinar a causa do erro.
- **Negado** – a solicitação de ação foi negada pelo aprovador.

## <a name="can-i-delete-a-personnel-action"></a>Posso excluir uma ação de pessoal?
Sim, você pode excluir as ações de pessoal que têm o status de **Rascunho**, **Erro**, **Falha**, ou **Cancelado**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>Qual é a maneira mais rápida de verificar o status de uma solicitação de ação de pessoal?
Abra algumas páginas de listagem de ação de pessoal e selecione uma ação de pessoal.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>O que devo fazer se uma solicitação de ação de pessoal falhar?
Se uma solicitação de ação de pessoal falhar, siga estas etapas para resolver o erro e para reenviar a solicitação:

> 1. No **Painel de Ação**, clique no botão **Texto de erro** para exibir a mensagem de texto que descreve o problema.

> 2. No **Painel de Ação**, clique em **Reativar** para carregar as informações mais recentes e para definir o status da ação de pessoal de volta para **Rascunho**.

> 3. Resolva o erro, e clique em **Concluído** ou **Enviar**.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>O que acontece com uma ação da pessoal que usa o fluxo de trabalho quando a aprovação final é concluída?
Se não houver um erro, a ação de pessoal se torna somente leitura. (Você pode exibir o histórico na página de lista **Todas as ações do trabalhador**, mas não pode alterar a ação de pessoal.) Quando o status de uma ação de pessoal é **Concluído**, a posição ou o registro do trabalhador já foi atualizado. Para exibir as alterações que foram executadas, abra a página de listagem de **Posições** ou **Trabalhadores**.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>Por que recebo a seguinte mensagem de erro quando incorporo um valor diferente de zero no campo Taxa de pagamento? "O valor está fora do intervalo válido - ele deve estar entre 0,00 e 0,00”
Você recebe esta mensagem porque o campo Nível no formulário Trabalho está em branco para os trabalhos associados à posição selecionada.

Para resolver esse erro, siga estas etapas:

> 1. No formulário de Atribuições da posição do trabalhador, clique no campo de Posição.  
> 2. Clique no valor do campo Trabalho para abrir a página Trabalho.
> 3. No painel de Ação, clique em Editar.
> 4. Clique na guia Remuneração.
> 5. No campo Nível, selecione um nível.
> 6. Feche a página Trabalho.
> 7. Feche a página Posição.
> 8. Retorne à guia Remuneração, na página do Trabalhador, e selecione Remuneração fixa.  Selecione novo e insira a posição do funcionário no campo Posição.  Insira um valor no campo Plano e, em seguida, digite a remuneração do funcionário no campo Taxa de pagamento.

## <a name="why-cant-i-change-the-effective-date-in-the-header-of-the-worker-action-form"></a>Por que não posso alterar a data efetiva no cabeçalho do formulário Ação do trabalhador?
Não é possível alterar a data efetiva porque o campo é preenchido com a data mais lógica para o tipo de ação.

Por exemplo:

- A data de vigência no cabeçalho de uma ação **Demitir um trabalhador** é a data que você inseriu no campo **Data da rescisão**.
- A data de vigência de uma ação **Contratar um trabalhador** é a data que você inseriu no campo **Data de início do funcionário**.
- A data de vigência de uma ação **Transferir um trabalhador** é a data que você inseriu no campo **Data inicial da atribuição** para o trabalhador.


