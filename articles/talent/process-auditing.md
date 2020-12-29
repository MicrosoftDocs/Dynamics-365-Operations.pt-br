---
title: Controlar alterações nos dados de recrutamento
description: O processo do recurso de auditoria permite que você saiba quando candidatos, oportunidades de emprego ou aplicações de trabalho mudam por motivos de relatório ou conformidade.
author: tracykeya
manager: AnnBe
ms.date: 04/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: c009f82e69bff0e4ea540514de8f9e60eca1e466
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460371"
---
# <a name="track-changes-in-recruiting-data"></a>Controlar alterações nos dados de recrutamento

[!include [banner](includes/banner.md)]

Você pode rastrear as alterações feitas a candidatos, oportunidades de emprego ou aplicações de trabalho, usando o processo de auditoria. Isso é útil por motivos de relatório ou conformidade.

Você pode exibir os dados rastreados no Power BI usando o conector OData. Para obter mais informações, consulte [Conectar aos feeds de OData em Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-connect-odata).

## <a name="track-changes"></a>Controlar alterações
Para configurar o acompanhamento de alterações nos dados de recrutamento, siga estas etapas:

1. Em [Power Apps](https://web.powerapps.com), selecione o ambiente apropriado.

2. Selecione **Configurações** (o ícone de ferragens), escolha **Personalizações avançadas**, e depois selecione **Recursos** em **Recursos de desenvolvedor**. 

3. Na página **Recursos de desenvolvedor**, copie o valor no campo **Valor API da Web de Instância**. Por exemplo, o valor pode se parecer com: https://yourorgname.api.crm.dynamics.com/api/data/v9.1/.

4. Em seguida, você pode definir os dados de uma das seguintes entidades:
  - Histórico de abertura de trabalho (msdyn_jobopeninghistories)
  - Histórico de solicitação de emprego (msdyn_jobapplicationhistories) 
  - História do candidato (msdyn_candidatehistories)

## <a name="data-reported"></a>Dados relatados

Os seguintes dados estarão disponíveis com o processo de auditoria.

| Dados relatados | Descrição |
| --- | --- |
| Alterado por (msdyn_ChangedbyId) | Referência ao usuário |
| Criado em (createdon) |  Data e horário em UTC quando a mudança aconteceu |
| Alterar tipo (msdyn_changetype) | Que alteração aconteceu |
| Valores comuns para candidatos, oportunidades de emprego, <br></br>e aplicações de trabalho | Criado em<br></br>Atualizado |
| Histórico da solicitação de emprego | Artefato adicionado <br></br>Artefato removido |
| Histórico de abertura de emprego | TAREFA: postagem adicionada <br></br>TAREFA: postagem removida <br></br>TAREFA: postagem atualizada <br></br>TAREFA: participante adicionado <br></br>TAREFA: participante removido |
| Histórico do candidato | Artefato adicionado <br></br>Artefato removido <br></br>Experiência de trabalho adicionada <br></br>Experiência de trabalho removida <br></br>Educação adicionada <br></br>Educação removida <br></br>Habilidade adicionada <br></br>Habilidade removida <br></br>Etiqueta adicionada <br></br>Etiqueta removida <br></br>Rede social adicionada <br></br>Rede social removida <br></br>Detalhes pessoais adicionados <br></br>Detalhes pessoais atualizados<br></br> |
| Campos alterados (msdyn_changedfields) | Campos de listagem de objeto JSON alterada, pode não armazenar valores para todos os campos.<br></br><br></br>Para alterações "Criado" e "Atualizado", ele listará os campos no registro criado ou modificado.<br></br><br></br>Para tipos de alteração "Adicionado", ele listará os campos no registro filho.<br></br><br></br>**Exemplo:**<br></br><br></br>{<br></br>  "msdyn_applyurl": { "newValue": "" },<br></br>  "msdyn_description": { "valueOmitted": true } <br></br>} |
|Histórico da solicitação de emprego | Solicitação de emprego (msdyn_JobapplicatonId)<br></br>Status (msdyn_status) <br></br>Razão do status (msdyn_statusreason) <br></br>Motivo de rejeição (msdyn_rejectionreason) |
| Histórico de abertura de emprego | Oportunidade de emprego (msdyn_JobopeningId) <br></br>Status (msdyn_jobopeningstatus) <br></br>Razão do status (msdyn_jobopeningstatusreason) |
| Histórico do candidato | Candidato (msdyn_CandidateId) |
