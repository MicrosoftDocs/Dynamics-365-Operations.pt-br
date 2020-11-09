---
title: Preparar-se para a ativação do Human Resources
description: Esta página fornece diretrizes sobre como se preparar para a ativação do Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 59d7274c3b40e78209d90960c4514321b736876a
ms.sourcegitcommit: d66fd72342931fad25a696b251c05781280d36c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "4011401"
---
# <a name="prepare-for-human-resources-go-live"></a>Preparar-se para a ativação do Human Resources

[!include [banner](../includes/banner.md)]

Este tópico descreve como preparar-se para a ativação de um projeto do Dynamics 365 Human Resources usando o Microsoft Dynamics Lifecycle Services (LCS). 

Este gráfico mostra as fases do processo de ativação. 

![Processo de ativação](./media/hr-admin-go-live-prepare-process.png)

A tabela a seguir lista todas as etapas do processo, a duração esperada e quem é responsável pela ação.

| Fase | Ação | Duração/Quando | Quem | Observação |
| --- | --- | --- | --- |--- |
| 1 | Atualizar data de ativação no LCS | No máximo, 2 a 3 meses de antecedência | Parceiro/Cliente | As datas de marco devem ser continuamente atualizadas. |
| 2 | Concluir e enviar lista de verificação | Após a conclusão do teste de aceitação do usuário (UAT) | Parceiro/Cliente | Siga as instruções fornecidas no [FastTrack de avaliação de ativação](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Avaliação do projeto (FastTrack) | Arquiteto FastTrack* | O arquiteto faz a avaliação depois que a lista de verificação é recebida e continua a revisão até que as perguntas sejam esclarecidas e as mitigações estejam em vigor, se aplicável. |
| 4 | Workshop de projetos (FastTrack) | Arquiteto FastTrack* | |
| 5 | Importações de pacotes de dados | Depende do projeto | Parceiro/Cliente | Siga as instruções em [Visão geral de gerenciamento de dados](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).|
| 6 | Pronto para produção | Depois que todas as etapas anteriores tiverem sido concluídas | Parceiro/Cliente | O Parceiro/Cliente pode assumir o controle do ambiente de produção.|
| 7 | Atividades de substituição | Depende do projeto | Parceiro/Cliente | |
| 8 | Ativação | Depende do projeto | Cliente | |

> [!IMPORTANT]
> *As etapas 3 e 4 são preenchidas somente para os clientes qualificados para o FastTrack.

## <a name="completing-the-lcs-methodology"></a>Conclusão da metodologia do LCS

Um importante marco em cada projeto de implementação é a transferência para o ambiente de produção. 

Para ajudar a garantir que o ambiente de produção seja usado para operações de ativação, a Microsoft provisiona a instância de produção somente quando a implementação está se aproximando da fase **Operar** , depois que as atividades necessárias da metodologia do LCS são concluídas. Para obter mais informações sobre os ambientes na sua assinatura, consulte o  [Guia de Licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). 

Os clientes deverão concluir as fases **Análise** , **Projetar e Desenvolver** e **Testar** na metodologia do LCS antes que o botão  **Configurar** para solicitar o ambiente de produção fique disponível. Para concluir uma fase no LCS, primeiro você deverá concluir todas as etapas necessárias nessa fase. Quando todas as etapas de uma fase forem concluídas, você poderá concluir a fase inteira. Você sempre poderá reabrir uma fase posteriormente se precisar fazer alterações. Para obter mais informações, consulte  [Lifecycle Services (LCS) para clientes de aplicativos do Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs). 

O processo de conclusão de uma etapa tem duas partes: 

- Faça o trabalho real, como uma análise de lacuna-ajuste ou o teste de aceitação do usuário (UAT). 
- Marque a etapa correspondente na metodologia do LCS como concluída. 

É uma boa prática concluir as etapas da metodologia à medida que você progride com a implementação. Não espere até o último minuto. Não clique simplesmente em todas as etapas para poder obter um ambiente de produção. É o melhor interesse do cliente ter uma implementação sólida. 

## <a name="uat-for-your-solution"></a>UAT para a sua solução

Durante a fase de UAT, você deve testar todos os processos de negócios que implementou e todas as personalizações feitas em um ambiente de Área Restrita no projeto de implementação. Para ajudar a garantir uma ativação bem-sucedida, você deverá considerar o seguinte ao concluir a fase de UAT: 

- Se os casos de teste cobrem todo o escopo de requisitos. 
- Teste usando dados migrados. Esses dados devem incluir dados mestre, como trabalhadores, trabalhos e posições. Além disso, inclua saldos iniciais, como acúmulos de licenças e ausências. Por fim, inclua transações abertas, como registros em benefícios atuais. Conclua os testes com todos os tipos de dados, mesmo que o conjunto de dados não esteja finalizado. 
- Teste usando as funções de segurança corretas (funções padrão e funções personalizadas) atribuídas aos usuários. 
- Verifique se a solução está em conformidade com qualquer requisito normativo específico da empresa e do setor. 
- Documente todos os recursos e obtenha a aprovação do cliente. 

## <a name="fasttrack-go-live-assessment"></a>Avaliação de ativação do FastTrack

Os clientes qualificados para FastTrack e que estejam envolvidos com um Arquiteto de Soluções FastTrack concluirão uma revisão de ativação com o Microsoft FastTrack. Para obter mais informações, consulte [Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). 

Cerca de oito semanas antes da ativação, a equipe FastTrack pedirá que você preencha uma [Lista de verificação de ativação](https://go.microsoft.com/fwlink/?linkid=2146013).

O gerente de projeto ou um membro de projeto chave deve preencher a lista de verificação de ativação durante a fase de pré-ativação do projeto. Normalmente, a lista de verificação é concluída de quatro a seis semanas antes da data de ativação proposta, quando o UAT é concluído ou está quase concluído. 

Depois de concluir a lista de verificação de ativação, envie-a por email ao Arquiteto de Soluções FastTrack. Inclua sempre um dos principais stakeholders do cliente e do parceiro de implementação no email. 

Depois de enviar a lista de verificação, o Arquiteto de Soluções FastTrack analisará o projeto e fornecerá uma avaliação que descreve os riscos potenciais, as práticas recomendadas e as recomendações para uma ativação bem-sucedida do projeto. Em alguns casos, o arquiteto de soluções poderá realçar os fatores de risco e pedir um plano de mitigação. 

## <a name="see-also"></a>Consulte também

[​Perguntas frequentes sobre ativação​](hr-admin-go-live-faq.md)