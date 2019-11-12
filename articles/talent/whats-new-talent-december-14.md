---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (14 de dezembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c972c04638f436f2fd56055e83bbcf06b29a9f20
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551855"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-december-14-2018"></a>Novidades ou alterações no Dynamics 365 Talent - Core HR (14 de dezembro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.2085**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="changes"></a>Alterações

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a>EUA – suporte à ACA (Lei de Serviços de Saúde Acessíveis) para os formulários 1095-B e 1095-C do ano fiscal 2018

Todos os anos, os ALEs (Applicable Large Employers) devem fornecer aos funcionários em tempo integral um formulário 1095-C. Além disso, se o empregador fornece cobertura autossegurada, ele deverá fornecer o 1095-C (se for um ALE) e um 1095-B (se for um empregador pequeno) a um funcionário (em tempo integral ou em meio período), coberto por um dos planos de saúde oferecidos por ele. Este recurso fornece formulários imprimíveis para o 1095-C e 1095-B.

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a>Durante a importação, o campo SubmittedByPersonId na HcmPerfJournalEntity é ignorado

Ao importar/exportar entradas do diário de desempenho, o campo **Enviado por** é ignorado. Com esta alteração, o valor **importado/exportado** refletirá o valor na tabela durante a exportação. Ao importar, o sistema será atualizado com o valor fornecido no arquivo de importação.

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a>A guia Análise no espaço de trabalho "Licença e ausência" exibe o erro "OpenConnectionError" para funções administrativas fora do sistema

Com esta atualização, nenhum erro será exibido quando a guia **Análise** for aberta no espaço de trabalho **Licença e ausência** .

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Há falha na obtenção do nó principal no autoatendimento para funcionários e na busca detalhada de Hierarquia de posições a partir do bloco.

Uma alteração foi feita para corrigir o erro "Falha ao obter o nó principal" quando a hierarquia de posições for personalizada para aparecer em um espaço de trabalho existente e uma posição for selecionada na hierarquia.  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a>É necessário ser Administrador do sistema para ver a guia Folha de pagamento na página Posição

Uma alteração foi feita para incluir os elementos de segurança corretos no privilégio existente: "Manter detalhes da folha de pagamento e da posição do trabalhador". Com esta alteração, por padrão, o Administrador da Folha de pagamento terá acesso aos campos da Folha de pagamento na página Posição.

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a>Erro ao enviar a avaliação de desempenho para o gerente e o espaço reservado %Reviews.PerfPeriod% é usado nas instruções de envio

Uma alteração foi feita que corrige o erro "Referência nula” ao usar o espaço reservado %Reviews.PerfPeriod% nas instruções de Envio.

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a>O relatório de força de trabalho do Power BI mostra o erro quando a data de aniversário de tempo de serviço do trabalhador é dia 29 de fevereiro

Com esta alteração, o dia 29 de fevereiro agora tem suporte no Power BI.

### <a name="integration-between-core-hr-and-attract"></a>Integração entre o Core HR e o Attract

Uma alteração foi feita para atualizar a integração entre o Core HR e o Attract relacionada aos candidatos a serem contratados. Para que os candidatos a serem contratados fiquem visíveis no espaço de trabalho **Gerenciamento de Pessoal**, são utilizadas as seguintes entidades do Common Data Service:

Solicitação de emprego
- A razão do status deve ser definida como Oferta Aceita
-   Fornece o Candidato e a Oportunidades de Emprego

Candidato
-   Fornece as Informações do Candidato

Oportunidade de Emprego
-   Fornece a ID da Oportunidade de Emprego e os Participantes da Oportunidades de Emprego

Participantes da Oportunidade de Emprego
-   Fornece o Gerente de Contratação

Quando um candidato é adicionado ao Gerenciamento de Pessoal, o candidato agora pode ser ignorado usando uma nova opção disponível no cartão do candidato.

## <a name="coming-soon"></a>Em breve

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Licença e ausência: saldos futuros de licença e de previsão de licença

Com as alterações que estão sendo feitas para permitir que funcionários prevejam folgas e solicitem futuras folgas sem afetar seus saldos atuais de folga, a forma como os saldos de folga são exibidos também está sendo alterada. 

O saldo disponível atualmente exibido é a quantidade de folgas disponíveis para solicitações, incluindo os acúmulos até hoje e todas as solicitações de licença aprovadas. 

Quando a possibilidade de previsão for liberada, o saldo exibido será alterado para ser o saldo atual de folga, incluindo os acúmulos até hoje e as solicitações até hoje. Os funcionários e gerentes verão esses saldos atualizados no autoatendimento para funcionários e gerentes no cartão **Folga** e na janela **Saldos de folga**. Os gerentes de RH verão esses saldos atualizados no espaço de trabalho **Pessoas** e na janela **Planos de licença atribuídos** do funcionário.

## <a name="known-issue"></a>Problema conhecido

### <a name="mapping-errors-in-the-integration-with-finance"></a>Erros de mapeamento na integração com o Finance

Os problemas a seguir foram identificados no modelo atual de integração do Talent com o Dynamics 365 Finance. Um novo modelo será publicado em breve e aplicado a todos os novos projetos de integração que forem criados. Para projetos de integração existentes, os mapeamentos de tarefas podem ser atualizados. Consulte a tabela a seguir para os mapeamentos atualizados. 

>[!NOTE]
> A tarefa Posições de trabalho para Atribuição de Trabalho Pai às Posições não integra dados. Este é um problema que está sendo investigado no momento. Não há uma solução alternativa no mapeamento atual. 

A tarefa Departamentos para a Unidade operacional necessita dos seguintes mapeamentos atualizados.

| Campo de origem existente          | Novo campo de origem |
| -------------------------------|------------------|
| cdm_description (Descrição)  | cdm_name (Nome)  |

Também é necessário acrescentar um mapeamento adicional Selecione o último campo **Nenhum** para adicionar o mapeamento a seguir.

| Campo de origem                   | Campo de destino    |
| -------------------------------|----------------------|
| cdm_description (Descrição)  | NAMEALIAS (NAMEALIAS)|

Os mapeamentos atualizados devem ser semelhantes à imagem a seguir.

![Tarefa Departamentos para a Unidade operacional](./media/DepartmentMapping.png)


A tarefa Trabalhos para Detalhes do Trabalho necessita dos seguintes mapeamentos atualizados.

| Campo de origem existente          | Novo campo de origem                   |
| -------------------------------|------------------------------------|
| cdm_name (Nome)                | cdm_description (Descrição)      |
| cdm_name (Descrição)         | cdm_jobdescription(Descrição do trabalho)|


Os mapeamentos atualizados devem ser semelhantes à imagem abaixo.

![Trabalhos para Detalhes do Trabalho](./media/JobMapping.png)

A tarefa Trabalhadores para o Trabalho necessita dos seguintes mapeamentos atualizados.

| Campo de origem existente                 | Novo campo de origem                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (Endereço de email 1)   | cdm_primaryemailaddress (Endereço de email principal) |
| cdm_telephone1 (Telefone 1)          | cdm_primarytelephone (Telefone principal)       |

A transformação do campo Sexo também deve ser atualizada. Selecione o tipo de mapa **fn** (função) para o Sexo e atualize os seguintes mapeamentos de valor.

| Valor do Common Data Service                   | Valor do Finance and Operations                     |
| ----------------------------|--------------------------------------------------|
| 75440000                    | Masculino                                             |
| 75440001                    | Feminino                                           |
| 75440002                    | Nenhum                                             | 
| 75440003                    | Não especificado                                      |

Os mapeamentos atualizados devem ser semelhantes às imagens a seguir.

![Tarefa Trabalhadores para o Trabalho](./media/WorkerMapping.png)

![Transformação do campo Sexo](./media/WorkerTransform.png)
