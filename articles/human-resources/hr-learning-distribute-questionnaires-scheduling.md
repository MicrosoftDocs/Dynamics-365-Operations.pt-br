---
title: Distribuir questionários usando agendamento
description: A programação do questionário permite que você planeje e distribua questionários para vários participantes.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 50be7631ec303171640b7fa9e6d283a198bd1a52
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464997"
---
# <a name="distribute-questionnaires-using-scheduling"></a>Distribuir questionários usando agendamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A programação do questionário permite que você planeje e distribua questionários para vários participantes. A empresa de dados demo usada para criar este procedimento é USMF.

## <a name="create-a-questionnaire-schedule"></a>Criar uma agenda de questionário

1. Vá para Questionário > Distribuir > Agendas de questionário.

2. Clique em Novo.

3. No campo Agendamento, digite um valor.

4. No campo Descrição, digite um valor.
    * Defina a agenda para Anônima se as respostas precisarem ser registradas sem nomes associados à resposta.  
    * Permitir resultados anônimos deve estar configurado primeiro nos parâmetros de RH.  

5. No campo Tipo, selecione o tipo de planejamento.  Neste exemplo, usaremos o tipo Satisfação.

6. Na lista, localize e selecione o registro desejado.

7. Na lista, clique no link na linha selecionada.

8. No campo Data, insira uma data.

9. Expanda a seção Email para autoatendimento de funcionários.

10. No campo Assunto, digite um valor.

    * Exemplo: questionário disponível  

11. No campo Texto, digite o corpo da mensagem do seu email. Observe que a variável pode ser usada para substituir valores no sistema.

    * Exemplo: Prezado(a) %P%, faça logon no Autoatendimento para funcionários para concluir o questionário sobre saúde da força de trabalho.  Contoso  

12. Clique em Salvar.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>Use os detalhes de configuração para selecionar os questionários a serem respondidos assim como algumas consultas a serem usadas para selecionar participantes.

1. Clique em Detalhes da configuração.

2. Na lista, selecione uma consulta que será usada para encontrar participantes para o questionário no sistema.

    * Example: trabalhadores  

3. Clique em Exibir ou modificar consulta para selecionar pessoas específicas ou ajustar a consulta para encontrar pessoas que atendem aos critérios específicos.

    * Observe que todos os participantes devem ser usuários do sistema.  

4. Na lista, marque a linha para pessoa.

5. No campo Critérios, insira ou selecione um valor.

    * Selecione Julia Funderburk  

6. Na lista, selecione Julia Funderburk

7. Clique em OK.

8. Clique na guia Questionários.

9. Na árvore, expanda "o nó da pesquisa de satisfação do tipo de questionário".

10. Na árvore, verifique "Avaliação da saúde da força de trabalho".

11. Clique em OK.

12. Clique em Sessão de respostas planejadas.

    * Observe que as sessões de respostas planejadas são criadas para cada usuário selecionado/consultado.  

13. Feche a página.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Inicie a agenda de questionário para disponibilizar o questionário para que os participantes o concluam.

1. Clique em Funções.

2. Clique em Iniciar.

3. Clique em OK.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Envie email para informar os participantes sobre o questionário disponível.

1. Clique em Funções.

2. Clique em Enviar email.

3. Clique em Cancelar.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Use sessões de respostas planejadas para monitorar quem precisa preencher o questionário.

1. Clique em Sessão de respostas planejadas.

    * Excluir todas as sessões de respostas planejadas pendentes quando estiver pronto para encerrar a sessão planejada.  

2. Clique em Excluir.

3. Clique em Sim.

4. Feche a página.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Encerre a agenda quando todos os entrevistados tiverem concluído o questionário e/ou todas as sessões de respostas planejadas restantes tiverem sido excluídas.

1. Clique em Funções.
2. Clique em Finalizar.
3. Clique em OK.



[!INCLUDE[footer-include](../includes/footer-banner.md)]