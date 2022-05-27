---
title: Preparar-se para a ativação do Human Resources
description: Esta página fornece diretrizes sobre como se preparar para a ativação do Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 425dfad542cf19e039f8613c5f7bcaacb4b15930
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688845"
---
# <a name="prepare-for-human-resources-go-live"></a>Preparar-se para a ativação do Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../includes/peap-2.md)]

Este tópico descreve como preparar-se para a ativação de um projeto do Dynamics 365 Human Resources usando o Microsoft Dynamics Lifecycle Services (LCS). 

Este gráfico mostra as fases do processo de ativação. 

![Processo de ativação.](./media/hr-admin-go-live-prepare-process.png)

A tabela a seguir lista todas as etapas do processo, a duração esperada e quem é responsável pela ação.

| Fase | Ação | Duração/Quando | Quem | Observação |
| --- | --- | --- | --- |--- |
| 1 | Atualizar data de ativação no LCS | No máximo, 2 a 3 meses de antecedência | Parceiro/Cliente | As datas de marco devem ser continuamente atualizadas. |
| 2 | Concluir e enviar lista de verificação | Após a conclusão do teste de aceitação do usuário (UAT) | Parceiro/Cliente | Siga as instruções fornecidas no [FastTrack de avaliação de ativação](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Avaliação do projeto (FastTrack) | Arquiteto FastTrack* | O arquiteto faz a avaliação depois que a lista de verificação é recebida e continua a revisão até que as perguntas sejam esclarecidas e as mitigações estejam em vigor, se aplicável. |
| 4 | Workshop de projetos (FastTrack) | Arquiteto FastTrack* | |
| 5 | Importações de pacotes de dados | Depende do projeto | Parceiro/Cliente | Siga as instruções em [Visão geral de gerenciamento de dados](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).|
| 6 | Pronto para produção | Depois que todas as etapas anteriores tiverem sido concluídas | Parceiro/Cliente | O Parceiro/Cliente pode assumir o controle do ambiente de produção.|
| 7 | Atividades de substituição | Depende do projeto | Parceiro/Cliente | |
| 8 | Ativação | Depende do projeto | Cliente | |

> [!IMPORTANT]
> *As etapas 3 e 4 são preenchidas somente para os clientes qualificados para o FastTrack.

## <a name="completing-the-lcs-methodology"></a>Conclusão da metodologia do LCS

Um importante marco em cada projeto de implementação é a transferência para o ambiente de produção. O processo de conclusão de uma etapa tem duas partes: 

- Faça o trabalho real, como uma análise de lacuna-ajuste ou o teste de aceitação do usuário (UAT). 
- Marque a etapa correspondente na metodologia do LCS como concluída. 

É uma boa prática concluir as etapas da metodologia à medida que você progride com a implementação. Não espere até o último minuto. É o melhor interesse do cliente ter uma implementação sólida. 

## <a name="uat-for-your-solution"></a>UAT para a sua solução

Durante a fase de UAT, você deve testar todos os processos de negócios que implementou e todas as personalizações feitas em um ambiente de Área Restrita no projeto de implementação. Para ajudar a garantir uma ativação bem-sucedida, você deverá considerar o seguinte ao concluir a fase de UAT: 

- Recomendamos que o seu processo de UAT comece com um ambiente limpo, no qual os dados da configuração OURO sejam copiados para o ambiente antes do início do processo de UAT. Recomendamos que você use o ambiente de produção como o ambiente OURO até a ativação, no ponto em que o ambiente se torna produção.
- Se os casos de teste cobrem todo o escopo de requisitos. 
- Teste usando dados migrados. Isso deve incluir dados, como trabalhadores, trabalhos e posições. Além disso, inclua saldos iniciais, como acúmulos de licenças e ausências. Por fim, inclua transações abertas, como registros em benefícios atuais. Conclua os testes com todos os tipos de dados, mesmo que o conjunto de dados não esteja finalizado. 
- Teste usando as funções de segurança corretas (funções padrão e funções personalizadas) atribuídas aos usuários. 
- Verifique se a solução está em conformidade com qualquer requisito normativo específico da empresa e do setor. 
- Documente todos os recursos e obtenha a aprovação do cliente. 

## <a name="mock-go-live"></a>Simulação da ativação

Antes da ativação, você deve executar uma simulação da ativação para testar as etapas necessárias para substituir os sistemas herdados pelo novo sistema. Você deve realizar a simulação de ativação em um ambiente de área restrita e incluir todas as etapas no plano de substituição.

- É recomendável usar o ambiente de produção como o ambiente de configuração OURO até a ativação.
- Garanta um processo de governança forte no local para proteger o ambiente de produção de transações ou atualizações acidentais antes da ativação.
- Quando estiver pronto para executar o UAT ou a simulação de ativação, atualize o ambiente de área restrita no ambiente de produção. Para obter mais informações, consulte [Copiar uma instância](hr-admin-setup-copy-instance.md).
- Teste cada etapa de seu plano de transição no ambiente de área de proteção e, em seguida, valide o ambiente de área restrita executando verificações de spot ou realizando testes de scripts UAT no ambiente.
  - Os testes devem incluir todas as migrações de dados, incluindo transformações necessárias para a ativação.
  - O processo deve incluir um fechamento de prática de todos os sistemas herdados.
  - Inclua as etapas de substituição de integração ou de sistema externo na simulação de substituição.
- Se você encontrar problemas durante a simulação de substituição, talvez seja necessária uma segunda simulação de substituição. Por esse motivo, recomendamos que você planeje duas simulações de substituição no plano de projeto.

## <a name="fasttrack-go-live-assessment"></a>Avaliação de ativação do FastTrack

Os clientes qualificados para FastTrack e que estejam envolvidos com um Arquiteto de Soluções FastTrack concluirão uma revisão de ativação com o Microsoft FastTrack. Para obter mais informações, consulte [Microsoft FastTrack](/dynamics365/fasttrack/). 

Cerca de oito semanas antes da ativação, a equipe FastTrack pedirá que você preencha uma [Lista de verificação de ativação](https://go.microsoft.com/fwlink/?linkid=2146013).

O gerente de projeto ou um membro de projeto chave deve preencher a lista de verificação de ativação durante a fase de pré-ativação do projeto. Normalmente, a lista de verificação é concluída de quatro a seis semanas antes da data de ativação proposta, quando o UAT é concluído ou está quase concluído. 

Depois de concluir a lista de verificação de ativação, envie-a por email ao Arquiteto de Soluções FastTrack. Inclua sempre um dos principais stakeholders do cliente e do parceiro de implementação no email. 

Depois de enviar a lista de verificação, o Arquiteto de Soluções FastTrack analisará o projeto e fornecerá uma avaliação que descreve os riscos potenciais, as práticas recomendadas e as recomendações para uma ativação bem-sucedida do projeto. Em alguns casos, o arquiteto de soluções poderá realçar os fatores de risco e pedir um plano de mitigação. 

## <a name="see-also"></a>Consulte também

[​Perguntas frequentes sobre ativação​](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
